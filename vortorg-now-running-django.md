Title: Vort.org now running on Django
Date: 2008-03-27 00:53:25
Category: general
Slug: vortorg-now-running-django
Author: Russell Neches
Tags: code, python
Summary: 


For the last couple of years, I've been running
[Typo](http://www.typosphere.org/), a [Ruby on
Rails](http://www.rubyonrails.org/) blogging tool. It was nice, but
there were a few persistent problems I encountered :

-   It was *sloooooow*. Nothing I did seemed to get it to run faster,
    even with carefully tuned caching.
-   It was unstable. Typo would run happily for months, and then
    mysteriously explode. This usually happened while I was traveling,
    or busy with something more important.
-   It was difficult to fix. Usually, when Typo would come down, it took
    a few days of research and pestering people to figure out why.
-   The database migrations between versions were awful. You'll notice
    that the first year of posts don't have any tags. They were deleted
    by a bad migration. I have backups, but merging them back in is
    nightmarish.

A lot of the problems I experienced are with older versions of Typo.
They've definitely gotten better over the years. But there is one big
reason I'm abandoning Typo; I don't want to code in Ruby. I do most of
my coding in python. I like python. I seems silly not to use the
knowledge I have from doing computational physics in python.

I have used [Blogmaker](http://code.google.com/p/blogmaker/) for most of
the main elements on my site, but with a fair bit of hacking to make it
do more of what I want. I also wrote a Typo-to-Django import utility, if
anyone is interested. The URLs are slightly different, so I'm going to
watch the 404s for a few days.
