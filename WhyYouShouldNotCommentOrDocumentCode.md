
<!-- https://visualstudiomagazine.com/articles/2013/06/01/roc-rocks.aspx -->

# Why You Shouldn't Comment (or Document) Code

It isn't news that developers don't like documenting their code. But you have good reason not to. And if you are documenting code, try to stop! It's not too late.

Recently I was intrigued by Joe Kunk's On VB column about commenting code. I especially liked Kunk's comment that: "It's important to communicate what the code should be doing." I thought that was the best description of what comments should do that I'd read in a very long time.

I also think it's the only thing comments should do. Comments should explain the **"why"** of the code and stop there. A great comment explains what purpose the developer felt that method or class should fulfill. That comment could be extended to include a description of how inputs and outputs of a method are related, and a list of expected side effects. (A "side effect" is any result from executing the code that isn't reflected in the values that the code returns; deleting a record and sorting an array are all examples of side effects.) But that's as far as any comment should go.

## The Problem

What comments should never, ever do is explain how the code does its job. To paraphrase "The Elements of Programming Style" (Computing Mcgraw-Hill, 1978): Comments that describe how the code achieves its goals are just a second version of the code. As a second version, they either agree with the code and add no value or they disagree with the code and provide negative value. This is why developers sometimes find MSDN documentation frustrating: It describes what you'd need to know in order to recreate a framework class but often completely omits the "why" for using that class.

Furthermore, getting comments "to agree with the code" is almost impossible. It would mean, at the very least, that the comments describe the code both accurately and completely. Further, as the code evolves over time, that level of accuracy has to be maintained -- the comments must continue to be both accurate and complete. And that's just to prevent the code from having a negative value. But the real problem is that, even if that miracle of accuracy and completeness were achieved, there's no way for someone reading the comments to know that accuracy and completeness have been achieved.

Let's say you modify some application based on the comments you find in the code. You then put your changes into production, and discover that there was some essential component that the comments failed to mention. And, because you didn't know that, your change causes irreparable harm. When your boss comes around for an explanation, is he likely to accept, "Well, the comments said that the change was OK"? From the perspective of job security alone, the only safe thing for you to do is to ignore comments about how the code works and find out what the code actually does. A maintenance programmer is as much detective and historian as code author.

What can't be determined by reading the code -- and what's likely to remain constant as the code evolves -- is the reason that the code exists. That should be documented. Nothing else.

## The Solution

If you're going to have to read the code to find out what's really going on, then your goal should be to write **Really Obvious Code (ROC)** rather than **Write-Only Code (WOC)**. WOC is, effectively, a love letter between the coder and the computer -- full of inside jokes and pet phrases that are meaningless to those not part of the relationship.

Yet you sometimes do end up creating WOC. The problem is that when you start writing code, you often don't know where you're going to end up -- you get smarter about the problem as you work with your code. (Wouldn't it be sad if that wasn't true?) As a result, some of your original decisions turn out to be … unfortunate. Your final code may, for example, be more complex than is necessary or use variable/parameter names that will lead someone reading your code astray.

The friend of ROC is refactoring: coming back after you finally and fully understand the code and rewriting it to make the code read better -- but without adding or changing functionality. The problem is that you'd have to be an idiot to do that.

You have a bug-to-code ratio: x number of changes lead to y number of bugs.

Refactoring your code to make it better just gives you a whole new opportunity to introduce a bug. And, if your boss asks why you made a change that introduced a bug and you say that it wasn't to make the code run faster or to eliminate some problem … Well, what sort of shape is your resume in ?

Refactoring is only reasonable if you're doing test-driven development (TDD).

With TDD, you're one click and a few seconds away from re-executing all of your tests to prove that your code still does what it did before you made it "better." And if one of your tests fails, you have choices: you can fix the failure, or click undo a couple of times to back out of your change. (Or just skip checking your code back in -- you did check your code in before starting to refactor it, didn't you?)

This argument can be extended to most of the technical documentation that's produced around software development projects. Most of it is never used because developers recognize that the documentation is probably not accurate, complete or up-to-date. And, even if the documentation did meet all of those criteria, there's no way for a developer to tell. It's safer to look at the reality of the executing code.

The technological partner to ROC (refactoring) and TDD are better tools to discover the reality of what your applications are doing. The solution is not to have programmers write documentation, but to get better analysis tools (besides, programmers are really, really bad at documenting).

Ignoring end-user documentation, documentation is, at best, a necessary task rather than a value-added task. As a result, reducing the time spent on documentation frees up time for value-added tasks. Your goal as a software developer should, therefore, be threefold: Reduce the amount of documentation you produce; adopt tools and practices that generate ROC; and adopt analysis tools that will make it easier to discover the reality of your applications.

One last note: To be honest (and don't tell anyone about this), in my heart of hearts I suspect that I believe that anyone who hasn't read "The Elements of Programming Style" shouldn't be allowed to write code. There are people who say I'm too judgemental -- but they're just wrong.
