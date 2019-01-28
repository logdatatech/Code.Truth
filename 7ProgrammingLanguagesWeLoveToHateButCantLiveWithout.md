# 7 languages we love to hate but can not live without

<!-- https://www.infoworld.com/article/3072163/application-development/7-programming-languages-we-love-to-hate-but-cant-live-without.html -->

Tools masquerading as languages, maddening syntax, dusty code that won’t die -- here's what has us shaking our fists

The well-meaning advice to not carry a grudge certainly didn’t come from anyone who’s wrestled with a computer for a living. Toil for anytime with the infernal logic of a programming language and you’ll know the horrors of the inky void where the worst bugs dwell.

Sure, everyone loves a computer language when they first encounter it. And why wouldn’t we, with all those “hello world” examples that show how powerful the language can be in three lines of code. Programming languages are defined to be implicitly logical, but that doesn’t mean they spread logic everywhere they go. A pleasant barkeep may make the lives of everyone at the bar happier. A brave firefighter radiates bravery. But the logical mechanisms of programming languages often breed illogic, confusion, and doubt.

It’s not, well, logical to say that languages are -- Spock pause -- illogical, but we say it anyway because we know that logic has its limits. From Gödel and Turing, we’ve learned that logical mechanisms have edges where scary things occur. Sure, maybe it’s our own fault, we humans, for misusing or misprogramming. But if the programming languages force our brains into weird yoga poses, it’s hard not to blame them for our ills.

And we often can’t do anything about it. The installed base may be too large for us to jettison the language that irks us. The boss may love a stack so much he can’t hear the screams coming from the cubicle farms. The cruel truth is that there may be no better options. We’re already using the best tools that humans can build.

Following are seven programming languages we love to hate but can’t live without.

## Language we love to hate: C

There are so many issues with a language that might better be called “portable assembler” than a full computer language. Does anyone like writing separate header files? Has anyone used the preprocessor for something elaborate without going slightly mad?

In theory, we’re supposed to be able to use the power of the pointer arithmetic to do superclever feats, but does anyone risk doing more than allocating data structures? Is it even a good idea to be too clever with pointers? That’s how code starts to break. If you’re able to be clever, it often requires writing a very long comment to document it, pretty much sucking up all the time you saved being clever. Can anyone remember all the rules for writing C code to avoid adding all the possible security holes, like buffer overruns?

But we have no choice. Unix is written in C, and it runs most cellphones and most of the cloud. Not everyone who writes code for these platforms needs to use C, but someone has to stay current with the asterisks and curly brackets, or else everything will fall apart. Then there are the device drivers and other embedded programs. Someone has to shoulder the load of keeping the Linux/Unix code base moving forward.

## Language we love to hate: JavaScript

JavaScript’s creators tried to make something modern. It’s too bad that in their cleverness they’ve forever doomed us to a life of counting curly brackets, square brackets, and parentheses -- while ensuring that they’re properly nested. Between the anonymous functions, the closures, and the JSON data structures, our pinkies get a real workout hitting those keys.

Then there are the weird details. If x is a string that holds the character for 1, then x+1 will produce the string 11 and x-1 will produce the number zero. Does anyone remember the difference between false, null, NaN, and undefined? They sound similar, but why does JavaScript have all four of them? And why don’t they behave consistently?

It doesn’t matter how much we complain. The Internet, the World Wide Web, and a bazillion browsers aren’t going anywhere. Then the clever Node.js team came along and forced us to write JavaScript on the server. Holding out on principle will last a few seconds until we need to check our email or buy something. We’ll run JavaScript for a long time.

## Language we love to hate: PHP

It’s not really a computer language. It’s more of a tool for adding a bit of smarts to static HTML. You can store information in a database and concatenate it with static tags. There might be a few more features, but it seems like all we do with PHP is glue together strings we grab from a database.

Arguing about toyish code or baby syntax isn’t worth the trouble. Most of the Web is built with PHP. Between WordPress, Joomla, and Drupal, most of the content on the Web is delivered through PHP code. Then there’s a little thing known as Facebook that was written in PHP and continues to suck up a larger and larger percentage of the time of people “on the Web.” We should be happy that Facebook built the HipHop Virtual Machine, inspiring Zend to create PHP 7.0. These new PHP engines are often twice as fast, an irresistible speed bump that will save millions in electricity and ensure we’ll write PHP long into the future.

## Language we love to hate: Cobol

Cobol began in 1959, long before most of us were born. It should be obsolete with its complex syntax filled with hundreds of restricted words. Yet the Cobol lovers keep generating new versions, borrowing ideas from other languages, and bolting them onto a frame that’s almost 60 years old. Did you know there’s something called Cobol 2014? It includes dynamic tables, an idea that people have been trying to get into the language since 2002. That’s not all that’s new. Did you think it died in the ’70s? You are so wrong.

We may have better tools for writing business logic to manipulate databases, but no one seems to bother because it’s easier to buy a bigger computer and keep the Cobol code running. As I type this, there are 543 jobs listed on Dice.com with the word “Cobol” in them. There are Cobol jobs in insurance companies and defense contractors everywhere. The early adopters of mainframes still use Cobol -- and get the job done. Computer scientists may recoil in horror, but as long as customers are lining up, the bosses will say, “If it ain’t broke, don’t fix it. Just buy another mainframe.”

## Language we love to hate: XSLT

Everyone starts off loving XSLT, a functional language for transforming XML. It’s a clever solution that works very well when you need to extract bits and pieces of large XML documents. But once the boss asks for something more complex than a simple search and replace, the development bogs down. The language is explicitly functional, and soon we discover that when the documentation says “variable,” it is using the word like an algebra teacher not a programmer. Ponder this Zen-like sentence from XSLT expert Bob DuCharme: “XSLT variables actually have a lot more in common with constants in many programming languages and are used for a similar purpose.” If you want to use a variable that behaves like a variable in other computer languages -- that is, it can change -- you better be very clever.

XML may be losing ground to more efficient data formats like JSON, but it’s still a powerful foundation for many big data processors. You don’t need to use XSLT. You can always write basic code that parses the text itself. However, writing all that code to parse the XML can be more work than grokking the XSLT structure.

## Language we love to hate: Java

The virtual machine and the libraries may date from the ’90s, but the syntax is stuck in the 1970s when C was created. The automatic memory management seems like a big step forward until your code decides to take a knee while the garbage collection takes control. The Android developers exchange tips on when to politely request a garbage collection in advance to ensure that the garbage collector doesn’t start up in the middle of an important event, like a phone call to 911.

Java programmers have complained for a long time about many issues, some of which have been fixed or at least addressed by Oracle. But this creates a new problem. Some of the newer code and libraries can’t work with the old VMs. I spent a day trying to wrangle java.lang.UnsupportedClassVersionError but could not find a permanent solution. It’s almost as if each version of Java after 1.4 is a different language.

None of these issues matter. Java is a foundation for the Web and mobile phones. It’s the first language taught in many high schools. The collection of libraries is deeper and more valuable than almost any other language. Why would anything use anything else?

## Language we love to hate: Python

It’s a modern language that the younger kids dig. The punctuation is sparse, and the code looks a bit cleaner. What’s not to love? Well, there’s the gap between Python 2.7 and 3.0. It was the only choice they had for moving the language forward, but the leap is large enough that you need to keep track of which syntax you’re using. We will forever be checking to see which version of Python is installed.

And how many people like counting all of the spaces used to indent blocks of code? Counting curly brackets is painful, but counting whitespace requires a monospace editor.

None of this matters because the soft science crowd has fallen for Python with all the warm, fuzzy emotions that kept them out of the hard sciences. Biologists and economists think Python is the only thing. Some even propose requiring Python code in new prospectuses for stocks and bonds so that investment bankers will be able to bamboozle us with Python instead of fractured lawyer-speak.

The good news is that It’s easier to read Python than the so-called English coming from the fingers of lawyers. That’s an improvement -- even if it means counting all of those spaces. The bandwagon has left the station, and it’s full of soft scientists.