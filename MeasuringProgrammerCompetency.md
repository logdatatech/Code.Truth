# Measuring programmer competency

One way is to ask them which books they have read to improve their craft. [BookShelf Porn For Programmers](./BookShelfPornForProgrammers.md) if they haven't read more than three of these books it's a **red flag**.

<!-- https://softwareefficiency.wordpress.com/2015/09/20/measuring-programmer-competency/ -->

As programmers it is easy to be arrogant about our skills. A lot of programmers have a prima donna complex. With a lot of consultants it even seems to be a requirement. Nobody likes a consultant that is uncertain. Right?

In my search to some way of measuring how good a programmer I am, I found this exquisite website: Programmer competence matrix.

Let’s evaluate if this is a sufficient measure.

> DATA STRUCTURES  

Medium: Able to explain and use Arrays, LinkedLists, Dictionaries etc in practical programming tasks

High: Knows space and time tradeoffs of the basic data structures, Arrays vs LinkedLists, ( array list vs linked list explained here)

Able to explain how hashtables can be implemented and can handle collisions, priority queues and ways to implement them etc.

Pro: Knowledge of advanced data structures like B-trees, binomial and fibonacci heaps, AVL/Red Black trees, Splay Trees, Skip Lists, tries etc.

While I’ve studied these data structures 10 years ago at university which would make me a pro according this measure I’ve never had to choose, use (by choice) or explicitly implement these datastructures. It would have looked great on my résumé but sadly that day is yet to come. 

> ALGORITHMS

Medium: Basic sorting, searching and data structure traversal and retrieval algorithms

High: Tree, Graph, simple greedy and divide and conquer algorithms, is able to understand the relevance of the levels of this matrix.

Pro: Able to recognize and code dynamic programming solutions, good knowledge of graph algorithms, good knowledge of numerical computation algorithms, able to identify NP problems etc.

If you’d like to train your mastery of algorithms, I’d like to reference project euler. This is an exquisite exercise of your knowledge of algorithms and math. Sadly in a professional environment I seldom see problems that need this kind of expertise. 

> SYSTEMS PROGRAMMING

Medium: Basic understanding of compilers, linker and interpreters. Understands what assembly code is and how things work at the hardware level. Some knowledge of virtual memory and paging.

High: Understands kernel mode vs. user mode, multi-threading, synchronization primitives and how they’re implemented, able to read assembly code. Understands how networks work, understanding of network protocols and socket level programming.

Pro: Understands the entire programming stack, hardware (CPU + Memory + Cache + Interrupts + microcode), binary code, assembly, static and dynamic linking, compilation, interpretation, JIT compilation, garbage collection, heap, stack, memory addressing…

I have to confess, I love system programming details and I love knowing the details. This comes in really useful when debugging a hard to find problem. As development is migrating away from the machine the amount of programmers that know how the hardware works diminishes. 

> SOURCE CODE VERSION CONTROL

Medium: VSS and beginning SVN user

High: Proficient in using SVN features. Knows how to branch and merge,use patches setup repository properties etc.

Pro: Knowledge of distributed VCS systems. Has tried out Bzr/Mercurial/Darcs/Git

This really isn’t something the developer has a lot of options in. Either their employer uses proper version control or they don’t.

> BUILD AUTOMATION

Medium: Knows how to build the system from the command line

High: Can setup a script to build the basic system

Pro: Can setup a script to build the system and also documentation, installers, generate release notes and tag the code in source control

I used to be the release manager. I had to do all of these tasks. I must say knowing how to do this doesn’t really add to programming expertise.

> AUTOMATED TESTING

Medium: Has written automated unit tests and comes up with good unit test cases for the code that is being written

high: Has written code in TDD manner

Pro: Understands and is able to setup automated functional, load/performance and UI tests

I find that writing good unit tests is important for any software developer. Load/performance tests are more of the task of a good quality engineer.

> PROBLEM DECOMPOSITION

Medium: Able to break up problem into multiple functions

High: Able to come up with reusable functions/objects that solve the overall problem

Pro: Use of appropriate data structures and algorithms and comes up with generic/object-oriented code that encapsulate aspects of the problem that are subject to change.

It should also be mentioned that only abstractions are made where they are needed. A lot of time has been wasted on abstract clutter that nobody understands. 

> SYSTEMS DECOMPOSITION

Medium:Able to break up problem space and design solution as long as it is within the same platform/technology

High: Able to design systems that span multiple technologies/platforms.

Pro: Able to visualize and design complex systems with multiple product lines and integrations with external systems. Also should be able to design operations support systems like monitoring, reporting, fail overs etc.

This seems to be pushing the boundaries of what a software analyst should do. Mostly monitoring, reporting and fail over is merely choosing for the right product, so to me it isn’t sure that this is a skill. 

> COMMUNICATION

Medium: Peers can understand what is being said. Good spelling and grammar.

High: Is able to effectively communicate with peers

Pro: Able to understand and communicate thoughts/design/ideas/specs in a unambiguous manner and adjusts communication as per the context

I know very few programmers that would succeed in this part. The only question is how do you train/verify this? This seems to be more of a job for an analyst. 

> CODE ORGANIZATION WITHIN A FILE

Medium: Methods are grouped logically or by accessibility

High: Code is grouped into regions and well commented with references to other source files

Pro: File has license header, summary, well commented, consistent white space usage. The file should look beautiful.

I barely see programmers that have time to add license headers and a summary to each file. I’d love to have this though. Count me in.

With the IDEs these days files can be formatted automatically. So extra credit for people who know the format button. Code grouping is also fairly hard. You can group functions according to different aspects. That’s why good IDEs have proper navigation tools for that.

> CODE ORGANIZATION ACROSS FILES

Medium: Related files are grouped into a folder

High: Each physical file has a unique purpose, for e.g. one class definition, one feature implementation etc.

Pro: Code organization at a physical level closely matches design and looking at file names and folder distribution provides insights into design

As for one class definition in one file, this is required in some languages like java. Most of this depends on what is imposed from higher end. Programmers tend to keep these habits.

> SOURCE TREE ORGANIZATION

Medium: Basic separation of code into logical folders.

High: No circular dependencies, binaries, libs, docs, builds, third-party code all organized into appropriate folders

Pro: Physical layout of source tree matches logical hierarchy and organization. The directory names and organization provide insights into the design of the system.

Programmers don’t get a lot of practice here. They are to adopt the company standard.

> CODE READABILITY

Medium: Good names for files, variables classes, methods etc.

High: No long functions, comments explaining unusual code, bug fixes, code assumptions.

Pro: Code assumptions are verified using asserts, code flows naturally – no deep nesting of conditionals or methods.

To me this is spot-on. In my humble opinion **this is the most important aspect**.

> DEFENSIVE CODING

Medium: Checks all arguments and asserts critical assumptions in code

High: Makes sure to check return values and check for exceptions around code that can fail.

Pro: Has his own library to help with defensive coding, writes unit tests that simulate faults

Defensive coding is not taught by most programming courses and your skill may depend on the type of programmers you encounter in your career. Defensive programming is more than checking arguments, it also means designing classes so it makes incorrect use hard. 

> ERROR HANDLING

Medium: Basic error handling around code that can throw exceptions/generate errors.

High: Ensures that error/exceptions leave program in good state, resources, connections and memory is all cleaned up properly.

Pro: Codes to detect possible exception before, maintain consistent exception handling strategy in all layers of code, come up with guidelines on exception handling for entire system.

> IDE

Medium: Knows their way around the interface, able to effectively use the IDE using menus.

High: Knows keyboard shortcuts for most used operations.

Pro: Has written custom macros

What is also a plus is knowing all the features of your IDE. With the modern IDEs this may not be as obvious as it may seem.

> API

Medium: Has the most frequently used APIs in memory

High: Vast and In-depth knowledge of the API

Pro: Has written libraries that sit on top of the API to simplify frequently used tasks and to fill in gaps in the API.

Knowing API details by heart has been obsoleted by auto-completion.(unless of course you haven’t discovered auto-completion yet)

> REQUIREMENTS

Medium: Come up with questions regarding missed cases in the specification

High: Understand complete picture and come up with entire areas that need to be specified

Pro: Able to suggest better alternatives and flows to given requirements based on experience

This is a nice job description of an analyst. Should every developer have analyst skills?

> SCRIPTING

Medium: Batch files/shell scripts

High: Perl/Python/Ruby/VBScript/Powershell

Pro: Has written and published reusable code

All programmers should be able to script, but the language doesn’t matter. Most scripting languages can be learnt in no time.

> DATABASE

Medium: Knows basic database concepts, normalization, ACID, transactions and can write simple selects

High: Able to design good and normalized database schemas keeping in mind the queries that’ll have to be run, proficient in use of views, stored procedures, triggers and user defined types. Knows difference between clustered and non-clustered indexes. Proficient in use of ORM tools.

Pro: Can do basic database administration, performance optimization, index optimization, write advanced select queries, able to replace cursor usage with relational sql, understands how data is stored internally, understands how indexes are stored internally, understands how databases can be mirrored, replicated etc. Understands how the two phase commit works.

> LANGUAGES WITH PROFESSIONAL EXPERIENCE

Medium: Imperative, Object-Oriented and declarative (SQL), added bonus if they understand static vs dynamic typing, weak vs strong typing and static inferred types

High: Functional, added bonus if they understand lazy evaluation, currying, continuations

Pro: Concurrent (Erlang, Oz) and Logic (Prolog)

How often does a professional environment need someone that is proficient in prolog or any other functional language? I’ve not encountered it yet.

> PLATFORMS WITH PROFESSIONAL EXPERIENCE

Medium: 2-3

High: 4-5

Pro: 6+

Does having more than 2 years of experience really add much? I doubt it.

> YEARS OF PROFESSIONAL EXPERIENCE
Medium, High, Pro: 2-5,6-9,10+

Experience on itself doesn’t say much. I’ve met very good juniors and very mediocre seniors. Programmers that stick with the same job for 10+ years rarely have a wide area of knowledge.  

> KNOWLEDGE OF UPCOMING TECHNOLOGIES

Medium: Has heard of upcoming technologies in the field

High: Has downloaded the alpha preview/CTP/beta and read some articles/manuals

Pro: Has played with the previews and has actually built something with it and as a bonus shared that with everyone else

This one gives an indication that the developer is interested in the latest trends and technology. Be aware though of the golden hammer. Some people may use new tools at the wrong place just to gain experience.

> Conclusion

This way of measuring competency is broad and the most accurate way I’ve seen so far.

It allows programmers to objectively reflect on their capacities.

For the employer it should be a question on what matters most and apply weights.

If all recruiters could use this, rather than flinging a list of technologies, then there would be no need for heaven, we’d already be there.
