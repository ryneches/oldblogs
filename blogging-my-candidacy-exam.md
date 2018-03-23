Title: Blogging my candidacy exam
Date: 2012-01-09 02:49:39
Category: general
Slug: blogging-my-candidacy-exam
Author: Russell Neches
Tags: science, grad, school, davis, genome, gene, eisenlab, metagenomics, research, genomics
Summary: 


I've finally scheduled my candidacy exam for the the 17th of January --
quite a bit later than my target date of August last year, but scheduled
nonetheless -- and I'm scrambling to arrange my research into something
that works as a talk. I've tried a couple of different approaches, and
nothing really feels natural. What I've decided to do is model my talk
on a well-worn habit of mine; posting things to my blog, and then
talking about what I've posted. So, I'm going to do my dissertation
proposal right here, on my blog. This will be the "primary" source, and
the the actual exam and the written proposal will just be derivative
products.

When I was in [Kamchatka](http://vort.org/tag/kamchatka/), I found that
in many areas, there were little hot springs all over the place. Here's
one of my favorites :

![](http://vort.org/media/images/uzon_bubblers.jpeg)

Each is about the size of a small bowl of soup, and they are so numerous
that it's sometimes impossible to avoid stepping in them. You can tell
just by looking at them that they have fairly different chemistry; I'm
given to understand that the different colors are due to the dominant
oxidation species of sulfur, and the one on the far left was about
thirty degrees hotter than the other two. All three of them are almost
certainly colonized by a variety of fascinating microbes.

Ever since seeing these hot springs, and others like them bubbling out
of wastelands sterilized by volcanic cataclysm, I have been perplexed by
one question : *How did they get there?*

Extremeophiles are fascinating. Delving into their biology has yielded
rich seam of both applied and basic science. Extremeophiles must live
differently, and their adaptations have taught us a lot about how
evolution works, about the history of life on earth, about biochemistry,
and all sorts of interesting things. However, their very peculiarity
poses an interesting problem. Imagine you would freeze to death at
80&deg; Celsius. How does the world look to you? Pretty inhospitable, I'd
imagine; a few little ponds of warmth dotted across vast deserts of
freezing death. Until humans came along and started building water
heaters, the all of earth's oases of warmth were in in volcanic regions.

Clearly, dispersal plays an essential role for the survival and
evolution of these organisms. Yet, we know almost nothing about microbes
get around the planet. The model that reigned supreme in microbiology
since it was first proposed in 1934 is [Lourens Baas
Becking's](http://en.wikipedia.org/wiki/Lourens_Baas_Becking), "*alles
is overal: maar het milieu selecteert*" (everything is everywhere, but
the environment selects). This is a pretty profound idea; it asserts
that microbial dispersal is effectively infinite, and that differences
in the composition of microbial communities at seemingly identical sites
are due to unknow selective parameters (i.e., the sites only seem
identical because we don't understand them well enough). This model has
been a powerful tool for microbiology, and much of what we know about
cellular metabolism has been learned by the careful tinkering with
selective growth media the hypothesis exhorts one to conduct.
Nevertheless, it just doesn't seem *reasonable*. Microbes do not
disperse across continents by quantum teleportation; they must face
barriers and obstacles, some perhaps insurmountable, as well as conduits
and highways. Even with their rapid growth and vast numbers, this
landscape of barriers and conduits must influence their spread around
the world.

Since Darwin, it has been known that these barriers and conduits are
crucial evolutionary mechanisms. Evolution can be seen as an interaction
of two processes; drift and selection. The nature of the interaction is
determined by the structure of the population. A monolithic population
evolves differently than a fragmented population, even if the drift
mechanisms and selective pressures are identical. And so, if we want to
understand the evolution of microbes, we need to know something about
this structure. Bass Becking asserted that the structure is monolithic
for all species microbes across the planet. In the last decade or so,
people like [Rachel
Whitaker](http://mcb.illinois.edu/faculty/profile/1544) have challenged
the Bass Becking model by looking at the biogeography of thermophilic
microbes (mostly *Sulfolobus islandicus*), first by 16S rRNA
phylogenetics and later [using multi-locus
methods](http://www.citeulike.org/user/rneches/article/3511138). It is
fairly easy to reject the first part of the Bass Becking hypothesis on
the basis of this data.

Nevertheless, the existing studies merely establish that some microbes
have a biogeography. They do not ascertain how much of the biogeographic
signal is due to local selection, and how much is due to dispersal. If
we want to understand the global structure of microbial populations, we
need a method that allows us to make this distinction.

Which brings us around to my hypothesis, which is pretty simple. I think
that dispersal plays a major role in the formation of microbial
communities.

To see if this indeed the case, we need to be able to do two things.
First, we need to build phylogenetic trees of microbes of the same
species found at different sites. Second, before we build these trees,
we need to isolate the effect of selection from drift (or, barring that,
we need need to partly isolate them in a way that can be parameterized
for variational analysis).

The general model used to study the structure of dispersal events in
populations is called the metacommunity. Metacommunity dynamics is an
extension of
[metapopulation](http://en.wikipedia.org/wiki/Metapopulation) dynamics;
a metapopulation is simply a group of populations that are connected
enough to interact, but not so much that they can be considered a single
population. The best example I can find of a metapopulation study is
[C.B. Huffacker's work on predator-prey
dynamics](http://www.citeulike.org/user/rneches/article/10031052). I'll
briefly describe this work because it clearly illustrates why
metapopulations (and metacommunities) are important.

If you've taken college-level calculus, you've probably encountered the
[Lotka-Volterra
equations](http://en.wikipedia.org/wiki/Lotka-Volterra_equation) of
predator-prey dynamics. For "reasonable" initial conditions and
parameters, they predict stable coupled oscillations in predator and
prey populations. However, when people tried to observe these dynamics
in the wild, or experimentally, the result was typically extinction
before any stable oscillations happened. Or, sometimes the system would
suddenly veer toward an extreme and then crash to extinction after it
had seemed to have settled into a stable mode. It turns out that the
combination of discrete units (you can't have a fractional fox or a
partial rabbit, at least not a living one) and stochastic effects can
very easily destabilize the system.

However, Huffaker was able to observe very stable predator-prey dynamics
using a species of mite that feeds on oranges and another species of
predatory mite. Here is one of the oranges used in the study :

![](http://vort.org/media/images/huffaker_orange.png)

The trick was to use more than one orange, and to keep them somewhat
separated. Both species of mite were able to travel among the oranges at
a rate that varied with the distance separating each orange from its
neighbors. Huffaker also varied the rate of dispersal by replacing some
of the oranges with rubber balls, like so :

![](http://vort.org/media/images/huffaker_oranges_500.png)

The four light colored spheres on the left are the oranges, and the rest
are rubber balls. The stability of the predator-prey dynamic was found
to be a function of the dispersal rates among the oranges. Place them
too close together, and they behaved as a single environment, and the
result was global stochastic instability resulting in global extinction.
Place them too far apart, and each orange behaved as a single
environment, and the result was local stochastic instability resulting
in uncorrelated local extinctions on all the oranges. At intermediate
distances, local stochastic instabilities would lead to local
extinctions, but because these events were uncorrelated, the local
extinction events were followed by recolonization from neighboring
oranges. This resulted in a globally stable predator-prey dynamic.

![](http://vort.org/media/images/huffaker_oranges_random.png)

Because there are two interacting species of mite, Huffaker's experiment
is really better understood as *two* metapopulatons; one of the prey,
and one of the predator. One could take the view that this is a
meta-meta-population, but the preferred framework is to think of the
predator-prey dynamics taking place on each orange as a community, and
that the experimental setup comprises a single metacommunity. This is
the model I will be using, although I will be using it in a different
way than Huffaker's experiment. Huffaker *specified* the dispersal rates
and observed the resulting dynamics; I will be observing the community
composition, modeling their recent evolutionary histories, and inferring
the dispersal rates from these histories.

So, enough background. Here's how I will actually go about doing this.

### Aim 1 : Select sites

The first order of business is to collect samples. For a variety of
reasons which will become clear as a I go along, I have chosen to study
microbes in hypersaline environments. For practical reasons, I am
limiting the scope of the study to those sites that are roughly within
one day's drive and one day's hike from UC Davis.

Obviously, it is impossible to collect samples from *every* community
that meets these criteria, and so I will not have a perfectly complete
picture of the *actual* metacommunity of halophilic archaea. So, it is
necessary to develop an informative sub-sample. In previous microbial
biogeography studies, the site selection seems to have been essentially
*ad hoc*. Sites were included because they were available, not because
there was a expectation that their distribution in space (or some other
parameter) would be a representative sampling of the complete community.

Fortunately, as I have [written about
before](http://vort.org/2011/10/01/borax-lake-sample-collection-and-processing/),
the US Geological survey has built [a massive catalog of hydrological
features](http://hotspringchem.wr.usgs.gov/) across the Western United
States. It's as complete a list of substantial, persistent halophile
habitats as one could possibly wish for, with almost two thousand
possible sites in California, Nevada and Oregon alone :

![](http://vort.org/media/images/salty_site_map.png) *USGS survey sites.
UC Davis is marked with a red star.*

It is possible that this map is missing a few sites, but it was intended
to be exhaustive. It is complete enough that we can get a pretty good
sense of what the distribution of sites might look like within this
region; they are basically coincident with mountain ranges. Even though
they aren't depicted, the Coastal Range, the Sierras, the Cascades and
the Rockies all stand out. This isn't surprising; salt lakes require
some sort of constraining geographic topology, or the natural drainage
would simply carry the salt into the ocean. Interestingly, hot springs
are also usually found in mountains (some of these sites are indeed hot
springs), but that has less to do with the mountains themselves as it
does with the processes that built them in the first place. To put it
more pithily, you find salt lakes where there are mountains, but you
find mountains where there are hot springs.

I can't help be intrigued by the fact that the two most charismatic
groups of extremophiles, thermophilic archaea and halophilic archaea,
are more often neighbors than not. These sorts of geographic
correlations ought to make any microbiologist think long and hard about
John Snow's [infamous pump
handle](http://en.wikipedia.org/wiki/1854_Broad_Street_cholera_outbreak)...
but let's set that aside for now.

Clearly, this is not a random distribution. In order to capture the
dispersal dynamics among these these sites, my sub-sample must at least
exhibit the same spectrum of pairwise distances. In log-linear scale,
here's what the spectrum of pairwise distances looks like :

![](http://vort.org/media/images/salty_site_distances.png) *The spectrum
of pairwise distances among sites, sorted by magnitude. Solid line
represents data, dashed line is a random distribution.*

The solid line is the spectrum of distances among every pair of sites in
the database, sorted from closest to farthest. The dashed line is the
spectrum of pairwise distances for sites distributed randomly over the
same geographic area. A successful sub-sample would have a pairwise
distance spectrum that closely matches the spectrum of the full
database.

Now, it would be very nice if I could write a little python script to
spit out representative sub-samples with a minimal number of sites.
However, there is a *reason* that previous studies have focused only on
*ad hoc* assemblages of sites: Getting permission to collect samples
from a particular site is *hard*.

Much to my relief, a fortunate conspiracy of the USGS database and the
mathematics of combinatorics renders this problem all but moot. If I
cannot get access to a particular site, I can systematically generate
lists of alternatives that yield the same spectrum of pairwise
distances. This is why the richness of this database turns out to be
crucially important; with a less complete database, the number of
acceptable alternatives would be severely curtailed.

So far, I have permission to collect samples at about a dozen sites, and
tentative permission (an invitation, but no paperwork yet) at several
more. By keeping an eye on the pairwise distribution spectra of various
sampling opportunities, I can make sure that I'm accurately capturing
the geographic distribution of halophile habitats.

Now, geographic distance isn't the only parameter of interest. The
second clause of Baas Becking's hypothesis predicts that differences in
selective regimes will lead to a species sorting effect on community
composition. This is interesting, but species sorting is not the process
we're trying to studying here. Thus, one of the considerations for
choosing sites is to minimize the physical and chemical differences
among the sub-sample. Once again, Doctors Mariner and Barnes have saved
the day; the USGS database is lavishly detailed. In most cases, it has
the chemistry nailed down to the isotope level.

### Aim 2 : Collect metadata and build metagenomes

At this point, I'm not exactly sure how many sites I will have to
sample, and so I need to be prepared for the possibility that I will
have to sample from a significant fraction of the sites in the database.
I think this is a fairly remote possibility, but I feel it is important
to be prepared nevertheless. To this end, I have developed three
technical solutions to minimize the time, effort and cost involved in
collecting samples, processing samples, and collecting metadata.

For collecting samples, I will use a battery powered bead mill to
disrupt the samples in the field, and a combined lysis and stabilization
buffer to preserve the DNA.

![](http://vort.org/media/images/zymo_processor.jpg)

In September, I had a chance to [try this out at Borax
Lake](http://vort.org/2011/10/01/borax-lake-sample-collection-and-processing/).
The Borax Lake area contains several sample sites from the database
within walking distance of one another; the lake itself, two solar salt
ponds, and about a dozen hot springs. I was able to collect and process
thirty five samples in about an hour; I only stopped because it was
getting dark, and I'd run out of things to sample. After DNA extraction
and quantification, the cost per sample was about five or six dollars.

In the worst-case scenario, I would have to create about six thousand
metagenomes (two thousand samples with three biological replicates
each). I do not anticipate having to do anywhere close to this many, but
I thought it was an interesting technical problem, and so [I solved
it](http://vort.org/2011/09/19/how-sequence-10000-metagenomes-3d-printer/).

Well, actually I just added some mechanization to a solution Epicentre
(now part of Illumina) marketed, and my lab-mates Aaron Darling and
Qingyi Zhang have refined into a dirt-cheap multiplexed sequencing
solution. The standard technique for building Illumina sequencing
libraries involves mechanically shearing the source DNA, ligating
barcode sequences and sequencing adapters to the fragments, mixing them
all together, and then doing size selection and cleanup. The first two
steps of this process are fairly tedious and expensive. As it turns out,
[Tn5
transposase](http://www.rcsb.org/pdb/explore/explore.do?structureId=1muh)
can be used to fragment the DNA and ligate the barcodes and adapters in
one easy digest. Qingyi is now growing liters of the stuff.

The trouble is that DNA extraction yields an unpredictable amount of
DNA, and the activity of Tn5 is sensitive to the concentration of target
DNA. So, before you can start the Tn5 digest, you have to dilute the raw
DNA to the right concentration, and aliquat the correct amount for the
reaction. This isn't a big deal if you have a dozen or two samples. If
you have thousands, the dilutions would quickly become the rate limiting
step. If I'm the one doing the dilutions, it becomes a show-stopper at
around 500 samples. I'm just not that good at pipetting.

The usual way of dealing with this problem is to use a liquid handling
robot. The trouble is, liquid handling robots are stupendously
expensive, yet many of them are agonizingly slow. They are also
miserable program, and the software tends to be closed source, buggy and
terrible. If you are
Glaxo-Welcome-Smithcline-Merc-Monsanto-General-Motors-Nabisco-Unilever,
and you are are hot on the trail of a cure for ennui, then it is
probably worth the trouble to deal with these damned machines. Happily,
I don't have to, because there is a perfectly reasonable, although
rather odd, solution: Use a 3D printer to print titer plates that have
well volumes calibrated for each dilution, and use a multichannel
pipetter.

![](http://vort.org/media/images/boxwell_model_500.png) \
 *Programmatically generated dilution plate CAD model*

Of course, if you are planning to 3D print things, it helps to have a 3D
printer and to know how to use it. So, I ordered a kit from
[Ultimaker](http://blog.ultimaker.com/).

![](http://vort.org/media/images/ultimaker_kit_on_bench.jpeg) \
 *The Ultimaker kit*

After three days of intense and highly entertaining fiddling around, I
managed to get the kit assembled. A few more days of experimentation
yielded my first successful prints (a couple of whistles). A few days
after that, I was starting my first attempts to build my calibrated
volume dilution plates.

![](http://vort.org/media/images/ultimaker_and_the_lins.jpeg) \
 *[Dawei Lin](https://twitter.com/#!/iGenomics) and his daughter waiting
for their whistle ([thing 1046](http://www.thingiverse.com/thing:1046))
to finish printing.*

Learning about 3D printing has been a bit of and adventure, but I've got
the basics down and I'm now refining the process. I've finished the
software that generates the calibrated dilution plate models, and I can
produce the models with *almost* perfect fidelity. I'm still working on
the last bug, which is closing the tiny gaps in the extruded plastic.
I've had some help from the Ultimaker community on this, particularly
from [Florian
Horsch](https://plus.google.com/116416453568555193309/posts).

<iframe width="500" height="315" src="http://www.youtube.com/embed/rSQotMDzsEw" frameborder="0" allowfullscreen></iframe>

Much to my embarrassment, the first (very lousy) prototype of my
calibrated volume dilution plate ended up on AggieTV. Fortunately, the
glare from outside made it look much more awesome than it actual was.

<iframe width="500" height="300" src="http://www.youtube.com/embed/VXb6_SGwiJw" frameborder="0" allowfullscreen></iframe>

As nice as it is to have a database of all of these wonderful
measurements, it is of course necessary to verify that conditions have
remained the same. Also, it may be important for understanding the
selective environment to have an idea of what the variability of some of
these parameters is like. Unfortunately, the devices that are normally
used for collecting this kind of data are... hilariously expensive. So,
I've designed a home-brew environmental data logger.

![](http://vort.org/media/images/data_logger_prototype.jpg) \
 *My prototype Arduino-based environmental data logger. This version has
a pH probe, Flash storage, and a Bluetooth interface.*

From the water, the data logger measures pH, dissolved oxygen,
oxidation/reduction potential, conductivity, and temperature. I may also
add a small weather station to record air temperature, precipitation,
wind speed and direction, and solar radiation. I doubt if all of these
parameters will be useful, but the additional instrumentation is not
very expensive, and if it would be very annoying to have to return to
each site to make additional measurements.

And speaking of returning to the sites; where there is cell phone
service, I will add a GSM modem to the datalogger (I like the
[LinkSprite SM5100B with SparkFun's GSM
shield](http://www.sparkfun.com/products/9607)), and transmit the data
to my server at UC Davis through an SMS gateway. This way, I won't have
to return to the site to have access to its environmental data.

### Aim 3 : Modeling and analysis

There are a [variety of
methods](http://www.citeulike.org/user/rneches/article/7894240) that
have been used for inferring dispersal from phylogeny, but my personal
favorite is probably the approach used by [Isabel Sanmart&iacute;n for modeling
dispersal of invertebrates among the Canary
Islands](http://www.citeulike.org/user/rneches/article/2386051).
Basically, they allowed each taxa to evolve its own DNA model, but
constrained by the requirement that they share a common dispersal model.
Then they did Markov Chain Monte Carlo (MCMC) sampling of the posterior
distributions of island model parameters (using [MrBayes
4.0](http://bioinformatics.oxfordjournals.org/content/19/12/1572.abstract)).

![](http://vort.org/media/images/gene_flow_graph.png)

One nifty thing I discovered about using MrBayes is that it can link
against the [BEAGLE library](http://code.google.com/p/beagle-lib/),
which can accelerate these calculations using GPU clusters.
Suspiciously, [Aaron Darling](http://secretmicrobe.org/) is [one of the
authors](http://sysbio.oxfordjournals.org/content/early/2011/09/29/sysbio.syr100.short).
Hmm. If you were looking for evidence that the Eisen Lab is a den of
Bayesians, this would be it.

### Epilogue : Lourens Baas Becking, the man verses the strawman

![](http://vort.org/media/images/baas_becking.jpg) \
 *Lourens Baas Becking*

Microbiologists have been taking potshots at the Baas Becking hypothesis
for a decade or two now, and I am no exception. I'm certainly hoping
that the study I've outlined here will be a fatal blow.

However, it's important to pause for a moment and recognize that in our
zeal for assaulting his hypothesis, we've been unfair to Baas Becking
himself. The hypothesis that carries his name is a *model*, and Baas
Becking himself fully understood that dispersal must play an important
role in community formation. That is to say, he understood perfectly
well that "*alles is overal: maar het milieu selecteert*" was not
literally true; it is only mostly true, and then only in the context of
the observational methodology available at the time. In 1934, in the
same book where he proposed his eponymous hypothesis, he observed that
there are some habitats that were ideally suited for one microbe or
another, and yet these microbes were not present. [He offered the
following
explanation](http://www.citeulike.org/user/rneches/article/10207829):
"There thus are rare and less rare microbes. Perhaps there are very rare
microbes, i.e., microbes whose possibility of dispersion is limited for
whatever reason."

Useful models are never "true" in the usual sense of the word (except
maybe quantum electrodynamics). Models like the Baas Becking hypothesis
provide us with an intellectual littoral zone; a place where the model
gives way, and something else rises up. As any naturalist knows, most of
the action happens at interfaces; land and sea, sea and air, sea and
mud, forest and prairie. The principle applies just as well to the
landscape of ideas. The limits of a model, especially one as sweeping as
Baas Becking's, provides a lot of cozy little tidal ponds for graduate
students to scuttle around in. If they're lucky, they can make a little
sortie onto the land without getting eaten by one of the abler denizens
of the tidal zone.

By the way, guess where Lourens Baas Becking first developed his
hypothesis? He was here in California, studying the halopiles of the
local salt lakes. In fact, the very ones I will be studying.
