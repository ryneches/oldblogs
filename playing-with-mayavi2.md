Title: Playing with MayaVi2
Date: 2006-12-06 21:20:13
Category: general
Slug: playing-with-mayavi2
Author: Russell Neches
Tags: science, math, code
Summary: 


I've been looking for a good 3D plotting tool that can, in some way, be
coaxed into a healthy relationship with python. Actually, I'd settle for
anything, really. All I really want is the ability to easily embed
points and surfaces into a volume, and then be able to apply some basic
manipulations (rotation, translation and zoom). What I'd really like is
to have an interface that would work something like this :

    import scipy
    import plot3d
    plotter = plot3d()
    
    plot = plotter( title="I'm a plot!" )
    plot.point( 1.0, -0.5, 1.25 )
    plot.point( 0.25, -1.5, -1.25 )
    
    def f( x, y ) :
        return scipy.sin(x) + scipy.sin(y)
    
    xx = arange( -1.0, 1.0, 0.01 )
    yy = arange( -1.0, 1.0, 0.01 )
    
    plot.func( xx, yy, f )
    
    plot.show()
    
    plot.save( filetype='png', 'image.png' )

The output doesn't have to be accelerated, although that would be nice.
The important thing is producing tolerably good images. Well, the
closest thing that I can find is MayaVi2. I would include a link to it,
but the site (sites?) is/are confusing enough that I can't even guess
where to point the link. You will do no worse than me with a Google
search. Clearly, something interesting is going on, but it's not
altogether clear what.

Anyway, by checking out a staggeringly large amount of code and
following the relatively simple build instructions, here is what the
output looks like :

[![](http://vort.org/media/images/tokamak_data_mayavi2_400px.png)](http://vort.org/media/images/tokamak_data_mayavi2.png)

Evidently, the thing I actually want is called mlab, which sort of
emulates the 3D plotting available in MatLab. The idea is rather like
the pylab API of the fantastic [matplotlib](http://matplotlib.sf.net)
package, but for 3D. The rest of the code appears to be some kind of
huge visualization framework, like [OpenDX](http://www.opendx.org/)
rebuilt in wxPython with similar intentions and a completely different
design.

There are some rendering bugs that are probably the fault of my graphics
driver, and the visualization system itself is bewildering and
semi-working. The mlab module only seems to work correctly when called
from the python console embedded in the MayaVi2 GUI, and even then
segfaults when certain other modules are loaded (e.g., matplotlib).
Also, the snapshot feature is completely broken, and will either crash
or write a file full of garbage (the image above is screen capture via
X.org). Maybe I will appreciate it more when it works a little better,
but for the moment, I would be happy if someone kidnapped mlab and moved
it into the matplotlib family of tools.

I will have to play with this some more. It has a lot of promise if I
can get around some of the bugs.
