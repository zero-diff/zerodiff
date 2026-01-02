# Hardware

This site documents the ZeroDiff process for small teams producing high-value products at low-to-medium volumes. The goal: rapid iteration with real users. Every commit—whether deploying code or shipping hardware—goes live for value testing. This repeats for an ever-growing user base with ever-growing product value. Experience suggests 15 iterations reach maximal user value, so multiply your iteration cycle time by 15 to estimate when your design reaches optimal utility.

For years, this site focused on hardware—how to iterate PCBs and enclosures the way software teams iterate code. But the more I worked in both domains, the more I realized they solve similar problems in parallel, often unaware of each other's solutions. After a long break from writing, I'm expanding this documentation to cover both. The hardware sections are more developed because that's where I've spent more time. Software insights are coming, informed by the same zerodiff principles. Both industries can learn from each other, and I'm learning by writing about both.

### In Software

Your development cluster is identical to production. Every branch can go live. No Docker Compose hacks that diverge from production infrastructure. When you merge, you deploy, because your test environment was already production ready.

### In Hardware

Your prototype PCBs, enclosures, and interfaces use the same process and tooling as your production run. Every revision is manufacturing-ready. No "works-like/looks-like" splits. When you validate a design with users, you can immediately scale it.

**The Result**: Rapid iteration with real users, no "big bang" releases, and the ability to scale at any moment.


## Examples in Practice

### Software: Everything as a Whole, Every Time!

Container orchestration has given us the ability to test whole systems with users, and [Karrots](https://karrots.zerodiff.org) is a way to cheaply and quickly deploy a cluster for every story. Now we can test whole systems with high user-fidelity. When it comes time to deploy the work to production, it's a simple git commit because we started with a git branch that gave us a faithful copy of the production cluster.

### Hardware: Kill the Waterfall Method (Again!)

#### i.e. Crowdsource, Works-Like/Looks-Like, Shenzhen

Prior to the 2000s, software development followed a process called The Waterfall Method. Product development would follow a sequence: conception, analysis, design, construction and testing. 12-18 months might pass before users saw anything, and if they wanted changes or didn't like features, it might be another 12-18 months before they would see those changes. It was pretty awful, and no good software product designer would ever want to go back to those times. Today, software developers follow a lean or agile practice that involves small, rapid iterations with continual and close user-value testing. Each iteration allows for incremental investments targeted toward value and user growth.

So why are hard goods designers stuck in the Waterfall Methodology? Setting aside the debate of just how easy/cheap it is to fly to Shenzhen to engage a fab/CMS in supply chain execution, there are two major problems with this approach:

* The team is working toward a single manufactured revision given imperfect user testing - a kind of Hail Mary pass.
* The product users are somewhere else, so for the factory design team, user empathy is low.

The whole point of ZeroDiff is to rapidly iterate with the users close at hand. With traditional overseas manufacturing, a single design iteration might take 4-8 weeks (design revision → overseas sampling → shipping → user testing → feedback analysis). Under ZeroDiff, this same cycle can happen in 1-2 weeks, meaning you can complete 5-10 iterations in the time it would take for a single overseas prototype cycle. Maybe you build ten of the first version and get them into the hands of real users. This allows the product design team to evaluate the user experience and propose design changes that show up in the next iteration within 1-2 weeks. Each successive iteration grows the product value, and potentially grows the user base. Since every revision is production-ready, the development team can select any revision for mass production. At that point, if your demand is high and you need MoQ 10K production runs then it's super simple to take your latest rev to Shenzhen. The rest of us (most of us) can continue to produce economically in low-volume close to where we live.

### Permission-based Production is Terrible

As small-batch production becomes less economically viable, product design teams find themselves in a permission-based production model where they have to convince a fab or CMS of the value of their job over other jobs. Most modern fabs will quickly design prototypes and produce samples in order to win larger business later, but they will not run those designs at low volume unless there's no other work on the line. To make things worse, the production-version designs and fab/assembly docs are generally not accessible to the product design team, making it painful and expensive to switch fabs.

ZeroDiff eliminates permission-based production by giving you direct control over your manufacturing process. When you own or have reliable access to the production tooling and can manufacture economically at low volumes, you don't need to convince anyone that your 50-unit run is worthwhile. You simply produce it. This autonomy means you can iterate on your timeline, not on a fab's production schedule, and every design file remains yours to use, modify, or take elsewhere.

## The Joy of High-Value at Low-Volume

A side-effect of the ZeroDiff process is that small-batch production is something you can do economically on short development cycles and low unit volume. Traditionally, low-volume manufacturing has been prohibitively expensive, limiting production to products with clear mass-market appeal and high price points. By making small-batch production economically viable, ZeroDiff opens the door to creating products that serve niche needs or pursue goals beyond profit maximization. "Value" is a complex word, but in production we tend to boil it down to simple economics. What happens when an object's cost or sales price is not a major component of its value? When you can produce 10 or 100 units economically rather than needing 10,000 to justify tooling costs, that gives us the luxury to choose the many other definitions of value. Perhaps we can choose to make things because they increase our enjoyment, or relieve the suffering of others — assistive devices for rare conditions, tools for small communities, or products that prioritize sustainability over scale. The possibilities are enormous and liberating!