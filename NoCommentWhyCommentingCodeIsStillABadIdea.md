
<!-- https://visualstudiomagazine.com/articles/2013/07/26/why-commenting-code-is-still-bad.aspx -->

# No Comment: Why Commenting Code Is Still a Bad Idea

## More on code commenting:

A few weeks back, my column on [the value of comments](./ToCommentOrNotToComment.md) in code caught a lot of comments itself. To a certain extent, I feel like Dirty Harry in Magnum Force: "I'm afraid you've misjudged me"…but not totally. The column's content seemed so obvious to me that it was hard, initially, for me to figure what people were objecting to (when I wrote the column, I thought I was just repeating conventional wisdom). But some readers did object: I was called an idiot, an incompetent, unprofessional, ignorant, an intellectual, and, at least once, threatened with physical violence.

## What I Got Right (and Wrong)

I did get at least one thing wrong: I felt that a column that listed off the reasons for not writing comments should be called "Why You Shouldn't Comment Code." I even began the column with two paragraphs on when commenting code makes sense before I launched into when they're a bad idea. I've come to realize that the column's title sent a different message: people read it as "Why You Shouldn't Comment Code At All" and then skipped over the paragraphs on when comments made sense. I suspect that the blurb under the title ("If you are documenting code, try to stop!") didn't help. In retrospect, I can see how the article title could be read as an order to not write comments.
But excepting the title, the rest of the article still makes sense. That column was driven by three fundamental facts:

Writing and then maintaining comments is an expense.
Your compiler doesn't check your comments so there is no way to determine that comments are correct.
You are, on the other hand, guaranteed that the computer is doing exactly what your code is telling it to.
Based on those three facts, my claim is simple: your code is going to communicate to the computer and should also communicate to whoever maintains the code (who may be you, three months from now). To make life easier for the next developer, code should be written and rewritten to be as obvious as possible. What's left for comments to do is explain what the compiler doesn't have access to: why the code is there. Adding comments to explain how your code does its job -- which (I think) some readers were recommending -- is not the solution. It's just adding more cost.

I will allow that there is one exception: there are times when you're forced to write clever, rather than obvious, code to achieve some goal (usually better performance). In that case a comment about how the code works (really, a kind of apology to the next programmer) is a good idea. However, that's a sufficiently unusual occurrence that I omitted it. To my mind, more often than not, that justification just provides an excuse for not writing better code.

Arguing with Readers

Some readers seemed to think that I was advocating "no comments at all" despite the first two paragraphs. Many of those readers, after saying I had it all wrong, went on to say that you have to include comments about why the code is there. Well, exactly. Glad we agree.

Others recalled occasions when a comment really helped them out. First, I'd want to know if that helpful comment described how the code did its job (bad) or described why the code was there (good!). But I suspect that those people are doing what psychics ask their customers to do: count the hits and forget the misses. I suspect that the reason those readers remember that helpful comment is because it's so unusual.

Some readers seem to feel that I wanted to discard all documentation and referenced specifications and requirement documents as useful tools in understanding code. Since these documents exist before the code is written, I have nothing to say about them (at least, not right now).

Some readers suggested that comments provided insight into what previous programmers thought their code was doing. I don't care what those programmers thought their code was doing -- I only care what their code actually does (though I do care why the previous programmers thought the code was necessary). Other readers suggested that comments could be used as a training tool for less experienced developers -- I think that's a really inefficient way to train programmers (and, given how often comments are wrong, actually counter-productive).

Other readers simply ignored the discussion in the article and asserted that "comments are good." Hard to argue with that, of course.

## Adding Value

So, here's the deal: there are five kinds of work: 

- value-added work
- necessary work
- rework
- not working
- wasted work

Value-added work is decided by the customer or client -- what they think of as adding value to their lives/work. Having a working application that supports the business is a value-added item.

Rework (doing it again because you got it wrong the first time)

not working (vacations, waiting for input), and wasted 
work (work whose output is thrown away) are all valueless kinds of work and should be minimized.

Well, maybe not the vacations -- but everything else.

Which leaves necessary work. Necessary work is the work that you must do in order to do the work that your customer/client values.

Documentation is necessary work. While it adds value to our lives, our customers/clients/users would be just as happy if we could deliver the application without doing it. Documentation is necessary to get the job done, but does not, in our customers' opinion, add value. Since customers pay the bills, their view is the only view that matters

We should do all the necessary work we have to do -- and not one bit more. Or, to put it another way, we should do as little necessary work as we can to spend more time on delivering value to our users.

Documenting and, especially, rewriting documentation to keep it in sync with code, is a task that we should, every year, be trying to do less of. Commenting the "why" and not the "how" is a good first step.
