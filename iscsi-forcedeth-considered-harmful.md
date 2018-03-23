Title: iSCSI on forcedeth considered harmful
Date: 2010-10-27 11:53:41
Category: general
Slug: iscsi-forcedeth-considered-harmful
Author: Russell Neches
Tags: hardware, computing, grad, school, eisenlab, research
Summary: 


One of the challenges with bioinformatics is that it is very, very easy
to generate overwhelmingly large datasets. The data is big to begin
with, and most analysis tends to generate even bigger intermediate
files. Even the digests can be many terabytes. Almost all of our work in
Jonathan Eisen's lab involves this problem, and inevitably, we ran out
of space.

We do not have any sort of lab IT staff, so I went looking for something
to expand our available storage without adding another computer to
administer, patch, update, upgrade, fiddle with, and worry about. After
some research and a few positive recommendations, I ordered a [Drobo
Pro](http://www.drobo.com/products/drobopro/) and eight 2TB drives. I
plugged the box into one of our desktop machines via USB, popped in the
drives, fired up [Drobo-Utils](http://drobo-utils.sourceforge.net/) and
within a few minutes I had mkfs chugging away. The filesystems mounted,
everyone was happy.

<p>
However, USB2.0 obviously isn't the ideal interface for a 16TB array,
and so we configured out NAS machine to talk to the Drobo with iSCSI.
Everything seemed to work... until we tried to actually push significant
amounts of data at it. Then, catastrophe!

>     sd 9:0:0:3: SCSI error: return code = 0x000e0000
>     end_request: I/O error, dev sdk, sector 2879867210
>     sd 9:0:0:3: SCSI error: return code = 0x000e0000
>     end_request: I/O error, dev sdk, sector 3007375778
>     ... lots and lots and finally ...
>     EXT3-fs error (device sdk1): ext3_journal_start_sb: Detected aborted journal
>     Remounting filesystem read-only

Then, about a month of frustrating thrashing about happened, which I
won't go into. The problem turned out to have nothing to do with the
Drobo -- it was the Ethernet controller in our NAS.

The motherboard in the NAS machine has an nForce chipset. Given my
personal experience with nVidia's video drivers in Linux, this wouldn't
have been my choice. Nevertheless, in this case nVidia seems to have
[tried to do the right
thing](http://liquidat.wordpress.com/2007/03/04/the-forcedeth-story/)
with the Open Source community. Sadly, the hardware itself is junk.

Basically, the Ethernet controller raises a stupendous number of IRQs,
and under certain kinds of high network loads, the system cannot handle
them as fast as they are generated; data loss results. There are a
number of
[bugs](http://bugs.debian.org/cgi-bin/bugreport.cgi?bug=506419) related
to this issue, with some workarounds and partial solutions. The best we
could achieve was to delay the collapse of the iSCSI link to about of
200GB traffic.

So, today I installed an Ethernet controller with an Intel Pro/1000
chipset (the e1000 driver). We moved the iSCSI link to the new
controller, where it has been completely stable under sustained 100%
load for almost a whole day. And, as a bonus, NFS is faster as well.
Evidently, NFS is more robust under high load and heavy packet loss than
iSCSI.

The moral of the story? If you are going to spend a couple of thousand
bucks on a fancy iSCSI storage solution, **do not use nForce Ethernet
controllers.** Make sure your order includes an Ethernet controller that
actually works. It'll cost \$35 and save you a ton of trouble.

I don't like to dump on peoples' work, and I certainly don't want to
discourage nVidia from working with the community. I do, however, want
nVidia to focus more on the quality of its engineering.
