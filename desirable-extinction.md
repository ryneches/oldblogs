Title: A desirable extinction
Date: 2010-03-25 15:19:52
Category: general
Slug: desirable-extinction
Author: Russell Neches
Tags: bugs, math, plotting, science, python, grad, school, davis, life
Summary: 


Some weeks ago, Buzz (my cat) escaped out my front door while I was
carrying my bicycle into the apartment. For ten or twenty minutes, he
romped through the ivy and bushes around my apartment while I followed
him around rattling a bag of cat treats. Eventually, he let me pick him
up and take him back inside. Naturally, he picked up a few fleas.
Naturally, they have multiplied.

Oddly, the fleas don't seem to like Neil very much, nor do they like me.
It's just poor Buzz that's beset by the nasty little critters.

### Figure 1: A flea.
 ![](http://vort.org/media/images/HookeFlea01.jpg)

As it happens, I've been thinking about [endogenous metrics for
estimating the sampling
quality](http://en.wikipedia.org/wiki/Rarefaction_(ecology)) of an
[environmental shotgun
sequencing](http://www.plosbiology.org/article/info:doi/10.1371/journal.pbio.0050082)
dataset, and Buzz's little problem presented an opportunity to play with
a simplified problem. So, I have decided to make Buzz, or rather his
fleas, into a small experiment in ecology. I am going to try to see if I
can drive them into extinction.

Now, this is normally what a pet owner does when they discover their pet
has contracted some sort of annoying parasite, but I decided to take a
more quantitative approach.

### Figure 2: A cat.
 ![](http://vort.org/media/images/buzz_serious.jpeg)

It's simple enough to count fleas on a cat, if the cat is willing to
cooperate. Buzz loves the flea comb, and will gleefully hop onto the
coffee table and wait to be combed if you show it to him. So, in the
interest of science, I convinced my roommate to count the number of
passes I made with the flea comb and how many fleas I captured
(posterity will remember your efforts, Mehdi). Using his tally, I
plotted the cumulative number of passes verses the cumulative number of
fleas.

### Figure 3: Fleas captured
![](http://vort.org/media/images/fleas_data.png)

As expected, it became somewhat more difficult to capture the next flea
as more fleas were captured, suggesting a depletion curve. The value of
the asymptote should be the actual number of fleas on Buzz at the time,
and reaching that number would imply local extinction for the fleas. Of
course, there are probably other fleas lurking about that would
recolonize Buzz. In principle, if I were to repeat the exercise
frequently enough, Buzz would become a sink for fleas, and their
migration to his fur would gradually deplete them from the environment.

There are a couple of different ways to model the impact of the combing
on the flea population, with various advantages and disadvantages. All
we really want to do here is to estimate the value of the asymptote, and
so a simple model is probably sufficient. I showed this data to my fried
Sharon Shewmake, an economics graduate student. Sharon, after
editorializing on the endeavor ("*Ew.*"), suggested this very simple
model.

Assume that Buzz is not going to sit still long enough for the fleas to
reproduce, for more fleas to migrate to his fur, and that the fleas
already on his fur are going to stay put unless captured. Thus, there is
a fixed initial population which only changes as a result of capturing
fleas. Next, we assume that any given flea is equally likely to be
captured on a single pass of the comb. So, the expectation value for
number of fleas captured on a single pass is the product of the current
population and the probability of capturing a flea.

$$N_{i+1}=N_i-pN_i$$

where $N$ is the population of fleas and $p$ is the probability of any
particular flea being captured on a single pass. One could tart this up
a bit by modeling it as a stochastic process and executing a bunch of
Monte Carlo trials until the outcomes converge, but that seems like
overkill for a simple single variable problem like this. We will put up
with the intellectual inconvenience of capturing fractional fleas.

This is a little easier to see if we let *N* represent the number of
fleas remaining on the cat, rather than the number of fleas captured.

$$N_{i+1}=qN_i$$

If we stretch our credulity far enough to imagine this as a continuous
function, we can express it as a differential equation.

$$\frac{d N}{d t}=\alpha N$$

Sorry if this bothers you. Not only are we extracting fractional fleas,
but we are now modeling the combing process as a sort of
flea-killing-combine continuously mowing its way through the fur. This
is a *model*, so you shouldn't be surprised to find massless rope and
spherical cows. Anyway, it has a nice easy solution.

$$N(t)=e^{\alpha t}$$

Well, what the heck. This is a decaying function, so let's pluck a minus
sign out of the exponential factor, and maybe tack on a scale factor for
the initial population.

$$N(t)=N_0 e^{-\alpha t}$$

While we're at it, why don't we go back to letting the function stand
for the number of fleas captured, rather than the fleas on the cat.

$$N(t)=N_0(1-e^{-\alpha t})$$

This gives us a nice function to use for a linear regression. [A little
help from scipy](http://www.scipy.org/Cookbook/LinearRegression), and we
find that the initial population is estimated at 39.7 fleas, and the
decay factor is 0.011.

### Figure 4: Flea population
![](http://vort.org/media/images/fleas_fit.png)

I captured 34 fleas, so that means I missed about five or six. In order
to be reasonably confident that I'd captured all 39 fleas, I would have
had to continued for about 400 passes with the comb, instead of 173.
Buzz is a patient cat, but he started to loose interest around 120
passes, and had to be fetched back onto the coffee table a few time
times during the last 50 passes. My guess is that 400 passes would
require some kind of sedative. On the other hand, he does seem to like
Guinness, so there may be something to that.

Science has been served. I'm going to the pet store to buy some flea
collars.
