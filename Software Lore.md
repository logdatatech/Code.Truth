# Software Lore

## Zawinski's law of software envelopment (also known as Zawinski's law)

https://en.wikipedia.org/wiki/Jamie_Zawinski#Principles

> Every program attempts to expand until it can read mail. Those programs which cannot so expand are replaced by ones which can.

---

## Murphy's Law

https://en.wikipedia.org/wiki/Murphy%27s_law

Probably one of the most famous of all laws, mostly because it is not only applicable to Software Development.

> If something can go wrong, it will.

First derivation: If it works, you probably didn't write it.
Second derivation: Cursing is the only language all programmers speak fluently.
Conclusion: A computer will do what you write, not what you want.

Defensive programming, version control, doom scenario's (for those damned zombie-server-attacks), TDD, MDD, etc. are all are good practices for defending against this law.

---

## Brook's Law

https://en.wikipedia.org/wiki/Brooks%27s_law

Most developers will -either knowingly or unknowingly- have experience with Brook's law, which states:

> Adding manpower to a late software project makes it later.

If a project is running late, simply adding manpower will most likely have disastrous results. Looking and reviewing the level of programming efficiency, the software methodology, the technical architecture, etc. will almost always have better outcomes. Or not, which probably means Hofstadter's Law is also in play.

---

## Hofstadter's Law

Have you ever noticed that doing something always takes longer than you think? So did [Douglas Hofstadter](https://en.wikipedia.org/wiki/Douglas_Hofstadter), who wrote a seminal book on cognitive science and self-reference called [Godel, Escher, Bach: An Eternal Golden Braid](http://amzn.to/1V6ThCz). In that book, he proposed Hofstadter's Law:

> "It always takes longer than you expect, even when you take into account Hofstadter's Law."

Always is the key word: nothing ever goes as planned, so you're better off putting extra time in your estimates to cover some thing that will go wrong, because it unfailingly does.

The "law" is a statement regarding the difficulty of accurately estimating the time it will take to complete tasks of substantial complexity. The recursive nature of the law is a reflection of the widely experienced difficulty of estimating complex tasks despite all best efforts, including knowing that the task is complex.

---

## Conway’s Law

https://en.wikipedia.org/wiki/Conway%27s_law

Any piece of software reflects the organizational structure that produced it.

Or even more clearly:

> "Organizations which design systems are constrained to produce designs which are copies of the communication structures of these organizations."

In many organizations teams are divided according to their functional skills. So you'll have teams of front-end developers, backend-developers and database developers. Simply stated, it's hard for someone to change something if the thing he/she wants to change is owned by someone else.

It is much better, and more and more implemented as such, to deploy teams around a bounded context. Architectures such as microservices structure their teams around service boundaries rather than siloed technical architecture partitions.

So, structure teams to look like your target architecture, and it will be easier to achieve it. That's how you defend against Conways's law.

---

## Wirth's law

https://en.wikipedia.org/wiki/Wirth%27s_law

> Wirth's law is an adage on computer performance which states that software is getting slower more rapidly than hardware becomes faster.

The adage is named after Niklaus Wirth, who discussed it in his 1995 paper, "A Plea for Lean Software".

The law was restated in 2009 and attributed to Larry Page, founder of Google. It has been referred to as Page's law. The first use of that name is attributed to Sergey Brin at the Google I/O Conference 2009.

Other common forms use the names of the leading hardware and software companies of the 1990s (Intel & Microsoft), or their CEOs (Andy Grove & Bill Gates): "What Intel giveth, Microsoft taketh away" and "What Andy giveth, Bill taketh away".

Gates's law ("The speed of software halves every 18 months") is a variant on Wirth's law, borrowing its name from Bill Gates, co-founder of Microsoft. It is an observation that the speed of commercial software generally slows by 50% every 18 months, thereby negating all the benefits of Moore's law. This could occur for a variety of reasons: "featuritis", "code cruft", developer laziness, or a management turnover whose design philosophy does not coincide with the previous manager.

May's law, named after David May, is a variant stating: "Software efficiency halves every 18 months, compensating Moore's law".

---

## Moore's Law

https://en.wikipedia.org/wiki/Moore%27s_law

> Moore's law is the observation that the number of transistors in a dense integrated circuit doubles about every two years.

The observation is named after Gordon Moore, the co-founder of Fairchild Semiconductor and CEO of Intel, whose 1965 paper described a doubling every year in the number of components per integrated circuit, and projected this rate of growth would continue for at least another decade. In 1975, looking forward to the next decade, he revised the forecast to doubling every two years. The period is often quoted as 18 months because of a prediction by Intel executive David House (being a combination of the effect of more transistors and the transistors being faster).

Moore's prediction proved accurate for several decades, and has been used in the semiconductor industry to guide long-term planning and to set targets for research and development. Advancements in digital electronics are strongly linked to Moore's law: quality-adjusted microprocessor prices, memory capacity, sensors and even the number and size of pixels in digital cameras. Digital electronics has contributed to world economic growth in the late twentieth and early twenty-first centuries. Moore's law describes a driving force of technological and social change, productivity, and economic growth.

---

## Greenspun's tenth rule of programming

[Greenspun's tenth rule of programming](https://en.wikipedia.org/wiki/Greenspun%27s_tenth_rule) is an aphorism in computer programming and especially programming language circles that states:

> Any sufficiently complicated C or Fortran program contains an ad-hoc, informally-specified, bug-ridden, slow implementation of half of Common Lisp.

---

## The Software Peter Principle

https://en.wikipedia.org/wiki/Software_Peter_principle

> The Software Peter Principle is used in software engineering to describe a dying project which has become too complex to be understood even by its own developers.

### Programmer incompetence

The best software developers understand the importance of communicating with people over communicating with the computer, according to Code Complete by Steve McConnell. On average, 85 percent of a programmer's time is spent communicating with people, while only 15 percent is spent communicating with the computer. Maintenance programmers spend 50 to 60 percent of their time trying to understand the code they have to maintain and a software program will have, on average, 10 generations of maintenance programmers in its lifetime.

### Programmer inexperience

Programmers sometimes make implementation choices that work but have unintended negative consequences. The most common of these mistakes are cataloged and referred to as smells in the book Refactoring by Martin Fowler. Over time, many such implementation choices degrade the software’s design, making it increasingly difficult to understand.

---

## Knuth's optimization principle

https://en.wikipedia.org/wiki/Program_optimization#When_to_optimize

> Premature optimization is the root of all evil.

optimization

First you write code, then you identify bottlenecks, then you fix!

---

## The Law of Accelerating Returns

https://en.wikipedia.org/wiki/Accelerating_change#Kurzweil's_The_Law_of_Accelerating_Returns

In his 1999 book The Age of Spiritual Machines, Ray Kurzweil proposed "The Law of Accelerating Returns", according to which the rate of change in a wide variety of evolutionary systems (including but not limited to the growth of technologies) tends to increase exponentially. Whenever a technology approaches some kind of a barrier, according to Kurzweil, a new technology will be invented to allow us to cross that barrier. He cites numerous past examples of this to substantiate his assertions. He predicts that such paradigm shifts have and will continue to become increasingly common, leading to "technological change so rapid and profound it represents a rupture in the fabric of human history." He believes the Law of Accelerating Returns implies that a technological singularity will occur before the end of the 21st century, around 2045.

---

## Norvig's Law

https://en.wikipedia.org/wiki/Peter_Norvig

> Any technology that surpasses 50% penetration will never double again (in any number of months).

---

## Turing tar-pit

https://en.wikipedia.org/wiki/Turing_tarpit

A Turing tarpit (or Turing tar-pit) is any programming language or computer interface that allows for flexibility in function but is difficult to learn and use because it offers little or no support for common tasks. The phrase was coined in 1982 by Alan Perlis in the Epigrams on Programming:

> 54. Beware of the Turing tar-pit in which everything is possible but nothing of interest is easy.

---

## Inner-platform effect

https://en.wikipedia.org/wiki/Inner-platform_effect

> The inner-platform effect is the tendency of software architects to create a system so customizable as to become a replica, and often a poor replica, of the software development platform they are using. This is generally inefficient and such systems are often considered to be examples of an anti-pattern.

In the database world, developers are sometimes tempted to bypass the RDBMS, for example by storing everything in one big table with three columns labelled entity ID, key, and value. While this entity-attribute-value model allows the developer to break out from the structure imposed by an SQL database, it loses out on all the benefits, since all of the work that could be done efficiently by the RDBMS is forced onto the application instead. Queries become much more convoluted, the indexes and query optimizer can no longer work effectively, and data validity constraints are not enforced. Performance and maintainability can be extremely poor.

---

## Second-system effect

https://en.wikipedia.org/wiki/Second-system_effect

> The second-system effect (also known as second-system syndrome) is the tendency of small, elegant, and successful systems, to be succeeded by over-engineered, bloated systems, due to inflated expectations and overconfidence.

The phrase was first used by Fred Brooks in his book The Mythical Man-Month, first published in 1975. It described the jump from a set of simple operating systems on the IBM 700/7000 series to OS/360 on the 360 series, which happened in 1964.

---

## Occam's Razor

This widely-known adage dates to a philosopher and friar from the fourteenth century named [William of Ockham](https://en.wikipedia.org/wiki/William_of_Ockham). [Occam's Razor](https://en.wikipedia.org/wiki/Occam%27s_razor) is often stated as:

> "Among competing hypotheses, the one with the fewest assumptions should be selected."

## It's no surprise that the whole reason we can recall an adage from 600+ years ago is that it works so well. Occam's Razor is so basic, so fundamental, that it should be the first thing we think of when deciding between two competing theories. I'd even go so far as to argue that in the vast majority of cases, simpler is better.

## Hanlon's Razor

Sometimes I feel like users are [intentionally trying to piss me off](http://www.exceptionnotfound.net/are-users-trying-to-make-developers-angry/). They push buttons they weren't supposed to, found flaws that shouldn't have been visible to them (since they weren't to me), and generally make big swaths of my life more difficult than it would otherwise be.
I try to remember, though, that the vast majority of actions done by people which may seem malicious are not intentionally so. Rather, it's because they don't know any better. This is the crux of an adage known as [Hanlon's Razor](https://en.wikipedia.org/wiki/Hanlon%27s_razor), which states:

> "Never attribute to malice what can be adequately explained by stupidity."

Don't assume people are malicious; assume they are ignorant, and then [help them overcome that ignorance](http://www.exceptionnotfound.net/we-dont-have-enough-teachers-of-technology/). Most people want to learn, not be mean for the fun of it.

---

## The Pareto Principle

The last Basic Law of Software Development is the Pareto Principle. Romanian-American engineer [Joseph M Juran](https://en.wikipedia.org/wiki/Joseph_M._Juran) formulated this adage, which he named after an idea proposed by Italian economist and thinker [Vilfredo Pareto](https://en.wikipedia.org/wiki/Vilfredo_Pareto). The [Pareto Principle](https://en.wikipedia.org/wiki/Pareto_principle) is usually worded as:

> "80% of the effects stem from 20% of the causes."

Have you even been in a situation where your app currently has hundreds of errors, but when you track down one of the problems, a disproportionate amount of said errors just up and vanish? If you have (and you probably have), then you've experienced the Pareto Principle in action. Many of the problems we see, whether coding, dealing with customers, or just living our lives, share a small set of common root issues that, if solved or alleviated, can cause most or all of the problems we see to disappear.
In short, the fastest way to solve many problems at once is the find and fix their common root cause.

---

## Dunning-Kruger Effect

Researchers David Dunning and Justin Kruger, conducting an experiment in 1999, observed a phenomenon that's come to be known as the [Dunning-Kruger effect](https://en.wikipedia.org/wiki/Dunning%E2%80%93Kruger_effect):

> "Unskilled persons tend to mistakenly assess their own abilities as being much more competent than they actually are."

What follows from this is [a bias](https://en.wikipedia.org/wiki/Illusory_superiority) in which people who aren't very good at their job think they are good at it, but aren't skilled enough to recognize that they aren't. Of all the laws in this list, the Dunning-Kruger effect may be the most powerful, if for no other reason than it has been actively investigated in a formal setting by a real-life research team.

---

## Linus's Law

Author and developer [Eric S. Raymond](https://en.wikipedia.org/wiki/Eric_S._Raymond) developed this law, which he named after [Linus Torvalds](https://en.wikipedia.org/wiki/Linus_Torvalds). Linus's Law states:

> "Given enough eyeballs, all bugs are shallow."

In other words, if you can't find the problem, get someone else to help. This is why concepts like [pair programming](http://www.exceptionnotfound.net/how-my-5-year-old-taught-me-the-value-of-pair-programming/) work well in certain contexts; after all, more often than not, [the bug is in your code](http://www.exceptionnotfound.net/the-bug-is-in-your-code/).

---

## Robustness Principle (AKA Postel's Law)

One of the fundamental ideas in software development, particularly fields such as API design, can be concisely expressed by the [Robustness Principle](https://en.wikipedia.org/wiki/Robustness_principle):
"Be conservative in what you do, be liberal in what you accept from others."
This principle is also called Postel's Law for [Jon Postel](https://en.wikipedia.org/wiki/Jon_Postel), the Internet pioneer who originally wrote it down as part of [RFC 760](https://tools.ietf.org/html/rfc760). It's worth remembering, if for no other reason than an gentle reminder that often [the best code is no code at all](http://www.exceptionnotfound.net/the-best-code-i-have-ever-written/).
Eagleson's Law
Ever been away from a project for a long time, then returned to it and wondered "what idiot wrote this crap?" only to find out [that the idiot was you](http://www.exceptionnotfound.net/ancient-oracle-modern-iis-and-a-failure-to-rtfm/)?
Eagleson's Law describes this situation quite accurately:
"Any code of your own that you haven't looked at for six or more months might as well have been written by someone else."
Remember that the next time you're rejoining a project you've been away from for months. The code is [no longer your code](http://www.exceptionnotfound.net/you-are-not-your-code/); it is someone else's that you've now been tasked with improving.

---

## Peter Principle

One of the fundamental laws that can apply to managers (of any field, not just software) is the [Peter Principle](https://en.wikipedia.org/wiki/Peter_principle), formulated by Canadian educator [Laurence J Peter](https://en.wikipedia.org/wiki/Laurence_J._Peter):
"The selection of a candidate for a position is based on the candidate's performance in their current role, rather than on abilities relevant to the intended role."
The Peter Principle is often sarcastically reduced to "Managers rise to their level of incompetence." The idea of this principle looks like this:

The problem revealed by the Peter Principle is that workers tend to get evaluated on how well they are currently doing, and their superiors assume that those workers would also be good at a different role, even though their current role and their intended role may not be the same or even similar. Eventually, such promotions place unqualified candidates in high positions of power, and in particularly bad cases you can end up with [pointy-haired bosses](https://en.wikipedia.org/wiki/Pointy-haired_Boss) at every step of an organization's hierarchy.

---

## Dilbert Principle

Speaking of pointy-haired bosses, cartoonist [Scott Adams](https://en.wikipedia.org/wiki/Scott_Adams) (who publishes the comic strip Dilbert) proposed an negative variation of the Peter Principle which he named the [Dilbert Principle](https://en.wikipedia.org/wiki/Dilbert_principle). The Peter Principle assumes that the promoted workers are in fact competent at their current position; this is why they got promoted in the first place. By contrast, the Dilbert Principle assumes that the least competent people get promoted the fastest.

The Dilbert Principle is usually stated like this:

> "Incompetent workers will be promoted above competent workers to managerial positions, thus removing them from the actual work and minimizing the damage they can do."

This can be phrased another way:

> "Companies are hesitant to fire people but also want to not let them hurt their business, so companies promote incompetent workers into the place where they can do the least harm: management."

---

## The 90-90 Rule

Because something always goes wrong, and because people are notoriously bad at estimating their own skill level, Tom Cargill, an engineer at Bell Labs in the 1980's, proposed something that eventually came to be called [the 90-90 rule](https://en.wikipedia.org/wiki/Ninety-ninety_rule):

"The first 90 percent of the code accounts for the first 90 percent of the development time. The remaining 10 percent of the code accounts for the other 90 percent of the development time."
Perhaps this explains why so many software projects end up over budget and short on features.

---

## Parkinson's Law

What is possibly the most astute observation that can be applied to the art of estimation comes from British naval historian [C. N. Parkinson](https://en.wikipedia.org/wiki/C._Northcote_Parkinson). He jokingly proposed an adage called [Parkinson's Law](https://en.wikipedia.org/wiki/Parkinson%27s_law), which was originally understood to be:
"Work expands so as to fill the time available for its completion." Remember this next time you pad your estimates.

---

## Sayre's Law

Economist and professor [Charles Issawi](https://en.wikipedia.org/wiki/Charles_Issawi) proposed an idea that came to be known as [Sayre's Law](https://en.wikipedia.org/wiki/Sayre%27s_law), named after a fellow professor at Columbia University. Issawi's formulation of this law looks like this:
"In any dispute the intensity of feeling is inversely proportional to the value of the issues at stake."
In short, that the less significant something is, the more passionately people will argue about it.

---

## Parkinson's Law of Triviality (AKA Bikeshedding)

Sayre's Law segues directly into another law that applies to meetings, and here we again encounter the ideas of C.N. Parkinson. Parkinson's [Law of Triviality](https://en.wikipedia.org/wiki/Law_of_triviality)states:
"The time spent on any agenda item will be in inverse proportion to the sum of money involved."
Parkinson imagined a situation in which a committee of people were tasked with designing a nuclear reactor. Said committee then spends a disproportionate amount of time designing the reactor's bikeshed, since any common person will have enough life experience to understand what a bikeshed should look like. Clearly the "core" functions of the reactor are more important, but they are so complex that no average person will understand all of them intimately. Consequently, time (and opinions) are spent on ideas that everyone cancomprehend, but which are clearly more trivial.

---

## Law of Argumentative Comprehension

The last law is one I totally made up I use to shorthand both Sayre's Law and Parkinson's Law of Triviality. I call it the Law of Argumentative Comprehension:
"The more people understand something, the more willing they are to argue about it, and the more vigorously they will do so."

---

# General Comments on Softwar Lore ...

You'll notice that many of the laws above don't directly apply specifically to software,
and this is intentional. The fact remains that software is built for people to use and interact with,
so many of these laws relate to dealing with people rather than code.

No pithy quote will ever replace the experience you gain every day by writing code, interacting with users,
and generally [getting better every day](http://www.exceptionnotfound.net/i-dont-care-if-i-suck-as-long-as-im-learning/).
Still, by keeping in mind these lore of software development, you might just make yourself a better developer. Or at least a more knowledgeable one, and really, aren't those the same thing ?
