Title: SmartMeter data from PG&E
Date: 2009-10-05 01:00:03
Category: general
Slug: smart-meter-data-pge
Author: Russell Neches
Tags: davis, google
Summary: 


PG&E is no angel, but it deserves credit for making what looks like a
good-faith effort to get California off of carbon. It's serious enough
to have [quit the US Chamber of
Commerce](http://www.nytimes.com/gwire/2009/09/25/25greenwire-another-utility-leaves-us-chamber-over-climate-2910.html)
to distance itself from the group's extremist views on climate change.

PG&E still owns six coal burning power plants, curiously located in
Florida, New Jersey and Pennsylvania (presumably it uses them to swap
power with other generators). It generates about 46% of its electricity
from hydroelectric dams.

![Rucker Creek dam, a small PG&E facility in Nevada County](http://vort.org/media/images/rucker_creek.jpg)

One of the more interesting projects PG&E is undertaking is improving
the resolution of its demand monitoring using SmartMeters. There is a
lot of hype about the "Smart Grid," but basically it boils down to
realtime use monitors, like these :

![](http://vort.org/media/images/kill-a-watt-power-meter.jpg)

that are wired up to report the data somewhere. It's basically an
off-the-shelf [Tweet-A-Watt](http://www.ladyada.net/make/tweetawatt/).

According to the PG&E web site, they are using SmartSynch meters, which
use TCP/IP over some kind of wireless network. It's difficult to find
information about the hardware itself, probably on account of the
[assorted
idiots](http://billmullins.wordpress.com/2009/09/04/smart-meters-make-us-dumb/)
wetting their pants about people h4X0ring their refrigerators (actually,
I don't know if Bill Mullins is an idiot, but his article about smart
meters is depressingly typical).

Yes, it is possible for a bad person to break into your PG&E account to
obtain this data.^1^ But so what? Power meters are inductively coupled
to the circuit they measure. They can look, but they cannot touch.
IOActive, a security research firm, claims that they can break into
certain smart meters and "cut off power." I suppose we are meant to
construe this as "cut off power to the house," but that isn't what power
meters do. That is what those huge knife switches, with the
lock-out-tag-out rings, are for. I'm skeptical that a certified
electrician would work on a residential circuit with a computer
controlled on-off switch. I certainly wouldn't. What "cut off power"
probably means is that they can shut down the microcontroller, and stop
the meter from collecting or reporting data. We're left to speculate,
though, because the report is confidential. I speculate that they are
hyping a buffer overflow exploit to gain as much attention as possible.

Nobody is going to h4x0r your refrigerator and reprogram it to be an *E.
coli* chemostat. If you are worried about your personal data floating
around on the big bad internets, your worries are better directed at
your bank and your health insurance provider. The bad guys don't care
that you left your bathroom light on all night last Thursday; they just
want the routing number for your savings account.

While the data isn't very valuable for nefarious purposes, it is
extremely valuable in the noble (if mundane) pursuit of frugality.
Here's what PG&E shows you if you've been upgraded to a smart meter :

![](http://vort.org/media/images/weekly_pge.png)

Having the graphs is neat, but the usability of the site is poor.
Fortunately, they let you download the data as CSV files, although you
have to go a week at a time. It's all very 1995. Happily, Google.org is
working on a real-time data browser tool called [Power
Meter](http://www.google.org/powermeter/) which will make this a lot
nicer. For now, I just wish I had an XML-RPC interface.

![](http://vort.org/media/images/daily_pge.png)

I've already learned something from this data. On the 29th and 30th, I
was at the Granlibakken conference center for the UC Davis Host Microbe
Interaction conference. Those days show dramatically less power use
between about 22:00 and 2:00, which is when I'm usually hacking at my
desktop machine. One more reason to start thinking about replacing this
behemoth.

1. Actually, it's stupidly easy to gain access to someone's PG&E
account if you have their account number. Just create a new web account,
type in the account number, and there you go! Now you can really fuck
with them by *paying their bill*, which is about all you can do with a
PG&E account.
