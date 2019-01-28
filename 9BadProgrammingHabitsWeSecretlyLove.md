# 9 bad programming habits we secretly love

https://www.infoworld.com/article/2992566/application-development/9-bad-programming-habits-we-secretly-love.html

Breaking the rules can bring a little thrill -- and produce better, more efficient code

We've all done it: snagged a cookie when mom wasn't looking, gone around Deadman's Curve a bit too fast. We've even let the car sit in a parking spot after the meter expires. Yes, we've all violated any number of the cardinal rules of programming, the ones that everyone agrees are bad. And we secretly liked it.

We've thumbed our nose at the rules of good programming, typed out code that is totally bad -- and we've lived. There were no lightning bolts from the programming gods. Our desktops didn’t explode. In fact, our code compiled and shipped, and the customers seemed happy enough.

[ Find out how to handle the real-world problems faced by developers, with InfoWorld's professional programmer's business survival guide. | Keep up with hot topics in programming with InfoWorld's Application Development newsletter. ]
That’s because bad programming isn't in the same league as, say, licking an electric fence or pulling the tail of a tiger. Most of the time, it works out. The rules are more often guidelines or stylistic suggestions, not hard-and-fast rules that must be obeyed or code death will follow. Sure, your code might be ridiculed, possibly even publicly, but the fact that you’re bucking conventions adds a little bit of the thrill to subverting, even inadvertently, what amounts more often than not to the social mores of pleasant code.

To make matters more complex, sometimes it's better to break the rules. (Shhhh!) The code comes out cleaner. It may even be faster and simpler. The rules are usually a bit too broad, and an artful programmer can improve the code by breaking them. Don’t tell your boss, but sometimes it makes sense to code your own way.

What follows is a list of nine rules that some may consider unimpeachable, but many of us break often, with both success and pleasure.

## Programming habit No. 1: Using goto

The prohibition on using goto dates to the era before many of the tools of structured programming even existed. If programmers wanted to create a loop or jump to another routine, they would need to type GOTO followed by a line number. After a few years, compiler teams let programmers use a string label instead of a line number. That was considered a hot new feature back then.

Some called the result “spaghetti code.” It was impossible for anyone to read your code later and follow the path of execution. It was a jumble of threads, forever tangled. Edsger Dijkstra banned the command with a manuscript drolly titled "Goto Statement Considered Harmful."

[ Learn Java from beginning concepts to advanced design patterns in this comprehensive 12-part course! ]
But absolute branching isn't the problem. It's the tangle that results. Often an artful break or return will offer a very clean statement about what the code is doing at that spot. Sometimes adding goto to a case statement will produce something that's simpler to understand than a more properly structured list of cascading if-then-else blocks.

There are counterexamples. The "goto fail" security hole in Apple's SSL stack is one of the best instances. But if we're careful to avoid some of the gnarly issues of case statements and loops, we can insert good, absolute jumps that make it easier for the reader to understand what's going on. We can put in a break or a return that is cleaner and more pleasing for everyone -- except perhaps the goto haters.

## Programming habit No. 2: Eschewing documentation

One friend of mine worked for a hard-nosed boss who never wrote any code but understood just enough to know that every function must include documentation. If the programmers didn’t include a comment, they must be punished. So my friend wired together an Eliza-like AI to his editor, and voilà, every function had a few lines of "documentation." The boss wasn't smart enough to understand that the lines meant nothing, so my friend was off the hook. His code was officially documented. I think he even got a promotion!

Many functions and even some classes are more or less self-documenting. Functions with names like insertReservation or cancelReservation or deleteAll don't need another line or three to explain what's going on. Choosing the right names for the function is often good enough. In fact it’s better than writing long documentation because the function names appear in other places in the code. The documentation is in only one place. Self-documenting function names improve every file where they appear.

There are cases when it's worse to have documentation. When the code is rapidly changing and the team is refactoring like crazy, documentation can diverge. The code says one thing, but the documentation is explaining what happened four or five revisions ago. This often happens at the top of the code where someone wrote a nice summary of what's supposed to happen. The refactoring team may be careful enough to fix the comments on the functions they change, but they may not even see the comments at the top of the file.

When the code and the text diverge, the comments become worthless and sometimes even dangerous. In cases like these, good, self-documenting code is better without comments.

## Programming habit No. 3: Jamming too much code on one line

One boss along my path to nirvana sent out a nasty email to the team. Suddenly, all of us must rewrite our code to follow very strict rules of style. The most dramatic requirement: Each action or step or clause must be on its own line. You couldn’t chain function calls together with dot syntax. You couldn’t have two or more clauses to the boolean in a branch statement. If you define a variable, put it on its own line. If you're doing a complex calculation, don't use parentheses. Put each fragment on its own line.

He had a point. His edict would make debugging easier. As you stepped through the code, the debugger would step from action to action. It wouldn’t get stuck on one line. It was easier to follow.

But boy did the code get long. The Return key on my keyboard wore out as I kept inserting lines. And I’m sure he bragged about how many lines of code his team was writing.

Alas, sometimes it makes it easier to declare a bunch of variables in one line. Sometimes it’s simpler to put all of the boolean clauses together -- everything is more compact. That means we see more logic on the screen without scrolling. It's easier to read, which means understanding comes faster. It’s that simple.

## Programming habit No. 4: Not declaring types

The folks who love typed languages have a point. We write better, more bug-free code when we add clear declarations of the data type of each variable. Pausing a moment to spell out the type helps the compiler flag stupid errors before the code starts to run. It may be a pain, but it helps. It’s a belts-and-suspenders approach to programming that stops bugs.

Times have changed. Many of the newer compilers are smart enough to infer the type by looking at the code. They can work backward and forward through the code until they can be sure that the variable must be a string or an int or something else. And if these inferred types don't line up, then they can raise an error flag too. They don’t need us to type the variables any more.

This means it's now easier to save a few bits by leaving off some of the simplest declarations. The code becomes a bit cleaner, and the reader is usually quite able to guess that the variable named i in a for loop is an integer.

## Programming habit No. 5: Yo-yo code

Programmers like to call it "yo-yo code." First the values are stored as strings. Then they're parsed into integers. Then they're converted back to strings. It's terribly inefficient. You can almost feel the CPU struggle under all the wasted load. Smart programmers who write fast code design their architectures to minimize the conversions. Their code runs faster because of their planning.

But believe it or not, sometimes it makes sense. Sometimes you have a whiz-bang library that does a bazillion intelligent things inside its proprietary black box. Sometimes the boss wrote a seven-figure check to license all of the genius inside that black box. If the library wants the data in strings, you give it to the library in strings even if you recently converted it into integers.

Sure, you could rewrite all of your code to minimize the conversion, but that would take time. Sometimes it’s OK for the code to run an extra minute, hour, day, or even week because rewriting the code would take even more time. Sometimes running up a technical debt like this is cheaper than building it right in the first place.

Sometimes the library isn't proprietary code, but code you wrote yourself long ago. Sometimes it's faster to convert the data one more time than rewrite everything in that library. So you go along and you write yo-yo code. It’s OK -- we’ve all been there.

## Programming habit No. 6: Writing your own data structures

One of the standard rules is that a programmer should never write code for storing data after completing the data structures course in their sophomore year. Someone else has already written all of the data structures we'll ever need, and their code has been tested and retested over the years. It’s bundled with the language and it’s probably free. Your code could only have bugs.

But sometimes the data structure libraries are a bit slow. Sometimes they force us into a structure that may be standard but wrong for our code. Sometimes the libraries push us into reconfiguring our data before we use the structure. Sometimes the libraries include belts-and-suspender protections with items like thread locking, and our code doesn’t need them.

When that happens, it's time to write our own data structures. Sometimes it's much, much faster. And sometimes it makes our code much cleaner because we don't include all of the extra code for reformatting the data exactly so.

## Programming habit No. 7: Breaking out of loops in the middle

Somewhere along the line, a rule-making group declared that every loop should have an "invariant," which is to say a logical statement that is true throughout the loop. When the invariant is no longer true, the loop ends. It's a good way to think about complex loops, but it leads to crazy prohibitions -- like forbidding us from using a return or a break in the middle of the loop. This is a subset of the rule forbidding goto statements.

This theory is fine, but it usually leads to more complex code. Consider this simple case that scans an array for one entry that passes a test:

```java
while (i<a.length){
   ...
   if (test(a[i]) then return a[i];
   ...
}
```  
The loop invariant lovers would rather we add another boolean variable, call it notFound, and use it like this:

```java
while ((notFound) && (i<a.length){
...
if (test(a[i])) then notFound=false;
...
}
```

If this boolean is well-named, it’s a great piece of self-documenting code. It may make it easier for everyone to understand. But it’s also added complexity. And it means allocating another local variable and clogging up a register that the compiler may or may not be smart enough to fix.

Sometimes a goto or a jump is cleaner.

## Programming habit No. 8: Using short variable names (but **i** and **x** and **and** make sense)

Edgar Allan Poe used to say that every word in a story should build to a single conclusion. By this, he meant that every word must say something to the reader. The coding rules insist on the same. Each variable name should explain what it's doing and why it's there. This is taken to insane lengths by Java programmers who’ve embraced the idea of using camel case variable names to tell elaborate details about what the variable does. Some programmers write variable names that have five, six, or even more words glued together.

But sometimes it's easier to use an inscrutable one-letter variable. Sometimes it's simpler to use only i or j for the iterators in loops. Sometimes it's simpler to use a for an array and l for a list, even if it's indistinguishable from the number 1.

Yes, an earlier part of this article encouraged self-documenting code over long comments. In this case, a one-letter variable name is self-documenting. The letter i is the universal iterator. The smart programmer will know immediately.

## Programming habit No. 9: Redefining operators and functions

Some of the most fun languages let you do truly devious things like redefine the value of elements that look like they should be constant. Python, for instance, lets you type TRUE=FALSE, at least in Version 2.7 and before. This doesn't create some kind of logic collapse and the end of the universe; it simply swaps the meaning of TRUE and FALSE. You can also play dangerous games like this with C preprocessors and some other languages. Still other languages let you redefine operators like the plus sign.

This is a stretch, but there will be points within a big block of code when it’s faster to redefine one or more of these so-called constants. Sometimes the boss wants the code to do something entirely different. Sure, you could work through the code and change every occurrence, or you could redefine reality. It can make you look like a genius. Instead of rewriting a huge library, you simply flip a bit and it does the opposite.

Perhaps it’s good to draw the line here. You shouldn’t try this at home, no matter how clever and fun it can be. This is too dangerous -- really ... honest.