# 7 bad programming ideas that work

https://www.infoworld.com/article/3106418/application-development/7-bad-programming-ideas-that-work.html

**Cheaper, easier, faster, safer -- sometimes bad habits are better than good enough**

## 1. Quick and dirty code

Few things can kill a project like poorly designed and poorly documented code. Even if your slapped-together stack stands up, maintaining it will be a nightmare. And anyone who inherits your steaming pile of bits will be a sworn enemy for life.

Then again, quick and dirty code has its place. In fact, the pursuit of clean, thoroughly engineered code can be costly. I once worked with a programming manager who looked everyone in the eyes and cited a long list of ways that our software needed to be cleaned up. Our old code may have been running, but the company would dole out another two months of budget to make sure the lines of code were presentable. Sometimes our programming manager would ask for six months’ worth of budget and she would get it. After all, who wanted unclean code?

Not everyone has access to that kind of budget, and few want to tell budgeting managers to cough up another N months of developer time because clean code is best.

Worse, cleanliness is often a slippery concept. One programmer’s clean code is another’s overly complex code. Often cleaning up code means adding new abstractions and layers that make it clear what the code is doing. This can quickly become TMI. Sometimes quick and dirty code is better than complex “clean” code that is paired with documentation on par with "War and Peace."

Anyone who has waded through pages and pages of well-engineered code with layers and layers of abstractions knows that sometimes a bit of code with one simple input and one simple job description is better than a masterful pile of engineering and computer science. Junky but functional code can take 10 seconds to understand -- sophisticated architectures can take weeks.

It’s not that doing a good job is a bad thing -- however, many times no one has the time or energy to unwrap all of the sophistication. When time is in short supply, sometimes quick and sloppy win -- and win big.

## 2. Wasteful algorithms

Sometimes being smart isn’t worth the price. Nowhere is this more evident than when it comes to thoroughly studied algorithms with strong theoretical foundations.

Everyone knows the lessons from college. A smart data structure will do the job in time proportional to the size of the data. A bad one might get slower in time proportional to the square or even the cube of the number of data elements. Some of the truly horrible get exponentially slower as the amount of data grows. The lessons from computer science class are important. Bad algorithms can be really slow.

The problem is that smart, theoretically efficient algorithms can be slow too. They often require elaborate data structures full of pointers and caches of intermediate values, caches that chew up RAM. They can take months or years to get right. Sure, in the long run they’ll be faster, but what is it that economist John Maynard Keynes said? “In the long run we’re all dead.”

Part of the problem is that most of the theoretical models analyze how algorithms behave when the data set grows very large. But even in the era of big data, we may not be dealing with a data set that’s large enough to enjoy all of the theoretical savings.

In these cases, it might be a good idea to toss together a sloppy algorithm, even if it’s potentially slow.

## 3. Using a separate database server

When it comes to software performance, speed matters. A few milliseconds on the web can be the difference between early retirement and a total flop. The common wisdom goes: To speed up communications between the layers of your software, put your database on the same machine as the software for packaging the results for the user. With your database code and presentation layer communicating quickly, you eliminate the latency of having to ping a separate machine.

Except it doesn’t always pay off, especially when the single machine can’t efficiently serve the needs of both the presentation and the database layer.

Machines that do a great job running databases are often much different from those running presentation software. To further complicate matters, the differences depend on the type and structure of database you are using. More RAM always helps, but it’s essential when indexes are involved. Big tables need much more RAM than a large number of little ones. If you plan to do many JOINS, you might be better off bucking the all-in-one trend and going with a separate database server.

When you put the database and the rest of the software together under one hood, that one machine is forced to be a jack-of-all-trades. It may be able to communicate with itself quickly, but it can’t be tuned to efficiently perform each of your code’s various tasks.

## 4. Using a big CMS hammer on a tiny nail

One of today’s trends is to strip down the work of a central hub and split it up to run as lightweight microservices. Instead of building one portal to all your data, you build dozens or perhaps hundreds of separate web services dedicated to answering specific queries and collecting specific data. Doing so allows you to create, debug, and deploy each service independently -- great for making iterative changes without having to upgrade a monolithic code base.

But using a big, fat content management system like WordPress or Drupal to do the same thing is another way to serve up JSON or XML data with a bit of reconfiguration. This may seem like a terrible idea at first glance, as the extra complexity of the CMS can only slow down the stack. But a CMS approach can also speed development and improve debugging. All of the data formatting and “content management” can serve the internal staff who are managing the system. Even if no users touch the fancy layers, it can still be a big help for the internal audience.

The extra overhead may be a pain, but it’s relatively easy to solve by adding more computing power to the back end.

## 5. Integrating display with data
O
ne of the cardinal rules of modern design is to split your project into at least three parts: data storage, decision making, and presentation. Such separations make it simpler to redesign any one part independently of the other two.

There are downsides, though, because separating the display from the data means that the application is constantly reprocessing the data to fit the current template for the display. Much of this is repeated if the template remains the same.

Lately, architects have been reworking data formats to make it easier for display code to process. The move to JSON data structures and JSON NoSQL databases is largely driven by the desire to deliver data in a format that is simpler for the browser to process. It’s not exactly mixing data with display code, but it’s moving them closer together.

Using a cache is often how the applications mix display code with the data. When data is mixed into the template, the result is stored back in the database to be served again and again.

## 6. Using a suboptimal foundation

It used to be that choosing the “wrong” architecture or strategy for your long-term growth goals meant imminent project death. These days, however, recovering from poor early choices can be relatively easy, as long as throwing more cloud machines at the problem remains a workable solution.

If your server stack is slow or your databases are getting bogged down, you can often simply turn up the dial and rent more machines. Then when the crowds dissipate, you can dial back the extra computing power. When extra machines cost mere pennies per hour, it’s no longer as catastrophic to make an architectural mistake.

Of course, not all errors can be fixed by throwing pennies at them. Some poor decisions lead to exponential blowups when the company grows. Those kinds of failures can quickly empty any wallet when the cloud meter is running. But simply choosing a stodgy database or an elaborate filter that’s merely twice as slow isn’t a deal breaker as long as it doesn’t compound.

The key is to avoid bottlenecks in the central, most crucial part of the design. Keeping the moving parts separate and independent helps ensure that they don’t interfere with each other and produce a deadly lockup. As long as the core architecture doesn’t produce gridlock, bad decisions can be covered up with faster hardware. It’s not pretty, but it’s often effective.

Consider Facebook, a company that began using PHP, one of the early tools for web applications that already felt a bit dated by the time Facebook launched. The unappealing issues, though, were ones that bothered programmers -- not users. For all the odd syntax and limited power, the approach was solid. Facebook has since spurred PHP development by creating the HHVM, a much faster version that inspired a rewrite of the PHP core. Now Facebook runs the old code much faster, and users don’t know the company settled on an early platform choice that still makes some programmers' eyes roll.

Choosing a passable solution is often cheaper than engineering a sophisticated new approach. Sitting everyone down to redesign software so that it runs smoothly and efficiently could cost a fortune. A smart programmer makes $200,000 a year -- but that can be more than millions of server hours at Amazon. Being smart often isn’t worth the trouble when more hardware is cheap and rentable by the hour.

## 7. Keeping dusty code in production

A team of managers once called me in to look at a fancy, modern web application developed with the latest ideas and the newest language (Java, at the time). The problem is that the old mainframe talking with monochromatic dumb terminals was so much faster that everyone who had to use the new code was complaining. Can’t we go back to the ’60s-era tech?

One of the new Java programmers even told me, in frustration, something like, “It’s not fair to compare us to the old green-screen app. We’re doing so much more.” By "more," he meant using fancy fonts, tasteful colors, and forms that fit into resizable windows. The same data was still moving from fingers to database, but the people answering the phones remembered how much faster it was to work with the garish green screens with their fixed-width fonts.

The latest software technology is not always an improvement. There’s a reason why hardware engineers chuckle that programmers exist to create the bazillion lines of new code to make sure the new hardware runs as slowly as the old. Otherwise there wouldn’t be a need for new hardware.

Some of the earnest programmers like to talk with serious tones about issues like “technical debt” and “continual refactoring.” They speak knowledgeably about the importance of investing in the refreshing of code. But at times all of the dreams of wiping the slate clean and rewriting everything turns into a nightmare.

It’s a tough call. If the old code is buggy or failing, rewriting is the only choice. But sometimes rebuilding an app simply to keep it current can be a big mistake. Sometimes you go backward and end up with a trendy architecture written in the latest language but filled with new, trendy bugs to go with it.