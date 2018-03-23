Title: Journals are the problem and the solution
Date: 2012-11-15 08:46:58
Category: general
Slug: journals-are-problem-and-solution
Author: Russell Neches
Tags: software, science, research
Summary: 


Titus wrote [an interesting post
yesterday](http://ivory.idyll.org/blog/w4s-overview.html) about
addressing some of what I'll call structural problems in scientific
research.

> This is one of a bunch of posts on what I'm calling 'w4s' -- using the
> Web, and principles of the Web, to improve science. The others are:
> <ul>
> <li>
> The awesomeness we're experiencing, which provides some examples of
> current awesomeness in this area.
> </li>
> <li>
> The challenges ahead, which covers some of the reasons why academia
> isn't moving very fast in this area.
> </li>
> <li>
> Strategizing for the future, which talks about technical strategies
> and approaches for helping change things.
> </li>
> <li>
> Tech wanted!, which gives some specific enabling technologies that I
> think are fairly easy to implement.
> </li>
> <ul>

He goes on to throw some well-aimed brickbats at the system of
publishing and grant reviewing, and how that plays out for researchers
who actually do things other than crank out traditional research papers
:

> As an increasing amount of effort is put towards generating data sets
> and correlating across data sets, funding agencies are certainly
> trying to figure out how to reward such effort. The NSF is now
> explicitly allowing software and databases in the personnel
> BioSketches, for example, which is a great advance. Surely this is
> driving change?
>
> The obstacle, unfortunately, may be the peer reviewer system. Most
> grants and papers are peer reviewed, and "peers" in this case include
> lots of professors that venerate PDFs and two-significant-digit Impact
> Factors. Moreover, many reviewers value theory over practice --
> Fernando Perez has repeatedly ranted to me about his experience on
> serving on review panels for capacity-building cyberinfrastructure
> grants where most of the reviewers pay no attention whatsoever to the
> plans for software or data release, and even poo-poo those that have
> explicit plans. And if a grant gets trashed by the reviewers, it's
> very hard for the program manager to override that. The same thing
> occurs with software, where openness and replicability don't figure
> into the review much. So there's a big problem in getting grants and
> papers if you're distracting yourself by trying to be useful in
> addition to addressing novelty, impact, etc.
>
> <p>
> The career implications are that if you're stupid enough to make
> useful software and spend your time releasing useful data rather than
> writing papers, you can expect to be sidelined academically -- either
> because you won't get job offers, or because you won't get grants when
> you do have a job.

I propose a simple solution : Start better journals.

The fundamental unit of exchange in the academic reputation economy is
the publication. At the moment, it is very hard to publish things that
are not "normal" research papers. PLOS ONE has helped by shifting the
review criteria towards correctness and leaving judgement of novelty to
the community. However, PLOS ONE is still nevertheless an awkward place
to publish a piece of software, for example.

Tool builders are expected to produce three publications for every one
research result. First they have to design, assemble, test and publish
the tool. Then they have to write a paper about the tool. Then they have
to document the tool. After that, they are expected to release updates,
patches and improvements. The only one of these items that "counts" in
the academic sense is the one that generates a DOI number -- the paper.
This is usually the least valuable of all the things produced. Honestly,
how many of you BLAST users have actually *read* [the BLAST
paper](http://nar.oxfordjournals.org/content/25/17/3389.long)?

What is needed are journals that let you publish things that aren't
strictly papers. It seems perfectly reasonable that a panel of peers
should be able review software on my GitHub account and bestow a DOI
number on a tag they feel meets the criteria set by the editorial board
that badgered them into participating in the review. It seems perfectly
reasonable that when I cut a major update of the software, I might
submit it for review. This would be extremely wonderful, as it would
lead to reviews and critiques **the code itself**, which almost never
happens when one submits an application note.

The same should apply to tool documentation. Science suffers a great
deal because documentation is missing, poor, or out of date. The
**only** way to fix that is to let tool builders have their tool
documentation reviewed and published. Perhaps some journals might review
code only, others documentation only, and others code and documentation
together. The same goes for updates. If you want academics to do
something, you have to provide rewards in the currency of academia.

It is also important not to overlook things beyond software. What about
people building methods and protocols? There are already journals that
publish methods papers, but a lot more could be done to make these
publications more useful. [JoVE](http://www.jove.com/), the Journal of
Visualized Experiments, is a pretty interesting step in that direction,
but much much more needs to be done. Most scientists have no experience
whatsoever in video production, narration, editing, or any of the skills
needed to make a really good JoVE publication.

There is also another big gap in instrumentation and hardware. Every
really productive laboratory has at least one person who builds things.
For example, at the UC Davis Genome Center perhaps a third of all the
science we publish involve some gizmo built by our [in-house machinist
Steve Lucero](http://www.bme.ucdavis.edu/teamprototyping/). Steve is
definitely what I would regard as a practicing researcher, and has been
(ahem) instrumental in a number of important publications. Nevertheless,
he was invited to be an author on his first publication only this year.
By a graduate student. I don't think this is particularly malicious on
the part of the laboratories that use his creations in their work. The
problem is that there isn't really a good venue for publishing *things*.

Booting up new kinds of journals is a long-term endeavor. PLOS ONE is
still struggling for acceptability in many circles. Nevertheless,
getting researchers to actually *look* at each others' code would yield
rewards in the short term while we wait for the resulting DOIs to be
appreciated by the broader scientific community.
