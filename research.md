---
layout: page
title: Research
permalink: /research/
---

I teach computers to be better at guess, check, and revise. At least, that is the short version of my research.
More precisely, I develop optimization algorithms based on evolutionary principles for the purpose
of finding high quality solutions to challenging real-world problems.
<!---
Most of the time this involves staring at white boards, pacing back and forth,
and muttering to myself, with occasional rushes of pure excitement caused by some new revelation.
-->

For the last 18 months I have been working to develop what I call the
[Parameter-less Population Pyramid](http://dl.acm.org/citation.cfm?id=2598350), or P3 for short.
P3 is built on the idea that it is often easier to determine how good a solution is than to find the best possible solution.
To understand how P3 works, let’s apply it to the problem of packing a moving truck.
It’s pretty easy to measure how good a packing configuration is (how much stuff fits in the truck) but pretty
hard to find the best configuration (getting everything in the truck). To solve this problem,
P3 starts with an initial guess (random solution) for how to pack the truck, and then makes minor
changes to that guess (hill climbing) until doing so can’t make it any better. For instance, you might get
to the point where moving any chair will not make things better, but if you could move all of them at once
into a big stack it would be a lot better.

{% include figure.html src="https://brianwgoldman.github.io/images/p3-algorithm.png"
    caption="These are the words under the image." width="50%" height="50%" %}

Unfortunately, trying to test all ways to make larger changes to a guess can take a lot of time.
To overcome this problem, P3 stores multiple good guesses (population) and tries to learn what makes them good.
To further improve, P3 tries to take the good parts of previous guesses and combine them to create new ones (mixing).
In our example, this could mean putting together the box stacking from one guess and the furniture layout of another.
In order to focus learning, P3 filters guesses based on how much effort went into producing each guess,
storing them separately (pyramid of populations). This design also lets P3 learn as it goes (parameter-less),
unlike most evolutionary systems where you need to know how many guesses to store before starting optimization.

This method of iterative solution improvement is designed to be applicable to a wide range of problems.
The exact same algorithm can, for instance, be applied to making better Organic LED molecules
to positioning wind turbines in a field for maximum efficiency.
Unlike many previous methods which rely on people to provide problem specific information,
P3 is focused on learning everything it needs from the problem itself.
On top of being easier to use, all of
[the initial results](http://www.mitpressjournals.org/doi/abs/10.1162/EVCO_a_00148) suggest that P3 is actually
more effective than existing methods for performing this kind of optimization.

