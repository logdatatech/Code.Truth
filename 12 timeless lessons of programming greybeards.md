# 7 timeless lessons of programming ‘graybeards’

Heed the wisdom of your programming elders, or suffer the consequences of fundamentally flawed code

In one episode 1.06 of the HBO series "Silicon Valley," Richard, the founder of a startup, gets into a bind and turns for help to a boy who looks 13 or 14.

The boy genius takes one look at Richard and says, “I thought you’d be younger. What are you, 25?”

“26,” Richard replies.

“Yikes.”

The software industry venerates the young. If you have a family, you're too old to code. If you're pushing 30 or even 25, you're already over the hill.

Alas, the whippersnappers aren't always the best solution. While their brains are full of details about the latest, trendiest architectures, frameworks, and stacks, they lack fundamental experience with how software really works and doesn't. These experiences come only after many lost weeks of frustration borne of weird and inexplicable bugs.

Like the viewers of “Silicon Valley,” who by the end of episode 1.06 get the satisfaction of watching the boy genius crash and burn, many of us programming graybeards enjoy a wee bit of schadenfraude when those who have ignored us for being “past our prime” end up with a flaming pile of code simply because they didn’t listen to their programming elders.

[ Learn Java from beginning concepts to advanced design patterns in this comprehensive 12-part course! ]
In the spirit of sharing or to simply wag a wise finger at the young folks once again, here are several lessons that can't be learned by jumping on the latest hype train for a few weeks. They are known only to geezers who need two hexadecimal digits to write their age.

## Memory matters

It wasn't so long ago that computer RAM was measured in megabytes not gigabytes. When I built my first computer (a Sol-20), it was measured in kilobytes. There were about 64 RAM chips on that board and each had about 18 pins. I don't recall the exact number, but I remember soldering every last one of them myself. When I messed up, I had to resolder until the memory test passed.

When you jump through hoops like that for RAM, you learn to treat it like gold. Kids today allocate RAM left and right. They leave pointers dangling and don't clean up their data structures because memory seems cheap. They know they click on a button and the hypervisor adds another 16GB to the cloud instance. Why should anyone programming today care about RAM when Amazon will rent you an instance with 244GB?

But there's always a limit to what the garbage collector will do, exactly as there's a limit to how many times a parent will clean up your room. You can allocate a big heap, but eventually you need to clean up the memory. If you're wasteful and run through RAM like tissues in flu season, the garbage collector could seize up grinding through that 244GB.

Then there's the danger of virtual memory. Your software will run 100 to 1,000 times slower if the computer runs out of RAM and starts swapping out to disk. Virtual memory is great in theory, but slower than sludge in practice. Programmers today need to recognize that RAM is still precious. If they don't, the software that runs quickly during development will slow to a crawl when the crowds show up. Your work simply won't scale. These days, everything is about being able to scale. Manage your memory before your software or service falls apart.

## Computer networks are slow

The marketing folks selling the cloud like to pretend the cloud is a kind of computing heaven where angels move data with a blink. If you want to store your data, they're ready to sell you a simple Web service that will provide permanent, backed-up storage and you won't need to ever worry about it.

They may be right in that you might not need to worry about it, but you'll certainly need to wait for it. All traffic in and out of computers takes time. Computer networks are drastically slower than the traffic between the CPU and the local disk drive.

Programming graybeards grew up in a time when the Internet didn't exist. FidoNet would route your message by dialing up another computer that might be closer to the destination. Your data would take days to make its way across the country, squawking and whistling through modems along the way. This painful experience taught them that the right solution is to perform as much computation as you can locally and write to a distant Web service only when everything is as small and final as possible. Today’s programmers can take a tip from these hard-earned lessons of the past by knowing, like the programming graybeards, that the promises of cloud storage are dangerous and should be avoided until the last possible millisecond.

## Compilers have bugs

When things go haywire, the problem more often than not resides in our code. We forgot to initialize something, or we forgot to check for a null pointer. Whatever the specific reason, every programmer knows, when our software falls over, it’s our own dumb mistake -- period.

As it turns out, the most maddening errors aren’t our fault. Sometimes the blame lies squarely on the compiler or the interpreter. While compilers and interpreters are relatively stable, they're not perfect. The stability of today’s compilers and interpreters has been hard-earned. Unfortunately, taking this stability for granted has become the norm.

It's important to remember they too can be wrong and consider this when debugging the code. If you don't know it could be the compiler's fault, you can spend days or weeks pulling out your hair. Old programmers learned long ago that sometimes the best route for debugging an issue involves testing not our code but our tools. If you put implicit trust in the compiler and give no thought to the computations it is making to render your code, you can spend days or weeks pulling out your hair in search of a bug in your work that doesn’t exist. The young kids, alas, will learn this soon enough.

## Speed matters to users

Long ago, I heard that IBM did a study on usability and found that people's minds will start to wander after 100 milliseconds. Is it true? I asked a search engine, but the Internet hung and I forgot to try again.

Anyone who ever used IBM's old green-screen apps hooked up to an IBM mainframe knows that IBM built its machines as if this 100-millisecond mind-wandering threshold was a fact hard-wired in our brains. They fretted over the I/O circuitry. When they sold the mainframes, they issued spec sheets that counted how many I/O channels were in the box, in the same way car manufacturers count cylinders in the engines. Sure, the machines crashed, exactly like modern ones, but when they ran smoothly, the data flew out of these channels directly to the users.

I have witnessed at least one programming whippersnapper defend a new AJAX-heavy project that was bogged down by too many JavaScript libraries and data flowing to the browser. It's not fair, they often retort, to compare their slow-as-sludge innovations with the old green-screen terminals that they have replaced. The rest of the company should stop complaining. After all, we have better graphics and more colors in our apps. It’s true -- the cool, CSS-enabled everything looks great, but users hate it because it’s slow.

## The real Web is never as fast as the office network

Modern websites can be time pigs. It can often take several seconds for the megabytes of JavaScript libraries to arrive. Then the browser has to push these multilayered megabytes through a JIT compiler. If we could add up all of the time the world spends recompiling jQuery, it could be thousands or even millions of years.

This is an easy mistake for programmers who are in love with browser-based tools that employ AJAX everywhere. It all looks great in the demo at the office. After all, the server is usually on the desk back in the cubicle. Sometimes the "server" is running on localhost. Of course, the files arrive with the snap of a finger and everything looks great, even when the boss tests it from the corner office.

But the users on a DSL line or at the end of a cellular connection routed through an overloaded tower? They're still waiting for the libraries to arrive. When it doesn't arrive in a few milliseconds, they're off to some article on TMZ.

## Algorithmic complexity matters

On one project, I ran into trouble with an issue exactly like Richard in "Silicon Valley" and I turned to someone below the drinking age who knew Greasemonkey backward and forward. He rewrote our code and sent it back. After reading through the changes, I realized he had made it look more elegant but the algorithmic complexity went from O(n) to O(n^2). He was sticking data in a list in order to match things. It looked pretty, but it would get very slow as n got large.

Algorithm complexity is one thing that college courses in computer science do well. Alas, many high school kids haven't picked this up while teaching themselves Ruby or CoffeeScript in a weekend. Complexity analysis may seem abstruse and theoretical, but it can make a big difference as projects scale. Everything looks great when n is small. Exactly as code can run quickly when there's enough memory, bad algorithms can look zippy in testing. But when the users multiply, it's a nightmare to wait on an algorithm that takes O(n^2) or, even worse, O(n^3).


https://www.infoworld.com/article/2891806/application-development/7-timeless-lessons-of-programming-graybeards.html  
\+
https://www.infoworld.com/article/3056600/application-development/5-more-timeless-lessons-of-programming-graybeards.html

# 5 more timeless lessons of programming 'graybeards'

Youth may be what HR wants, but nobody bangs out code like a longtime programming pro.

The HR departments and hiring managers in Silicon Valley have a challenge. They can’t ask an applicant’s age because their companies have lost brutal discrimination lawsuits over the years. Instead, they develop little tricks like tossing in an oblique reference to “The Brady Bunch” (“Marcia, Marcia, Marcia!”) and seeing if the candidate gets the joke. Candidates who chuckle are deemed a poor cultural fit and are tossed aside.

Alas, the computer industry has a strange, cultish fascination with new technologies, new paradigms, and of course, new programmers. It’s more fascination than reality because old tech never truly dies. Old inventions like the mainframe may stop getting headlines, but they run and run. As I write this, Dice shows more than five times as many jobs postings for the keyword "Cobol" (522) than "OCaml," "Erlang," and "Haskell" combined (11, 52, and 27, respectively).

The stories of age discrimination are common, as are the rationalizations. Younger programmers’ heads aren’t filled with old ideas, so they learn faster. Whippersnappers are more focused and diligent. They don’t suffer distractions, like having families, or at least their distractions keep them yoked to their PCs and smartphones.

Even if these are true -- there’s evidence they aren’t -- programming geezers have valuable wisdom you can’t absorb simply by watching a TED talk on YouTube or fast-forwarding through a MOOC. They understand better how computers work because they had to back when computers had front panels with switches. They didn’t have the layers of IDEs, optimizing compilers, and continuous integration to save their bacon. If they didn’t build it right from the beginning, it wouldn’t run at all. The young punks won’t know this for years.

## Assembler

Most people younger than 50 can’t recognize a statement like mov ah, 09h or cmp eax, ebx. Many probably think that computers naturally demand lots of curly brackets because the major languages use them to delimit blocks of code. Even those who understand that languages like Java or C must be translated into binary often have little to no experience crafting it.

Many older programmers spent their days writing assembler code, the name given to the human-readable version of raw binary machine code. Some could actually convert the assembly code by hand and turn it into hexadecimal bytes. The very best could then flip the toggle switches on the front panel to program the computers.

It’s not that writing assembler is great or essential. It’s a long slog filled with repetition and lots of opportunities to make sloppy mistakes. The compilers have become good enough to recognize complex patterns that can be optimized; in fact, some compiler creators like to brag that they can create better code than humans can.

That may be true, but the advantage of learning even a sliver of assembler is that you understand how a computer works. The higher-order languages may offer lots of quick shortcuts for standard operations, such as concatenating strings, but these can be a trap because programmers start to think that the plus operand (“+”) takes the same amount of time whether it’s adding two integers or concatenating two strings. It doesn’t. One operation takes dramatically longer, and people who understand assembly code and the way the JMP (jump) operation works are going to make the right decision.

Understanding how objects are packed in memory and loaded into the CPU when necessary is a big help in minimizing the copying and overcalculation that can produce slow code. Folks who grew up on assembler may not remember much about writing x86 code, but they still have instincts that tingle when they start to do something inherently slow. The whippersnappers don’t have these instincts, unless they train themselves through experience.

## Sounds and lights

A long time ago, a programmer told me he hated Unix. Why? He started out programming single-user microcomputers like the Altair or the Sol 20 that only ran one block of code at a time.

“A Unix computer will start running something else at any time,” he told me. “You’ll hear the floppy disks start up and you’ll have no idea why.”

This upset him because he was losing a powerful means of understanding what the computer is doing. No one really knows what’s going on in a modern computer. There are countless layers of software running on four or eight cores. Viruses and worms can live forever without the user noticing the lag.

Old programmers still watch for visual and auditory clues that help them understand and debug the code. They watch the light on the RJ-45 Ethernet jack that flickers when data is flowing. They listen to the hard disk and can hear when the disk starts to change tracks, an indication that something is either reading or writing to the disk. The really good ones can tell the difference between the paging that happens when memory is full and the sustained reading and writing that’s part of indexing.

The value of these clues are fading as the hard disks are replaced with solid-state drives and more and more data move wirelessly instead of through routers with blinking lights. But as long as the smartphones have little indicators that show when data is flowing, there will be value in sleuth skills like these.

## Bitbanging

In the good old days, the programmers would pack as many as eight different Boolean values into one byte. They flipped the individual bits because they didn’t want to waste any of them.

The modern data structures are incredibly wasteful. XML is filled with tags with long names, and each has a matching closing tag with an extra slash. It’s not uncommon to see modern XML files that are more than 90 percent fluff added to meet strict parsing rules.

JSON is considered an improvement because it’s a bit smaller, but only because there are no closing tags -- just curly brackets. There are still too many quotation marks on all the tags and strings.

The good news is that modern compression algorithms can often squeeze much of the fat out of data structures. But they can never get all of it. The graybeards know how to avoid putting it in from the beginning. That’s why code like MS-DOS 3.0 could run fast and light within a partition of no more than 32MB. Notice the modifier: no more than. That’s 32 million bytes and the maximum size of the disk partition.

That detail from MS-DOS 3.0 dates from the early 1980s, a time when the personal computer was already common and the computer revolution was well past its infancy. If you go back a bit more, the code from the 1970s was even leaner. The code from the 1960s was amazing.

## Binary mathematics

The operations for testing and flipping bits weren’t merely novelties for early programmers; they were necessities. Some operations were so slow that programmers had to look for any advantage they could find. The best was understanding that dividing by two was equivalent to shifting a binary number to the right, like dividing by 10 is the same as shifting a decimal number to the right.

Shifting all of the bits is a standard operation on CPUs, and it was often blazingly fast compared to basic division. The good programmers used this advantage to write faster code that didn’t need to wait for multiplication and division when a shift could do the same.

We’re losing the connection to powers of two. It used to be that designers would instinctively choose numbers that were powers of two because they would lead to greater efficiencies. Numbers like 512 or 4,096 appeared frequently because it was easier to work with limits that are powers of two.

## Little details add up

On many early processors, some operations took much longer than others. On the original 8086, dividing a number took anywhere from 80 to 190 times clock cycles, while adding two numbers took only three cycles. Even when the CPU could run at 5MHz, that could still make a big difference when doing the operation again and again.

Older programmers know that not every line of code or every instruction will execute in the same amount of time. They understand that computation is not free, and not every line of code is equivalent. Choose the wrong kind of operation and your machine will dramatically slow down.

People forget that choosing the wrong data type can also have consequences. Using a double or a long variable can still be slower on some chips. Using the wrong data structure can turn the program into sludge when you scale.