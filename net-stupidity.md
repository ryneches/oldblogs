Title: Net Stupidity
Date: 2006-04-25 07:36:00
Category: general
Slug: net-stupidity
Author: Russell Neches
Tags: 
Summary: 


"It's not about the customer, you see, it's about their profits," Kossak
mcjoan [argues](http://www.dailykos.com/storyonly/2006/4/24/201526/948).
That couldn't be more correct, though probably not in the way it was
meant.

You see, I am an AT&T shareholder. I'm also a Comcast shareholder. I am
*very* interested in the profits of these companies. I want them to make
great steaming heaps of money because this will become *my* money.
That's why I think it's absolutely essential to preserve network
neutrality.

Why, you might ask? Won't AT&T and Comcast make more money if they can
charge Google to access their customers? Sadly, No! (apologies to
Seabas, Brad and Gavin)

The value of a network is not simply the cost of of the equipment in it.
To understand what a network is worth, and thus what you can charge
people for the privilege of using it, we're going to have to dip into
utility theory.

Before we get into that, fathom a few simple facts:

-   A single telephone is utterly worthless.
-   A heap of telephones and wires in a sack is worthless.
-   A telephone network that connects people who hate each other is
    worthless.

Utility theory isn't state of the art economics, but because networks
are complex objects, utility theory is really the only place to start.
It's easy to see how, for example, a cup of coffee or a banana or a
back-massage is valuable. When you have one, you're happier. Utility
theory allows you to very formally rank your preferences among choices
by assigning each choice a certain number of "utils" (yes, they really
call them that). You can then attempt to find the best choice by
maximizing the number of utils with the right choice.

It's easy to see that a hypothetical person might be happier with a
banana, a cup of coffee and a back massage than they would be with two
of the three, or with none. Now, say this person is not a morning
person, but is nevertheless awake in the morning. A cup of coffee and a
back massage might be a lot more valuable to them than a banana and a
back massage. Now say you have a bunch of each item (just pretend a back
massage is an "item"), and a bunch of people. Some people might have
different preferences, and thus different utility functions -- say your
group includes a diabetic, a Mormon, and guy with a really bad sunburn.
There should be some way of distributing the items such that the total
utility is maximized.

So, how happy will you be with one network verses another?

Say we have a very simple telephone network. You pick up the phone, you
dial a number, and someone else on the network picks up. You talk about
something interesting, and then hang up. What's that worth?

If you're the only person on the network (there's only one phone), the
utility of the network is zero. You can talk to yourself without a
telephone for free. If you need to talk to yourself, then perhaps the
novelty of adding a telephone to mix might be of some interest to you,
but let's just pretend you don't talk to yourself on the phone.

If there is one other person on the network, then the network earns one
util by allowing you to call that person. As you add people to the
network, the value increases with the number of people you can call.
However, you aren't the only person on the network, of course, so the
network has the same utility for every other person on the network too.

![ [[image from WikiPedia]](http://en.wikipedia.org/wiki/Image:Network_effect.png) ](http://vort.org/media/images/Network_effect.png) 

The utility function of the network scales with the square of the number
of users, but to make sure our function is zero when we've only got one
user:

$$U(n) = \frac{n ( n - 1 )}{2}$$

This is called Metcalfe's Law.

Now the Internet isn't like the telephone network. You can do a lot more
than simply call one other person at a time. You can read news from news
sites, talk with twenty-three of your friends on Instant Messenger, make
a VoIP call, post some trollish comments on some blogs, check your
personal email, your work email, your email from your college account,
and the email account you gave to that cute so-and-so at the bar the
other day, upload photos to your photo gallery, download viruses and
spy-ware that will slowly cripple your computer (automatically!), leech
music from 300 strangers, download the latest episode of West Wing from
your mom's TiVo, stream NPR, and fill your iPod with a podcast of
someone screaming incoherently in German. *And you can do it all at
once.*

Clearly, such a network has a lot more utility than our simple telephone
network. The Internet is about groups of people communicating, not pairs
of people. So, we need a new utility function that captures this. The
utility function for a network like the Internet is:

$$U(n) = 2^n - n - 1$$

This is called Reed's Law, after David P. Reed. Reed helped design
TCP/IP.

Indeed, Reed's law may even be an underestimate of the utility because
it doesn't take into account the fact that the Internet is simply a
bit-moving mechanism, and that the real services people use, which
usually follow Reed's Law, run on top of it. It's really an ur-network,
and we can build whatever we want on top of it.

However, there is an underlying assumption in both of these models: That
any user can connect to any other user, without preference or penalty.
Reed's Law and Metcalfe's Law are ideal cases in which the network is
utterly agnostic about who connects to who. The ideal cases have the
maximum utility, and the less ideal they are, the less utility.

In the case of a telephone network governed by Metcalfe's Law, the
non-ideal behavior might be that calls to more distant users cost extra.
This may seem somehow more "fair," but the simple fact is that it
reduces the value of the network over all. There is a very, very good
reason cell phone companies often offer free long distance.

The scaling of Reed's Law suggests that networks that reflect this model
would be extremely sensitive to violating the connection-agnostic
assumption. Indeed, that stands to reason. If you suddenly find out that
you have to pay extra to use Google, you're not allowed to make VoIP
calls, advertisement agents will join your private IM conversations to
push their wares, that your friends on other networks have to pay per
message to send email to you, and that a random smattering of sites are
mysteriously blocked, then your network connection isn't going to be
worth very much to you, is it?

Indeed not. How many such restrictions and penalties would it take for
you to regard your connection as significantly less valuable? Probably
not very many. And if people regard the connections as less valuable,
what will happen to the price they're willing to pay?

The existence of the Internet has added trillions of dollars of value to
the world economy. AT&T and Comcast are asking Congress for permission
to slash the value of their own capital investments. They aren't being
greedy. For God's sake, please, yes! Let them be greedy! Let them
squeeze every last goddamn penny from their network assets!

This is the point where the the Left gets things wrong. Yes, sometimes
greed is a vice, but sometimes it is a virtue. It is profoundly dumb to
cast the net-neutrality debate in terms of greedy network operators
versus virtuous Google, eBay and their own (always virtuous) customers.
If it were really true, then of *course* they should try to collect as
much money as possible. But that's not what's going on here, and it's
not why people are upset. People aren't upset because they're going to
get charged more; they're upset because this will wreck the value of the
single most valuable technological and cultural asset on the planet.

AT&T, Comcast, Verizon and Time Warner are not being greedy. They are
being idiots.
