Title: Vort.org... now with more math!
Date: 2007-04-13 05:03:41
Category: general
Slug: vort-org-now-with-more-math
Author: Russell Neches
Tags: internet, math
Summary: 


Back when Tim Berners-Lee and Robert Cailliau brought forth the World
Wide Web, the idea was to create an easier way for researchers to
discuss and share their work. For reasons I've never really understood,
through many revisions, the specification for web layout has never
included a good way of writing mathematics. Now there is this
[MathML](http://www.w3.org/Math/) thing that we are supposed to use. It
is only now starting to seep into the default configurations of most
browsers. Sadly, it ignores the fact that there is *already* a perfectly
wonderful and truly elegant [markup language for typesetting
mathematics](http://en.wikipedia.org/wiki/LaTeX).

So, until MathML takes over the world, or is replaced by something that
people might actually want to use, there is a fantastic little program
called [mimeTeX](http://www.forkosh.com/mimetex.html). Once it is
happily nestled in your cgi-bin directory (remember CGI?), mimeTeX will
burble forth all the equations you could ever want. You just pass it a
string of LaTeX math mode in as a query, and out pops beautiful
equations:

$$
         \left(\large\begin{array}{GC+23}
         \varepsilon_x\\\varepsilon_y\\\varepsilon_z\\\gamma_{xy}\\
         \gamma_{xz}\\\gamma_{yz}\end{array}\right)\ {\Large=}
         \ \left[\begin{array}{CC}
         \begin{array}\frac1{E_{\fs{+1}x}}
         &-\frac{\nu_{xy}}{E_{\fs{+1}x}}
         &-\frac{\nu_{\fs{+1}xz}}{E_{\fs{+1}x}}\\
         -\frac{\nu_{yx}}{E_y}&\frac1{E_{y}}&-\frac{\nu_{yz}}{E_y}\\
         -\frac{\nu_{\fs{+1}zx}}{E_{\fs{+1}z}}&
         -\frac{\nu_{zy}}{E_{\fs{+1}z}}
         &\frac1{E_{\fs{+1}z}}\end{array} & {\LARGE 0} \\
         {\LARGE 0} & \begin{array}\frac1{G_{xy}}&&\\
         &\frac1{G_{\fs{+1}xz}}&\\&&\frac1{G_{yz}}\end{array}
         \end{array}\right]
         \ \left(\large\begin{array}
         \sigma_x\\\sigma_y\\\sigma_z\\\tau_{xy}\\\tau_{xz}\\\tau_{yz}
         \end{array}\right)
$$

It's not the solution that would make the most sense -- a LaTeX engine
on the client-side -- but it's the next best thing. So go ahead and blog
about math, and stop writing stupid things like f(x-a)/sigma\_thingy.

Oh, and if you are too lazy to install it yourself, I warn you now not
to use mine. I will use url\_rewrite to introduce embarrassing mistakes
into your posts.

**Update, October 26, 2012** : I've scrapped this whole thing in favor
of [MathJax](http://www.mathjax.org/), which, I am pleased to say, I
hoped would happen. Only took six years!
