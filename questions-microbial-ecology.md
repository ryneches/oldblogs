Title: Questions of microbial ecology
Date: 2011-04-27 22:50:03
Category: general
Slug: questions-microbial-ecology
Author: Russell Neches
Tags: science, grad, school, davis, genome, gene, kamchatka, thermophiles, russia, eisenlab, metagenomics, research, genomics
Summary: 


When the first environmental sequencing projects were conducted, the
genetic bredth present within an environmental sample so far outstripped
the available sequencing capacity at the time that it was only possible
to obtain a tiny slice of the genetic material present. This gave
researchers two choices; either target a particular gene, or go fishing.
Both approaches have been extremely fruitful. Targeted studies of
ribosomal RNA led to [the discovery of the
archaea](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC432104/?tool=pmcentrez),
among other important accomplishments. The "fishing" approach (which has
a shorter history) has also led to
[exciting](http://www.ncbi.nlm.nih.gov/pubmed/15001713)
[discoveries](http://www.plosone.org/article/info:doi%2F10.1371%2Fjournal.pone.0018011).
If you do a literature search for your favorite enzyme with the word
"novel," it's quite likely that most of the recent publications will
involve some kind of metagenomic survey.

As the cost of sequencing continues to plummet, a third approach to
environmental sequencing has suddenly become possible: Exhaustive
sequencing. It should be possible not only to survey the entire genomes
of the organisms present (although assembling them is another story),
but also to survey the population-level variability of the organisms
present. This is a rather unprecedented development. Microbial
communities have suddenly gone from the most challenging ecologies, with
only a handful of observable characters, to a spectacularly detailed
quantitative picture.

Here is an example from one of my datasets :

![](http://vort.org/media/images/zav_roseiflexus_12518.png)

This is a small region in the genome of [Roseiflexus
castenholzii](http://ijs.sgmjournals.org/cgi/content/abstract/52/1/187).
I have mapped reads from an environmental sample to the reference
genome, yielding an average coverage of about 190x. If you look closely
at the column in the middle (position 12519 in the genome, in case you
care), we see some clear evidence of a single nucleotide polymorphism in
this population of this organism.

![](http://vort.org/media/images/zav_roseiflexus_12518_zoom.png)

As it happens, this coordinate falls in what appears to be an intergenic
region, between a phospholipid/glycerol acyltransferase gene on the
forward strand to the left and a glycosyl transferase gene one the
reverse strand to the right. The two versions appear with roughly equal
frequency in the data. For this organism, I've found single nucleotide
polymorphisms at thousands of sites. There are also insertions and
deletions, and probably rearrangements.

In this ecosystem, I'm able to get between 50x and 300x coverage for
almost every taxon present. This should make it possible to see variants
that make up only a percent or two of their respective taxon's
population. With data like this, it should be possible to do some really
beautiful ecology!

For example, suppose one wanted to see if a community obeys the island
biogeography model. One could measure the theory's three parameters,
immigration, emigration and extinction, by comparing the arrivals and
disappearances of variants between the "mainland" and the "island" over
time. The ability to examine variants within taxa should make these
measurements very sensitive. Additionally, because these are genomic
characters, it should be possible to control for the effects of
selection (to some extent) by leveraging our knowledge of their genomic
context. The 12519th nucleotide of the *R. castenholzii* genome is
perhaps a good example of a character that is unlikely to be under
selection because it happens to sit downstream from both flanking
genes.^1^

So, here is my question to you : What ecological model or process would
you be most excited to see studied in this way?

^1^ Well, actually I haven't looked at this site in detail, so I'm not
sure if one would or wouldn't reasonably expect it to be under
selection. My hunch is that it is less likely to be under stringent
selection than most other sites. I'm basing this hunch on eyeballing the
distance of this locus from where I think RNA polymerase would be
ejected on either side, and that both transcripts terminate into its
neighborhood. My point is that it should be possible to have *some* idea
of how selection might operate on a particular locus based on its
genomic context. One should take this with the usual grain of salt that
accompanies inferences drawn solely from models. A better example would
be a polymorphism among synonymous codons, but I wasn't able to find one
in a hurry.
