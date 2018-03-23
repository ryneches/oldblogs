Title: Ophidian Complete!
Date: 2006-08-31 01:54:40
Category: general
Slug: ophidian-complete
Author: Russell Neches
Tags: science 
Summary: 


I finally nailed down the bugs in the edge-finding code, so now Ophidian
interpolates a nice, smooth plasma edge from the data provided by CUBE.

![](http://vort.org/media/images/lcfs_edge.png)

The red points are the grid points just inside the plasma, and the blue
points are the interpolated position of the last closed flux surface.
This would have been a simple problem, except the [Python NURBS
library](http://runten.tripod.com/NURBS/) doesn't work and hasn't been
updated in years. This wasn't an actual wheel re-inventing event, but I
did find that all current wheel implementations were but shattered
monuments, and was forced to chisel my own by studying the shards I was
able to excavate from the hardening loam of the Internet's sedimentary
layers.

![](http://vort.org/media/images/ophidian_smooth.png)

Once the grid is represented as a non-uniform rational B-spline (which
just sounds cooler than "NURBS"), finding the plasma boundary is just an
exercise in projecting the surface onto a plane and finding roots of
some cubic equations. So, after spending a few hours mixing up the array
indexes, I managed to write a beautiful solution to my problem. Most
importantly, it got rid of the nasty wedges of points where the
psi-solver would generate bad data.

The only issue left on my list of bugs is that the boundary finder will
get confused if there are any regions of vacuum flux that exceed zero
flux. That tends to happen near vertical field coils, especially when
computing equilibria for highly shaped plasmas. Unfortunately, plasma
shaping is very important, so I'll probably have to fix this eventually.
For this paper, though, I'm going to stick to circular, large aspect
ratio equilibria. Nothing too exotic.
