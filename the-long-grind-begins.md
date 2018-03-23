Title: The long grind begins
Date: 2006-09-09 17:15:41
Category: general
Slug: the-long-grind-begins
Author: Russell Neches
Tags: code, science
Summary: 


Sometimes, I'm really amazed that people are able to accomplish anything
in computational science. It has turned out to be nearly impossible to
package up [Scipy](http://scipy.org) in a way that I can distribute to
people running, for example, Fedora or MacOS. It's not fair to ask
people like my mom to install g77 and start debugging build options just
to run the Ophidian client. Scipy is damn-near impossible to compile, so
building it as an egg also damn-near impossible. With only four nodes
working on my problem, at least I'll have plenty of time to figure it
out.

Dependency issues notwithstanding, I finally have a (hopefully)
distributable version of Ophidian. I'm going to make sure it gets
through the first case before giving the client out to people. So far,
here is the work:

![](http://vort.org/media/images/ophidian_partial.png)

Aside from a few dropped blocks, it looks like it's pretty much
glitch-free. There are a few points on the outboard midplane that I'll
have to go back andhere is the work manually recompute, but that
shouldn't be too bad.
