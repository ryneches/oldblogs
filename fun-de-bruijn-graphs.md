Title: Fun with de Bruijn graphs
Date: 2010-10-29 04:34:52
Category: general
Slug: fun-de-bruijn-graphs
Author: Russell Neches
Tags: code, computing, science, python, grad, school, davis, eisenlab, metagenomics, research
Summary: 


One of the projects I'm working on right now involves searching a better
approaches to assembling short read data metagenomic data. Many of the
popular short read assembly algorithms rely on a mathematical object
called a [de Bruijn graph](http://en.wikipedia.org/wiki/De_Bruijn_graph). I wanted to play
around with these things without having to rummage around in the guts
of a real assembler. Real assemblers have to be designed with speed
and memory conservation in mind -- or, at least they ought to be. So,
I decided to [write my own](http://github.com/ryneches/debruijnator).
My implementation is written in pure Python, so it's probably not
going to win any points for speed (I may add some optimization later).
However, it is pretty useful if all you want to tinker around with de
Bruijn graphs.

Anyway, here is the de Bruijn graph for the sequence
`gggctagcgtttaagttcga` projected into 4-mer space :

![](http://vort.org/media/images/mini_debruijn.png)

This is the de Bruijn graph in 32-mer space for a longer sequence (it
happens to be a [16S
rRNA](http://en.wikipedia.org/wiki/16S_ribosomal_RNA) sequence for a
newly discovered, soon-to-be-announced species of Archaea).

![](http://vort.org/media/images/long_contig_debruijn.png)

It looks like a big scribble because it's folded up to fit into the
viewing box. Topologically, it's actually just two long strands; one for
the forward sequence, and one for its reverse compliment. There are only
four termini, and if you follow them around the scribble, you won't find
any branching.
