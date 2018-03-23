Title: Bike saftey in Davis
Date: 2009-04-25 23:18:41
Category: general
Slug: bike-saftey-davis
Author: Russell Neches
Tags: code, ajax, imaging, gps, maps, commuting, bicycle, california, accident, davis
Summary: 


I've been tinkering with a little data visualization applet for looking
at bicycle crash data in Davis, and I thought this map might be
interesting to people. This is a image was generated with Google Maps
and a heatmap overlay generated with a
[gheat](http://code.google.com/p/gheat/) tile server.

![](http://vort.org/media/images/davis_bike_crashes_2004-2006_heatmap.png)

This is for 168 bicycle accidents that happened between 2004 and 2006. I
have a lot more data, but 95% of the work in this little project
involves parsing and renormalizing it. Evidently, police reports are not
written with data processing in mind! I suppose that makes perfect
sense. An officer at the scene of an accident probably has things on her
mind besides generating a nice, easy to parse data point for future
analysis. The priority seems to be completeness, rather than
consistency. My parsing code, for example, has to be able to correctly
detect and calculate distances measured in units of "feeet".

I'll release the applet here once I make an interface for it (and get
the rest of the data imported). Stay tuned.
