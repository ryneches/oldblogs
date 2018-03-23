Title: Sneak Pique
Date: 2011-07-13 03:41:10
Category: general
Slug: sneak-pique
Author: Russell Neches
Tags: code, software, user, interface, computing, science, davis, eisenlab, research, genomics
Summary: 


I'm about to release a new piece of Open Source software; it's a fast,
fully automated and very accurate analysis package for doing
[ChIP-seq](http://en.wikipedia.org/wiki/Chip-Sequencing) with bacteria
and archaea. I'm doing my best to avoid the sundry annoyances of of
bioinformatics software; it uses standard, widely used file formats, it
generates error messages that might actually help the user figure out
what's wrong, and I've designed the internals to be easily hackable.

I have two problems, though.

Most of the people who will be interested in using this software are
microbiologists and systems biologists, not computer people. At the
moment, the software is a python package that depends on
<a "http: www.scipy.org ">scipy</a>, [numpy](http://numpy.scipy.org/)
and [pysam](http://code.google.com/p/pysam/). I used
[setuptools](http://pypi.python.org/pypi/setuptools), wrote tests with
[nose](http://code.google.com/p/python-nose/), and hosted it on github.
If I were going to distribute it to experienced Linux users, it's
basically done. However, installing these dependencies on Windows and
MacOS is a showstopper for most people -- scipy in particular. So, how
would you suggest distributing it to MacOS and Windows users?

![](http://vort.org/media/images/Pique_GUI.png)

The second problem is... it's kind of ugly. I wrote the GUI in Tk, which
is not particularly great in the looks department. Should I bother
creating native tooklkit GUIs? Would that make people significantly more
comfortable? Or would it be a waste of time?
