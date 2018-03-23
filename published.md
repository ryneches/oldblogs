Title: Published!
Date: 2008-12-10 16:01:25
Category: general
Slug: published
Author: Russell Neches
Tags: power, nuclear, science, energy, python
Summary: 


I just got the email from AIP a few hours ago; my first paper as first
author [is published](http://link.aip.org/link/?PHP/15/122504)!

It was a surprisingly long process. I think most of the delays were due
to my own lack of experience. Hopefully, they are lessons learned, and
my next trip through the publishing gauntlet will be easier, faster, and
hopefully even more fun.

My uncle asked me if I would try to explain what I did in simple terms,
so here it goes.

There is a thingy called a
[tokamak](http://en.wikipedia.org/wiki/Tokamak) that is basically a very
fancy Thermos. It keeps hot things hot. If you can make the stuff inside
hot enough, it will work like a nuclear reactor. This is interesting
because it is possible to build much better, much safer nuclear reactors
this way. The trouble is, these Thermos things cost billions of dollars.
[The one they are building in France](http://en.wikipedia.org/wiki/ITER)
is going to cost something like nine billion bucks, and it will get
barely hot enough enough to work as an experiment. Real ones would cost
even more.

The good news is that the current designs for these fancy bottles only
use a few percent of their heat-trapping capacity. That's what 'beta'
means in the title; you can think of it as the heat-trapping efficiency
of the machine. This is different from the energy efficiency, though.
The heat trapping efficiency is more like how full you can fill the
Thermos. Right now, we are building a nine billion dollar Thermos, and
only filling it to 2% of its theoretical capacity. If we could use more
of the heat-trapping capacity, then you could maybe reduce the cost by a
factor of ten or a hundred (or increase the performance by that much).

So, this line of research is all about computer simulations of these
doughnut-shaped nuclear Thermoses, and how they behave when they are
nearly full.

In some other papers, I helped show that it is likely possible to build
a nuclear Thermos that you can fill almost all the way up. In another
paper, I also helped my friend Pierre show that it is possible to start
with a nearly empty Thermos, and fill it to nearly full without anything
bad happening (it all comes down to how you pour, to stretch the
metaphor).

Typically, you have a theory that you trust, and you want to know if
your computer simulation matches the theory. In this case, however, we
built a computer simulation that contained very few assumptions. It
solves [Maxwell's
equations](http://en.wikipedia.org/wiki/Maxwells_equations) (for
magnetic fields and currents) and [Newton's
equations](http://en.wikipedia.org/wiki/Newton%27s_laws) (for moving
masses). This is nice, because those equations have been tested really,
really well over the last 130 years. It also means that you can take the
output of the computer program, and very easily check to see if it is
correct.

As a result, we had the opposite problem one normally faces in science;
a computer program that we trusted, and a theory that maybe we didn't.
In this paper, I used the computer program to validate that the theory
was correct. I did this in an unusual way. The theory is approximate,
and so we expected it to go funny in some places. I treated the
computer-generated output as the "exact" solution, and showed that when
you subtract the theoretical result from the result we got from the
computer, the difference is precisely the amount by which we expected
the theoretical result to go funny. (In more rigorous language, I proved
that the deviation from the numerical result has the same scaling as the
error term in the expansion.)

[Here is a link to the
paper](http://vort.org/media/papers/PhysPlasmas_15_122504.pdf), in case
you don't have access to AIP.
