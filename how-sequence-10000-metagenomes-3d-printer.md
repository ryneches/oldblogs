Title: How to sequence 10,000 metagenomes with a 3D printer
Date: 2011-09-19 01:15:00
Category: general
Slug: how-sequence-10000-metagenomes-3d-printer
Author: Russell Neches
Tags: science, grad, school, davis, eisenlab, metagenomics, research, genomics
Summary: 


For my thesis project, one of the things I would like to do is sequence
many different samples, perhaps on the order of several hundred or
thousand. It's easy enough to build sequencing libraries these days, at
least, with Illumina, anyway. Obviously, doing a couple of hundred lanes
of Illumina sequencing would be ridiculous (not even Jonathan Eisen is
that nice to his graduate students), and so I'll be using several
barcoded samples pooled into each lane. The barcoding chemistry itself
was fairly tedious, until people starting doing
[transposon](http://en.wikipedia.org/wiki/Transposon)-based library
construction.

A [transposon](http://www.pdb.org/pdb/101/motm.do?momID=84) is a little
piece of DNA that copies itself around inside the genome of an organism,
via an enzyme called transposase. Here's what the genetic element looks
like :

![](http://vort.org/media/images/transposon_gene.png)

Transposase binds the element at the inverted repeats on either end, and
coils it into a loop. Then it cuts the DNA at the inverted repeats, and
the complex floats away. It leaves complementary overhanging ends in the
chromosome, which are usually repaired by DNA polymerase and DNA ligase
(DNA gets broken surprisingly frequently in the normal workaday life of
a cell; that's why DNA repair mechanisms are so important). When it's
complexed to DNA, transposase grabs the DNA like this :

![](http://vort.org/media/images/Tn5_transposon.jpg)

The transposase we're using
([Tn5](http://www.rcsb.org/pdb/explore/explore.do?structureId=1muh)) is
a homodimer; the two subunits are in dark and light blue. The inverted
repeats (red) are bound to the complex at the interfaces between the
subunits. The pink loop is the DNA that gets cut and pasted.

The complex then floats around in the cell until the transposase
recognizes an integration site somewhere else in the genome. It then
cleaves the DNA and inserts the payload into the break. DNA ligase then
comes along and fixes the backbones. You can see why this kind of
transposon is also called a cut-and-paste transposon.

The reason these are interesting for library construction is that you
can prepare a transposon complex where the loop of payload DNA is
broken. When the transposon integrates, it pastes in a gap. If you add a
lot of transposons that aren't too choosy about their binding sits, they
will chop up your target DNA. Fragmentation is one of the steps needed
for sequencing library construction. What's nice about transposons is
that when you use them to chop up your target DNA, they leave the two
halves of their payload stuck onto the ends.

![](http://vort.org/media/images/Tn5_transposon_tagmentation.jpg)

If you stuck your sequencing adapters on there, the fragmentation
process also includes adapter ligation. If you added barcodes along with
the sequencing adapters, the reaction combines almost all of the library
construction into a single digest. Epicentre whimsically named this
process
"[tagmentation](http://www.epibio.com/nextera/nextera_tech_overview.asp)."
Get it?

However, there's still a fly in this ointment. The distribution of
transposon insertions is a function of the relative concentrations of
charged transposon complexes to target DNA, and DNA extraction, even
from seemingly identical samples, can have highly variable yields. So,
it's very important to control the input concentrations and reaction
volumes during the digest. This is fairly easy if you're only making a
dozen or so libraries, but what if you want to make ten thousand of
them?

Measuring DNA concentrations of lots of samples is relatively easy, and
there are lots of ways of doing it. We have a plate reader that can do
this by florescence on titer plates with 1534 wells, or we could (ab)use
the qPCR machine to give us DNA concentrations on 384 well titer plates.
There are other ways, too.

However you quantify the DNA concentrations, you have to dilute each
sample to the desired concentration before you can start the
tagmentation process. If you get the concentrations wrong, the library
comes out funny.

A few dozen library constructions calls for hours of tedious work at the
bench. I've gotten better at wetlab stuff since my [first
rotation](http://vort.org/2009/10/19/cloning-blues/), and the
transposon-based library construction helps a lot, but staking my Ph.D.
on reliably powering through lots of molecular biology would be a bad
idea. Some people might not blink an eye at this, but as soon as I find
myself repeating something four or five times, my computer science
upbringing starts whispering *there has got to be a better way* in my
ear. And lo, there is indeed a better way.

Hundreds or thousands of library constructions would call for a robotic
liquid handling machine. I spent some time researching these things, and
I'm not impressed. The hardware is nice, but programming the protocols
involves wading into a morass of crumbling, poorly maintained closed
source software, expensive vendor support contracts, and a lot of
debugging and down-time. Oh, and they're terrifyingly expensive, and can
be kind of dangerous.

Dispensing water into titer plates doesn't seem like a very challenging
robotics application, so I thought about building my own robot. It would
probably be about the same amount of work as ordering, programming and
debugging one of the commercial robots, and it would be more fun.

But, robots are just such a *mainframe-ish* solution. If there is [one
thing my dad taught me](http://thesis.library.caltech.edu/3087/), it's
that a lot of little machines working in concert will beat the stuffing
out of a single big machine. The trick is figuring out how to organize
and coordinate lots of little machines. The key to this problem is to do
lots and lots of little reactions in parallel; the coordination requires
lots of precise dilutions simultaneously. Getting this part right would
crack the whole thing wide open, allowing you to easily do more
reactions than you probably even want.

So. I'm going to make my own custom microtiter plates, just for the
dilution. This satisfies the coordination criteria, and allows me to
treat a plate-load of reactions identically. If each well has the right
volume for the dilution, I can just fill all the wells up to the top,
pipette in the same volume of raw DNA with a multichannel pipetter, let
the DNA mix a little, and all the wells will be at equal concentration.
Then I pipette that into the tagmentation reaction, and I'm done. With a
good multichannel pipetter, I can do 384 reactions about as easily as I
could do one.

All that's necessary is a 3D printer, and the ability to procedurally
generate CAD/CAM files from the measured DNA concentrations. As it
happens, this is really easy, thanks to a little Python library called
[SolidPython](https://github.com/SolidCode/SolidPython) :

![](http://vort.org/media/images/dilution_plate_model.png)

These are the wells of a 96-well plate with randomly chosen volumes for
reach well.

One of the things I'm worried about is contamination. 3D printers are
not really designed for making sterile parts. So, what I've done here is
design a mold, and I'm going to cast the plate itself in [PDMS silicone
elastomer](http://en.wikipedia.org/wiki/Polydimethylsiloxane). PDMS is
easy to cast, and it has the nice property of being extremely durable
once it's set. And, even better, when exposed to UV, the surface
depolymerizes and turns into, essentially, ordinary glass. I can
autoclave the heck out if it, blast it with UV, and indulge in all
manner of molecular paranoia.

If I can figure out a way to reliably sterilize thermoplastic, I'll skip
the business with the PDMS casting, and simply print microtiter plates
directly, like this :

![](http://vort.org/media/images/96_well_plate.png)

By the way, I used the dimensions of a [Corning round-bottom 96 well
microplate](http://catalog2.corning.com/lifesciences/media/equipment_compatibility/MD_Microplate_Dimension_Sheets_96_Well.pdf).
You can download the model from [my account on
Thingiverse](http://www.thingiverse.com/ryneches).

So, I ordered a personal 3D printer. It looks like the hottest Open
Source personal 3D printer right now, and the only one with a build
volume larger than a titer plate, is the
[Ultimaker](http://blog.ultimaker.com/). I'd have really liked to have
gone with MakerBot Industries'
[Thing-o-Matic](http://store.makerbot.com/makerbot-thing-o-matic.html),
but the build volume is just a scoche too small. Come on, guys! Just a
few more millimeters? Please?

Unfortunately, the Ultimaker has a four to six week lead time, so I have
to wait for a while before ours arrives. At the suggestion of [Ian
Holmes](http://bioeng.berkeley.edu/cv/iholmes.php), I headed off to
[Noisebridge](https://www.noisebridge.net/wiki/Noisebridge), a
hackerspace in the San Francisco's Mission District where they have a
couple of 3D printers available for people to use. The machines are
[Cupcake CNC's](http://www.makerbot.com/blog/tag/cupcake-cnc/),
MakerBot's first kit. The ones at Noisebridge are... well, let's just
say they are well-loved. The one I used had to be re-calibrated before
it would go. 3D printers are pretty straightforward machines when it
comes down to it, so it only took me a couple of minutes of poking
around at it to figure out how to make the right adjustments. Then, it
worked like a charm!

![](http://vort.org/media/images/3D_printing_at_noisebridge.jpg)

As you can see, I was a bit conservative about the design, since I
wasn't sure how good the print quality would be (especially after my
cack-handed ministrations).

![](http://vort.org/media/images/first_3D_print.jpg)

I'm experimenting with PDMS casting now, but I'm going try some tests to
see how thoroughly I can clean thermoplastic with UV. I'd really like to
just order up a nice 384 well plate, and get right to it!

![](http://vort.org/media/images/384_well.png)

Anyway, I need to thank (or perhaps blame) [Aaron
Darling](http://secretmicrobe.org/) for getting me interested in
transposon-based library construction, and for pointing out their
significance to me.
