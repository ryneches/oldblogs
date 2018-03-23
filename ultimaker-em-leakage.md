Title: Ultimaker EM leakage
Date: 2012-02-01 16:06:21
Category: general
Slug: ultimaker-em-leakage
Author: Russell Neches
Tags: davis, eisenlab
Summary: 


Steven Lucero, the machinist for Biomedical Engineering, just finished
building his own (well, the college's) Ultimaker 3D printer. BME is in
the process of setting up a pretty awesome rapid prototyping facility,
with an [Objet Eden 260](http://twitpic.com/75qlgn), a
[MakerBot](http://twitpic.com/8ay57r) and now an Ultimaker. To go with
the 3D printers, Steven is also setting up a little electronics lab to
go with it. A few weeks ago, he asked me for a shopping list of items
that would be useful for electronics hacking, which I was delighted to
provide.

One of the things I had to put on my shopping list for Steven was a
basic oscilloscope. It's amazing how useful these things are. I've
wanted my own o-scope for a long time, and so I happened to have a bunch
of low-cost o-scopes bookmarked. Steven ended up buying exactly the one
I would have bought for myself, which is [sold by
Sparkfun](http://www.sparkfun.com/products/10806) (they're sold out
right now, unfortunately).

I wanted to see if I liked the software, so while Steven was printing
something on his Ultimaker, I put two of the probes next to the X and Y
stepper motors to measure the EM leakage.

![](http://vort.org/media/images/oscope_and_ultimaker.jpg)

Like most modern digital oscilloscopes, you can freeze the trace, and
save the data as a CSV file onto a USB key. So, here's what the EM
leakage from the stepper motors looks like during a print :

![](http://vort.org/media/images/oscope_ultimaker_trace.png)

Cool, huh?
