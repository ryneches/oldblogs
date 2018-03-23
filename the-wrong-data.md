Title: The Wrong Data
Date: 2006-10-26 23:38:34
Category: general
Slug: the-wrong-data
Author: Russell Neches
Tags: physics, science, code
Summary: 


I tracked down the problem that had been mucking up the unity-beta
results from Ophidian. Either Pierre or I accidentally checked in a
version of CUBE into the repository that wrote the output file data
tables in the output in a different order. So, all this time I had
thought it was a logic bug, or worse, a math error, turns out to be the
result of importing the wrong table.

The weird thing is that it somehow *passed* my integrity tests. It was
the right length, it had the right precision, it had the right boundary
conditions, and it had an inflection point.

![](http://vort.org/media/images/the_wrong_data.png)

Er, it had *lots* of inflection points. I guess I should add a test for
the entropy before I pass imported data to the rest of my code. These
are all supposed to be nice, smooth, differentiable functions. I don't
even use the data in this table -- I think it has something to do with
benchmarking the convergence cycle. Maybe it's a poorly calculated
magnetic shear. Maybe it's some sort of error distribution. All I know
about it is that the values came out of a vector burried somewhere in
the solver, and that it's labled "s".

![](http://vort.org/media/images/wrongtrousers.jpg)

That's the trouble with computers. You leave one thing out of place, and
before you know it, they go stomping all over the place. Sooner or
later, you will find yourself the victim of your own Techno Trousers.
Anyway, here my plot from last week, but without the garbage.

![](http://vort.org/media/images/xi_no_shit_small.png)

No, I'm not going to explain what it means. You'll just have to wait for
the paper.
