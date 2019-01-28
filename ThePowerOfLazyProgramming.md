# The power of lazy programming

https://www.infoworld.com/article/3122803/application-development/the-power-of-lazy-programming.html#tk.ifwrs

These 13 tools and techniques prove that, when it comes to coding, laziness is a virtue

>By Peter Wayner Contributing Editor,InfoWorld | SEP 28, 2016

Whoever said working hard is a virtue never met a programmer. Yes, ditch diggers who work hard generate longer ditches than those who daydream, and farmers who lean into the plough plant more food than those who stare off into the sky. But programming isn’t the same. There is no linear relationship between sweat on the brow and satisfied users.

Sometimes it helps if programmers pull all-nighters, but more often than not it’s better for programmers to be smart -- and lazy. Coders who ignore those “work hard, stay humble” inspirational wall signs often produce remarkable results, all because they are trying to avoid having to work too hard. The true geniuses find ways to do the absolute minimum by offloading their chores to the computer. After all, getting the computer to do the work is the real job of computer programmers.

Here are 13 techniques and tools that prove the power of lazy programming. The next time the boss tells you it’s time to roll up your sleeves and lean into the console, head to the nap room instead.

## 1 Lazy evaluation
Somewhere along the line, smart programmers realized their software would run faster if it didn’t dutifully calculate every single part of an expression. This feature, sometimes referred to as “call by need” or “lazy evaluation,” is now officially part of programming languages like Haskell, F#, and Python 3.0.

The simplest example is the strategy’s use in checking for null pointers. The object x is checked to be non-null before the calculation routine begins in this statement:

if (x && x.calculation()) then …

Testing the existence of x prevents crashing. In more elaborate examples, lazy evaluation saves endless amounts of calculation that will be thrown away by looking ahead to see when the computation tree can be pruned. If the quick test is the first one executed, it can save a bazillion cycles later. When the data structures are potentially infinite, as they are in some number-theory examples, then lazy evaluation allows the program to actually finish.

The technique is not only useful for speeding up functional languages such as Haskell. Smart programmers won’t spend hours calculating values if only a few of them are going to be used. They’ll embed lazy switches that trigger the computation only when someone wants to use it. Here, doing the minimum amount of work makes sense.

## 2 Caching
Why repeat yourself? Anyone who’s programmed for the web knows there’s a lot of repeating yourself to everyone who shows up at your site. Caching is the answer -- and not only for websites. Any code that recomputes the same problem can be sped up by keeping copies of the answer around.

It doesn’t have to be the final answer. Sophisticated caches can keep partial answers for various parts of the problem. If some parts need to be recomputed, they can still tap the cache for the parts that don’t need to be redone. Websites that assemble web pages, for instance, often cache blocks for different parts of the page, then assemble the full pages from the blocks.

Extralazy people may complain that caching is more work for the programmer. After the code for finding the answer is done, it’s time to write another layer that sits on top to keep a cache of the answers. They may be right about this extra layer, but they’re missing the other work that’s being saved. Good caches can save us all of the work of scaling the server farm to handle the extra load. Scaling is often more work than writing some caching code.

## 3 Specify everything only once
One of the most important rules I learned about programming is that each constant should be written only once in the code. If the software is spec’d to put a one-inch margin around a page, the value of one should appear only once in the definition of a constant. Then the constant is used everywhere else.

This simple bit of organized laziness pays off down the road. If you want to change the value -- say, by boosting the margin to 1.5 inches -- you need to make only one change to the code.

You can also work in a bit of self-documentation into the name of your constants, giving your margin value a name like MarginSizeInInches. That can save you the trouble of writing a separate comment, and this constant-as-comment will follow the constant throughout the code.

Sure, longer constant names could mean more typing, but then most programming editors offer autocomplete to save you even more.

## 4 Frameworks: The ultimate shortcuts
On one project, a suit wanted a new website, so I whipped one up and made the mistake of telling him I was using WordPress. That was no good. One of his buddies down at the golf course told him that WordPress was for blogs and this was going to be brochureware. Was I an idiot?

So he bullied the CFO into allocating $5,000 for a professional website. The results looked great and it functioned very smoothly, as it should because the guts were all WordPress. The company that charged him $5,000 was smart enough not to mention what they used for a foundation.

Some people like custom code for the same reason that some people hike Mount Everest: They like to do it themselves, no matter what the costs. Smart programmers download a good open source framework like WordPress or Drupal and stand on the shoulders of giants. If any new code is written, it’s no more than a few lines.

Breaking a sweat to write your own code is often a big mistake. The open source code for the frameworks is already well-tested by hundreds if not thousands of people. It’s not always ideal, but it’s like starting at the 99-meter line in a 100-meter dash. Furthermore, as you test the code and upload any bug reports or fixes, everyone else’s installation benefits.

## 5 Automation: Better than ever

Some C jockeys still love to malloc their own memory and free it when they know it’s done. As they see it, reference counting and garbage collection are for wimps. Of course, there also might be some coal miners who still use a pick axe, just like John Henry.

A good part of programming language development is automation, and the tools have never been better. Memory management, type checking, and parallel processing are being reinvented as automatic tools, replacing all the grungy background work programmers used to do themselves.

Lazy programmers aren’t resisting these tools. They know that for all of their flaws, they’re still better than the average human on an average day. Oh sure, a very clever hacker can spend extra time and produce an insanely fast work of art, but that makes sense only for the inner loops of the most important parts of the system. The rest of us are better churning out average code and letting the automated tools keep us from making some of the worst mistakes.

## 6 Devops: Laziness personified
Some people sneer at the script writers who craft the instructions for keeping the code up-to-date and the servers running. What’s so hard about unzipping some files or copying over some directories?

Of course most of the housekeeping isn’t that hard, and most of the common Unix commands are only two characters, but that misses the point. Being lazy and automating the deployment and maintenance ensures it will be done quickly and -- most important -- consistently. The midnight shift will do things exactly like the 8 a.m. team -- and it won’t matter if either had coffee or not.

Automation brings rigor and stability. Sure, the devops team looks fat and lazy when it doesn’t even push a button because the crontab triggers it, but everything runs smoother. There aren’t as many mistakes when the humans are out of the loop.

## 7 Code reuse
Only suckers start from scratch. In fact, today I took out some code I wrote over the summer, changed five lines, and started it running again. Woo hoo. It was sitting there in a code repository waiting for a chance to live again.

Smart developers reuse code as often as they can. That was one of the main goals of the open source movement. It wasn’t freedom;it was laziness. If we reuse our code, we save a gazillion hours of work.

## 8 Flexible code
Before I immerse myself into programming, I like to take a nap -- not a full trip to dreamland, but a gentle excursion that gives me the time to imagine everything the code might do. It looks like I’m sleeping, but I’m planning how to make the code as flexible as possible.

This laziness always pays off. Good programmers usually try to build flexibility into their code in case they need to change parameters or details in the future. Naysayers will complain that adding flexibility may make the code longer. They take some shortcuts that are often short-sighted. Adding flexibility by building in more parameters and splitting up procedures doesn’t cost that much time. Yes, it adds lines and expands the size of the file sizes, but those extra key clicks always pay off later when someone wants to change the code.

The key is to understand the code and architecture well enough to know when to add the extra flexibility. When this becomes instinct, you’ll have a way to be lazy and efficient at the same time. And usually a nap helps.

## 9 Documentation saves questions

While it is a well-known fact that writing is hard work and writers are never appreciated enough for their ability, programmers write out of laziness. They create documentation about the code so that others won’t bother them. They don’t want to field questions from the great sea of fools, so they write up good man pages explaining what the switches do. Sure, it takes a bit more work to write clearly and crisply, but it more than makes up for it in the long run when people leave you alone.

# 10 Sparse comments

Of course, when it comes to commenting, often less is more. Yes, you’re supposed to mix in a few words from your favorite human language to make it easier to understand the computer language. In fact, contracts often include requirements that withhold payment if there are no comments.

But being lazy about comments does force you to produce clean, simple code based on straightforward logic. Sure, if you’re doing something weird or hard to grasp, leave a note explaining your burst of genius. But should you really be doing something weird and hard to grasp? The best solution is to spend a little nap time pondering a very clean architecture. Then you won’t need to write many comments or spend hours updating them.

As with the constants mentioned above, longer variable names mix documentation into the code. This documentation follows the variable everywhere it’s used, unlike comments, which are merely attached to the declaration.

## 11 Automated testing
When you’re creating amazing code with only a few keystrokes, who has time to double and triple check to make sure it works? And how can anyone validate whether the new code isn’t breaking the old code? Enter the unit test -- the lazy programmer’s godsend for automatically making sure the code still works.

Some people say the greatest thing Sun did when it created Java was build millions of unit tests. Oh, the software is wonderful, but the unit tests make sure it keeps working in a predictable and unsurprising manner.

## 12 Automated metatools

It’s not only automated housekeeping like garbage collection, and it’s not automated devops tools like Puppet and Chef alone. There are now great metatools that merge all of the housekeeping chores into one big system. The logo for Hudson and Jenkins is a goofy cartoon of a butler, a perfect symbol for a system designed to organize all of the scut work around code -- while you kick back with a cold brew.

Once you check in the code, these automated metatool systems handle all the other tasks, like running unit tests, backing up the code, and even deploying it. It’s like the ultimate assistant for a lazy person -- and that’s why these so-called continuous integration tools are the ultimate assistants for programmers.

## 13 Compilers

Many of the basic tools we take for granted started out as inventions of the lazy. If it weren’t for compiler creators, we would still be stringing together machine op-codes and trying to remember whether that intermediate value was stashed in register two or three. Heck, if it weren’t for the inventors of mass storage tools like paper tape or magnetic tape, we would be flicking in these values through those front panels, the ones with flashing lights and switches. They look so cool in movies but were a pain to use.

Pretty much all of computing has been a quest to create a new set of tools to make our lives easier. Almost every tool or app began out of frustration. It’s been a long journey from the beginning of the internet to Snapchat, but every step along the way has been a short exercise in laziness. In a few years we probably won’t even have to use a keyboard to program.