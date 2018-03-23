Title: At last, Results!
Date: 2006-06-17 20:35:00
Category: general
Slug: at-last-results
Author: Russell Neches
Tags: science, physics
Summary: 


After more than a year of work, I've finally finished the calculations
and coding for my paper on high-performance tokamak equilibria (working
title: *Comparison of Analytic and Numerical High-Beta Equilibrium
Solutions*). This is my first piece of truly original research. This is
a little snapshot of the error analysis from my first parallel run:

![](http://vort.org/media/images/Ophidian_error.png)

The code is written in Python, with the bits that need to go fast
(numerical integration and root finding) compiled and optimized for the
local CPU flavor. The optimized functions were supplied by the wonderful
[SciPy project](http://scipy.org). Given how much work I put into this
project, I probably could have done it without SciPy, but I wouldn't
have wanted to. The end result would have been much less reliable,
slower, and more annoying to use. I am also extremely grateful for the
Debian project and its package maintainers, who deliver the only OS I
can find that has all the necessary packages compiled and ready to use.

Now, I just have to prepare the cases, run them, and write the
"Conclusions" and "Error Analysis" section. That, and cross my fingers
and hope that I don't get any grumpy reviewers.
