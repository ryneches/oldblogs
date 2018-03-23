Title: Ubuntu X.org frustrations
Date: 2007-05-04 23:20:03
Category: general
Slug: ubuntu-x-org-frustrations
Author: Russell Neches
Tags: ubuntu, xorg, monitor, screen, bugs
Summary: 


To those of you who may be struggling to get your non 4:3 aspect ratio
monitor working under the new Ubuntu release (Feisty), here is the
magical incantation that will make it happy:

    russell@riouj:~$ gtf 1440 900 60

      # 1440x900 @ 60.00 Hz (GTF) hsync: 55.92 kHz; pclk: 106.47 MHz
      Modeline "1440x900_60.00"  106.47  1440 1520 1672 1904  900 901 904 932  -HSync +Vsync

Place the output into the "Monitor" section of /etc/X11/xorg.conf, and
restart X. Obviously, choose the resolution and frequency that is
suitable for your monitor. The one above is appropriate for an iMac G5.
