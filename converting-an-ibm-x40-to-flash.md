Title: Converting an IBM X40 to Flash
Date: 2008-02-21 19:02:29
Category: general
Slug: converting-an-ibm-x40-to-flash
Author: Russell Neches
Tags: ibm, x40, flash, cf, ssd
Summary: 


The Hitachi 1.8" hard drive in the IBM X40 is probably the worst data
storage product I've ever used. It is expensive, excruciatingly slow,
irritatingly loud, and non-standard. There are basically no options for
replacement except to just buy another one. And, as I discovered to my
sorrow, it is also fragile and unreliable. So, I decided to replace it
with a Compact Flash card.

You may have heard something about Solid State Drives (SSDs), such as
the one available as an option for Apple's MacBook Air. You can think of
this project as sort of a poor-man's version of these products.

While most CF drives are relatively small and expensive, there are a few
products that seem to sacrifice speed for capacity. This may seem
sub-optimal, but the drive it will be replacing is astonishingly slow to
begin with. According to hdparm, it can do buffered reads at 18 MB/sec,
but in practice that seems pretty optimistic.

If I understand correctly, the Compact Flash interconnect standard is
basically a subset of IDE. So, you just need a little passive adapter
board, and you can plug a CF card directly into an IDE port. I used a
[D44MIDECF adapter card from
Addonics](http://www.addonics.com/products/flash_memory_reader/ad44midecf.asp).
At \$20, it's a little overpriced. There are no active components, and
the board contains only the CF plug, the 44 pin IDE pinout, a jumper, a
surface mount resistor, a surface mount capacitor, and a surface mount
LED. On the other hand, it is something of a specialty part, so I
suppose I should be happy that they bothered to sell it to me at all.
For the CF card, I found [this monster on
NewEgg](http://www.newegg.com/Product/Product.aspx?Item=N82E16820211244).

![](http://vort.org/media/images/ad44midecf_diagram.gif)

The X40 doesn't have removable media (other than the SD/MMC reader).
I've always hated fiddling around with boot floppies and installers
anyway. Supposedly, Debian has gotten their installer in better shape
since I last played with it. That was more than five years ago. I just
skipped that whole process, and built out a minimal Debian install by
hand. I popped the CF disk into my SanDisk USB Flash reader, and did the
following :

    sudo fdisk /dev/sdc 
       # created a 31 GB primary partition tagged as Linux [id 83]
       # and a 1 GB primary partition tagged as Linux Swap [id 82]
    sudo mkfs.ext3 /dev/sdc1
    sudo mkswap /dev/sdc2
    sudo mount /dev/sdc1 /mnt/flash
    sudo debootstrap sid /mnt/flash/ http://linux.csua.berkeley.edu/debian
    sudo chroot /mnt/flash
    vi /etc/apt/sources.list
    apt-get update
    apt-get dist-upgrade
    apt-get install linux-image-2.6.24-1-686 grub sudo 
    mkdir /boot/grub
    update-grub
    vim /boot/grub/menu.lst
    exit
    sudo grub-install --root-directory=/mnt/flash --recheck /dev/sdc

Then, pop the CF card in its little adapter board into the drive bay,
and boot. Hooray! Here is how hdparm identifies the CF disk :

    /dev/hda:

     Model=, FwRev=20070912, SerialNo=CF CARD 000040D9
     Config={ HardSect NotMFM Fixed DTR>10Mbs }
     RawCHS=16383/15/63, TrkSize=0, SectSize=576, ECCbytes=4
     BuffType=DualPort, BuffSize=1kB, MaxMultSect=1, MultSect=off
     CurCHS=16383/15/63, CurSects=15481935, LBA=yes, LBAsects=63438848
     IORDY=no, tPIO={min:120,w/IORDY:120}, tDMA={min:120,rec:120}
     PIO modes:  pio0 pio1 pio2 pio3 pio4 
     DMA modes:  mdma0 mdma1 *mdma2 
     AdvancedPM=no

     * signifies the current active mode

The default IDE settings for the CF drive result in very slow
performance, so some tuning is in order. I edited /etc/hdparm.conf
accordingly :

    /dev/hda {
            write_cache = on
            io32_support = 3
            dma = on
            lookahead = on
            interrupt_unmask = on
    }

Here is the output of the script :

    Setting parameters of disc:
    /dev/hda:
     setting 32-bit IO_support flag to 3
     setting unmaskirq to 1 (on)
     setting using_dma to 1 (on)
     setting drive read-lookahead to 1 (on)
     setting drive write-caching to 1 (on)
     IO_support    =  3 (32-bit w/sync)
     unmaskirq     =  1 (on)
     using_dma     =  1 (on)
     look-ahead    = not supported
     write-caching = not supported
      /dev/hda.

The result is actually a little faster than the Hitachi hard drive :

    sudo hdparm -Tt /dev/hda

    /dev/hda:
     Timing cached reads:   1474 MB in  2.00 seconds = 737.30 MB/sec
     Timing buffered disk reads:   44 MB in  3.13 seconds =  14.06 MB/sec

So far, I'm pretty happy.
