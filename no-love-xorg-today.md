Title: No love for X.org today
Date: 2009-04-19 20:37:09
Category: general
Slug: no-love-xorg-today
Author: Russell Neches
Tags: xorg, bugs
Summary: 


I'd like to give a big fat raspberry to the
[X.org](http://www.x.org/wiki/) people today, and possibly the [Debian
X.org maintainers](http://wiki.debian.org/XStrikeForce), for pushing
busted X.org packages. Booo!

![](http://vort.org/media/images/grrr_cat.jpg)

If you should happen to download said packages, you will find mouse and
keyboard input on your computer completely disabled once the login
manager comes up. If you log in via ssh (or boot with "single" in your
kernel boot options), and look at /var/log/Xorg.0.log and observe the
following,

    (II) The server relies on HAL to provide the list of input devices.
        If no devices become available, reconfigure HAL or disable 
            AllowEmptyInput.
    (WW) AllowEmptyInput is on, devices using drivers 'kbd', 'mouse' or
            'vmmouse' will be disabled.
    (WW) Disabling Keyboard0

then you have contracted this particular affliction.

Dear X people, *why the fuck would you make the default behavior to
<bold>ignore</bold> properly configured devices?* Especially when this
can brick peoples' computers? Yes, I know about
[this](http://wiki.debian.org/XStrikeForce/InputHotplugGuide). I stand
by my raspberry. HAL still doesn't enable the right quirks for my
motherboard, even though I submitted FDI files more than two years ago.
HAL does not, and will not ever, work for everyone. When it works, it's
nice, and I'm in favor of it. But please, please stop making life suck
for people HAL doesn't help.

A pox on you all!

Anyway, the way you fix this particular bug is to add the line

    Option "AllowEmptyInput" "false"

to the ServerLayout section of your xorg.conf file. For example

    Section "ServerLayout"
        Identifier      "Default Layout"
        Screen          "Default Screen"
        InputDevice     "Generic Keyboard"
        InputDevice     "Configured Mouse"
        Option          "AllowEmptyInput"    "false"
    EndSection

Props to K.Mandla for [figuring it
out](http://kmandla.wordpress.com/2008/11/30/hal-xserver-153-and-allowemptyinput/).
