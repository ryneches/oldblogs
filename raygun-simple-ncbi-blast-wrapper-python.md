Title: raygun : a simple NCBI BLAST wrapper for Python
Date: 2010-10-25 11:42:04
Category: general
Slug: raygun-simple-ncbi-blast-wrapper-python
Author: Russell Neches
Tags: code, science, python, grad, school, eisenlab, metagenomics, research
Summary: 


Things have been a little quiet on Vort.org for the last couple of
weeks, but a lot of frantic activity has been going on behind the
peaceful lack blog updates. When I returned from
[Kamchatka](http://vort.org/tag/kamchatka/),
[Jonathan](http://phylogenomics.blogspot.com/) had a little present for
me -- he took the DNA from the 2005 Uzon field season for Arkashin and
Zavarzin hotsprings, and ran a whole lane of paired-end sequencing on
one of our Illumina machines.
[Charlie](http://dnatech.genomecenter.ucdavis.edu/) made some really
beautiful libraries, and the data is really, really excellent. For the
last couple of weeks, I've been trying to do justice to it.

I'm not quite ready to talk about what I've been finding, but I thought
I would take a moment to share a little tool I wrote along the way. It's
made my life a lot easier, and maybe other people could get some use out
of it.

It's called [raygun](http://github.com/ryneches/raygun), a very simple
Python interface for running local [NCBI
BLAST](http://blast.ncbi.nlm.nih.gov/Blast.cgi) queries. You initialize
a RayGun object with a FASTA file containing your target sequences, and
then you can query it with strings or other FASTA files. It parses the
BLAST output into a list of dictionary objects, so that you can get
right to work.

It doesn't take a lot of scripting chops to do this without an
interface, of course, and there are [other Python tools for running
BLAST
queries](http://biopython.org/DIST/docs/tutorial/Tutorial.html#htoc80).
The advantage of raygun over either the DIY approach or the BioPython
approach is that raygun is extremely simple to use. I wanted something
that would basically be point-and-shoot :

>     import raygun
>     import cleverness
>
>     rg = raygun.RayGun( 'ZOMG_DNA_OMG_OMG.fa' )
>
>     hits = rg.blastfile( 'very_clever_query.fa' )
>
>     results = []
>     for hit in hits :
>         results.append( cleverness.good_idea( hit[ 'subject' ] ) )
>
>     cleverness.output_phd_thesis( results )

Unfortunately, you must furnish your own implementation of the
cleverness module.

I designed raygun is with interactive use in mind, particularly with
[ipython](http://ipython.scipy.org/moin/) (by the way, if you do a lot
of work in python and you're not using ipython, you're being silly).
[The code is available on github](http://github.com/ryneches/raygun).
