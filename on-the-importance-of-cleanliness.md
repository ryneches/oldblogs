Title: On the Importance of Cleanliness
Date: 2007-05-20 18:15:32
Category: general
Slug: on-the-importance-of-cleanliness
Author: Russell Neches
Tags: cpu, heat, electricity
Summary: 


As we all know, dust kills computers. It clogs up the fans and mucks up
their bearings. Eventually they begin to emit an annoying grinding or
mooing noise. Even if the racket is tolerated, eventually the computer
will stop working.

But even a relatively clean computer suffers from dust. You don't need
giant dust bunnies clogging your CPU fan to see a significant impact on
its cooling effectiveness. The thin, translucent coating of dust that
settles onto anything after a few weeks is actually a pretty good
insulator. It's like wrapping your heat sync in thermal underwear.

Here is what happens when you clean off that thin little layer of dust:

![](http://vort.org/media/images/CPU_clean.png)

I have the polling rate for the temperature set at 1/20 Hz, so this is
actually a significant length of time. I mention this to demonstrate
that the temperature drop wasn't caused by the compressed air.

It's also worth noting that the hotter a semiconductor (or, in most
cases, an ordinary conductor) gets, the higher its resistance. The
increased overall resistance will cause larger voltage drops within the
gate logic. Semiconductors require a minimum voltage to work reliably.
So, you have two options; raise the supply voltage, thus dissipating
more power, or run the risk of the voltage dropping too low somewhere in
the gate logic, thus causing a logic fault. Either way, it's bad.

If the machine adjusts the supply voltage to avoid a logic fault, the
part will get hotter, causing its resistance to go up even more, which
requires another increase in supply voltage. One hopes that the cycle
damps out before it runs away and the part explodes. So, even a
relatively small improvement in heat dissipation can lower the
temperature significantly due to this compounding effect.

So, boys and girls, remember to keep your computer clean. It will run
cooler, last longer, and use less electricity.
