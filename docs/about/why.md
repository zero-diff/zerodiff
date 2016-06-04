# Why ZeroDiff?

In 2011 I started a side-project that would become my next startup: an innovative, low-power, cloud-controlled IoT device applied to e-commerce logistics and automation. Prior to 2011 I knew nothing about electrical, hardware or radio engineering. I tapped the many sites (Sparkfun, Instructables, Stack-Exchange, etc.) that explained how "makers" like me could learn to build hardware, and within 12 months I had a cloud-controlled hardware system complete enough to conduct my first pilot project. After we completed the pilot and collected all of the usability data, it was clear that "version 2" was going to be almost as much work to design/build as "version 1!"

What these sites **don't** explain is how to build a hardware business!

Undeterred, we pressed on. Version 2 took almost six more months! The product was starting to look pro and we were able to raise money to become a real company. A frustrating problem was that more people and money had almost no material impact on our ability to rapidly innovate hardware designs. We would think, "Oh, if the product could do X, then it would be awesome." We knew X wouldn't see the light of day for almost a year, and there was a growing pile of X-like feature requests. It was depressing. Right around this time, my wife asked me to clear out of the home shop so that our boys could have a big play space. That meant hauling to work a CNC mill and a bunch of tools. That same week we learned of our first opportunity to create an "add on" product to our system, but we didn't have 6-12 months to do it. The opportunity would disappear in 8-12 weeks. I went online to see if it was possible to create sophisticated SMT/SMD circuit boards on a CNC mill, and sure enough we found a tutorial for our exact mill. We hired a skilled machinist, and within two weeks we could generate a completed PCB/A in just a few days. At that time we used off-the-shelf enclosures that were expensive and ugly (to us by now). We decided to create a formal design studio and hired our design consultant to run it. He devised a system where we could build new enclosures in a CNC mill following a layer-by-layer stack-up process. This enabled us to create fairly complex, but good looking enclosures with features, like undercuts, that you normally can't create from a single, milled part. Eventually, we developed our design process further to incorporate folded steel to greatly increase our iteration and manufacture rate while bringing costs way down. The tooling we used is not expensive: likely you could recreate our entire shop for $50K, and a light-duty version of it for less than $25K.

Over the course of a year we formalized this process into a set of internal processes and documentation we called ZeroDiff. Through these process improvements we were able to complete production-ready hardware design revisions in as little as 48 hours. Working with local vendor/partners we were able to source all of the components to make tens of thousands of sophisticated radio control systems entirely in our downtown Oakland office. 

## Now to Share it

We had always intended to share our ZeroDiff process, but there just never seemed to be a good way (or time) to do it. All of the company docs were trapped in Confluence, which is not a particularly great system (not forkable, and now long on tooth). I really wanted this stuff to live in github, so that the community could share and possibly grow it without a lot of inter-organization coordination. Once I found mkdocs, it seemed clear this was the right way forward.

## A Work In Progress

Because I only lightly edited these documents as I extracted them, they still may have the company stink on them. They might also be incomplete, because it's just not possible to collect all the weird loose ends from our company system since it was spread across Confluence, Google Docs, Email and Jira. This is just a starting point, and I hope we all can grow this together.

## ZeroDiff is not for Everyone

I find that about 20% of the folks who hear about ZeroDiff "get it" and would like to embrace it. I'm not on a mission to sell ZeroDiff, and I recognize there's many ways to reach the same end in product development. It's just a simple idea, and never really should be complex. There's a certain kind of product auteur nowadays who can seem to do it all, and I find them fascinating no matter what process they follow.

## Make it Local Wherever Local is

Finally, probably the most important part of ZeroDiff is that you can design and build a product close to the user *wherever they are*. This is the thing that excites me the most because I believe it unlocks a world where low-volume, high-value products can thrive **.

<br>
<br>
** For the non-economic definitions of value: basically when there's no money in making people's lives better.