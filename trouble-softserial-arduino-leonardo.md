Title: Trouble with SoftSerial on the Arduino Leonardo
Date: 2012-05-25 12:05:31
Category: general
Slug: trouble-softserial-arduino-leonardo
Author: Russell Neches
Tags: code, bugs, free, software, hardware, computing, science, grad, school, davis, eisenlab, research
Summary: 


While I was wandering around at [Maker Faire](http://makerfaire.com/)
last weekend, I heard someone say, "Woah, is this the Leonardo?" And lo,
there was a handful of Arduino Leonardo boards lined up on a shelf for
sale. I instantly grabbed one, and bundled it home to play with it.

![](http://vort.org/media/images/arduino_leonardo.jpg)

The Leonardo is Arduino's latest board, [announced last
September](http://arduino.cc/blog/2011/09/17/arduino-launches-new-products-in-maker-faire/).
It uses the Atmega32u4 chip, which has onboard USB. This has two
important implications; first, the Leonardo costs less than the Uno, and
second it will be able to operate in any USB mode. That means people can
make Human Interface Devices (HID), like mice and keyboards and
printers, with Arduino, and present themselves to the host using the
standard USB interfaces for those devices. That means you can build
things that don't need to talk via serial, and use the host's built-in
drivers for mice and printers and whatnot. This is a big step forward
for Open Hardware.

Anyway, I'm developing an little remote environmental data logger to use
for part of my [dissertation
project](http://vort.org/2012/03/04/blogging-my-candidacy-exam/), and I
thought I'd see if I could use the Leonardo board in my design. I'm
using the Arduino board to talk to an [Atlas Scientific pH
stamp](http://atlas-scientific.com/product_pages/embedded/ph.html),
which communicates by serial. It works fine on the Uno with
[SoftwareSerial](http://arduino.cc/en/Reference/SoftwareSerial)
(formerly known as
[NewSoftSerial](http://arduiniana.org/libraries/newsoftserial/) until it
was beamed up into the Arduino Core mothership).

<p>
Unfortunately, it didn't go so well on the Leo. The board can send
commands to the pH stamp, but doesn't receive anything. I swapped in an
FTDI for the pH stamp, and confirmed that the Leonardo is indeed sending
data, but it didn't seem to be able to receive any characters I sent
back. I tried moving the rx line to each the digital pins, and had no
luck. Here is my test program :

>     #include <SoftwareSerial.h>
>
>     #define rxPin 2
>     #define txPin 3
>
>     SoftwareSerial mySerial( rxPin, txPin );
>
>     byte i;
>     byte startup = 0;
>
>     void setup() {
>
>       mySerial.begin( 38400  );
>       Serial.begin(   9600   );
>     }
>
>     void loop() {
>       
>       if( startup == 0 ) {             // begin startup
>         for( i = 1; i <= 2; i++ ) {
>           delay( 1000 );
>           mySerial.print( "l0\r" );    // turn the LED off
>           delay( 1000 );
>           mySerial.print( "l1\r" );    // turn the LED on
>         }
>         startup = 1;                   // don't re-enter
>       }                                // end startup
>
>       Serial.println( "taking reading..." );
>       mySerial.print( "r\r" );
>       delay(1000);
>       
>       Serial.println( mySerial.available() );
>       
>     }

On the Uno, I see the number increasing as the read buffer fills up :

>     taking reading...
>     0
>     taking reading...
>     0
>     taking reading...
>     7
>     taking reading...
>     16
>     taking reading...
>     16

On the Leo, it seems that nothing ever gets added to the read buffer, no
matter how any characters I send over from the FTDI or which pins I used
for the rx line :

>     taking reading...
>     0
>     taking reading...
>     0
>     taking reading...
>     0
>     taking reading...
>     0
>     taking reading...
>     0
>     taking reading...

I really wanted to see if I was crazy here, but I'm one of the first
people among the General Public to get their hands on a Leonardo board.
So, I started talking with Ken Jordan on \#arduino on Freenode (he goes
by Xark) who has a similar board, the [Atmega32u4
Breakout+](http://www.ladyada.net/products/atmega32u4breakout/). It's
based on the same chip as the Leonardo, but it has different pinouts and
a different bootloader. He flashed the Leonardo bootloder onto his
board, and worked out the following pin mapping :

> <small>
>
>     Arduino 1.0.1     Adafruit         ATMEL
>     digitalWrite pin  atmega32u4+ pin  AVR pin function(s)
>     ----------------  ---------------  ------------------
>     D0                D2               PD2 (#INT2/RXD1)
>     D1                D3               PD3 (#INT3/TXD1)
>     D2                D1               PD1 (#INT1/SDA)
>     D3#               D0               PD0 (#INT0/OC0B)
>     D4/A6             D4               PD4 (ICP1/ADC8)
>     D5#               C6               PC6 (OC3A/#OC4A)
>     D6#/A7            D7               PD7 (T0/OC4D/ADC10)
>     D7                E6 (LED)         PE6 (INT6/AIN0)
>     D8/A8             B4               PB4 (PCINT4/ADC11)
>     D9#/A9            B5               PB5 (OC1A/PCINT5/#OC4B/ADC12)
>     D10#/A10          B6               PB6 (OC1B/PCINT6/OC4B/ADC13)
>     D11#              B7               PB7 (OC0A/OC1C/PCINT7/#RTS)
>     D12/A11           D6               PD6 (T1/#OC4D/ADC9)
>     D13#  (LED)       C7               PC7 (ICP3/CLK0/OC4A)
>     D14   (MISO)      B3               PB3 (PDO/MISO/PCINT3)
>     D15   (SCK)       B1               PB1 (SCLK/PCINT1)
>     D16   (MOSI)      B2               PB2 (PDI/MOSI/PCINT2)
>     D17   (RXLED)     B0               PB0 (SS/PCINT0)
>     D18/A0            F7               PF7 (ADC7/TDI)
>     D19/A1            F6               PF6 (ADC6/TDO)
>     D20/A2            F5               PF5 (ADC5/TMS)
>     D21/A3            F4               PF4 (ADC4/TCK)
>     D22/A4            F1               PF1 (ADC1)
>     D23/A5            F0               PF0 (ADC0)
>     -     (TXLED)     D5               PD5 (XCK1/#CTS)
>     -     (HWB)       -  (HWB)         PE2 (#HWB)
>
> </small>

This was derived from the [ATmega 32U4-Arduino Pin
Mapping](https://github.com/arduino/Arduino/blob/master/hardware/arduino/variants/leonardo/pins_arduino.h>pins_arduino.h</>%20for%20the%20Leonardo%20board,%20the%20<a%20href=)
and ATMEL's [datasheet for the ATmega32U4
chip](http:/www.atmel.com/Images/doc7766.pdf). Once that was worked out,
he flashed my test program onto his board, and also found that
SoftwareSerial could transmit fine, but couldn't receive anything.

Ken rummaged around a little more, and had this to say :

> The SoftSerial seems to use PCINT0-3 so there seems to me a minor
> problem in Leo-land in that only PCINT0 appears to be supported (and
> it is on "funky" output for RXLED). Hopefully I am just
> misunderstanding something (but it imay be the interrupt remap table
> is incorrect for Leo).

Then he disappeared for a little while, and came back with :

> I have confirmed my suspicion. When I disassemble SoftSerial.cpp.o I
> can see that only \_\_vector\_9 is compiled (i.e., one of 4 \#ifdefs
> for PCINT0-3) and the interrupt vector 10 is PCINT0 (0 is reset vector
> so offset by one makes sense). So, unless you hook serial to RXLED pin
> of CPU I don't believe it will work with the current libs.
> <p>
> Also I believe the Leo page is just wrong when it says pins 2 & 3
> support pin change interrupts (I think this was copied from Uno but it
> is incorrect, the only (exposed) pins are D8 D9 D10 and D11 that
> support PCINT according to the [ATMEL
> datasheet](http:/www.atmel.com/Images/doc7766.pdf) (and these are
> PCINT 4-7 not the ones in the interrupt mapping table AFAICT).

I believe this is where I can stop worrying that I'd be wasting the time
of the core Arduino developers, and say *quod erat demonstrandum*; it a
bug in SoftwareSerial. Hopefully they can update the Arduino IDE before
the boards hits wider distribution.

**Update :** So, it turns out that this is a known limitation of the
Leonardo. David Mellis looked into it, and left this comment :

> You're right that the Leonardo only has one pin change interrupt,
> meaning that the software serial receive doesn't work on every pin.
> You should, however, be able to use pins 8 to 11 (inclusive) as
> receive pins for software serial. Additionally, the SPI pins (MISO,
> SCK, MOSI) available on the ICSP header and addressable from the
> Arduino software as pins 14, 15, and 16 should work.

He is, of course, correct. I'm not sure why my testing didn't work on
pins 8-11, but they do indeed work fine. Unfortunately, this means that
the Leonardo is not compatible with a number of cool shields. The
Arduino SoftSerial Library Reference documentation has been updated with
a [more detailed list of
limitations](http://arduino.cc/en/Reference/SoftwareSerial).
