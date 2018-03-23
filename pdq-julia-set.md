Title: PDQ Julia Set
Date: 2007-03-29 21:01:49
Category: general
Slug: pdq-julia-set
Author: Russell Neches
Tags: 
Summary: 


I was up late last night while waiting for the laundry to finish drying,
and was annoyed at myself for wasting time fooling around on the
internet. So, I decided to try to remember how to plot the Julia set. I
vaguely remember doing this in high school, so I turned off my wireless
card (so I couldn't cheat) and timed myself to see how long it would
take me to figure it out.

![](http://vort.org/media/images/julia.png)

After 11 minutes I got this. Not bad. It's not the most efficient way of
plotting it, and I didn't bother to use modular arithmetic to handle big
numbers (that's why I only go to six iterations). Here is my (very
stupid) Julia set calculator.

    #!/usr/bin/env python
    # vim: set ts=4 sw=4 et:
    from numpy import *
    from scipy import *
    from pylab import *
    
    def julia( l, I, M ) :
        a = zeros( (I,I), Float64 )
        for i in range(I) :
            for j in range(I) :
                N = complex(-2.0+i/(0.25*I),-2.0+j/(0.25*I))
                for m in range(M) :
                    try :
                        N = (N)**2+l
                    except OverflowError :
                        N = 10000000000.0
                        break
                a[i,j] = abs(N)
        return a
    
    l = complex( 0.4, 0.3 )
    a = julia( l, 200, 6)
    contourf( log(a), 32 )
    colorbar()
    #contour( a, [1], colors='black' )
    show()
