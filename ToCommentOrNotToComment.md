
<!-- 
https://visualstudiomagazine.com/articles/2011/01/06/to-comment-or-not-to-comment.aspx -->

# To Comment or Not to Comment

> On VB columnist Joe Kunk explores the benefits and drawbacks of commenting source code, and finds that the answer is not as clear cut as many might think.

To badly paraphrase Shakespeare's Hamlet, "To Comment or Not to Comment, that is the question". There is a surprising amount of passionate debate within the developer community regarding the usefulness or desirability of comments in production source code. Should source code include significant comments or none at all or something in-between? In this article I examine the comments debate from a language-independent viewpoint. No matter what your favorite development language, the role of source code comments is something you should carefully consider.

In the following discussion, *comments are defined as those lines of text added to the source code following a specific language token to indicate non-functional text, explicitly ignored by the compiler or interpreter.* Forms of comments that are meant to provide some meaning such as compiler directives or metadata are outside the scope of this article.

## Everyone Carefully Comments Their Code, Right ?

At first glance, it seems so simple. Developers should comment their source code so that the code's intent is clear to the next developer or even to the same developer at a later date.

Most professional developers have experienced pulling up their own source code months later and felt the surprise of seeing strangely unfamiliar code and asking themselves the question

> "Why did I do that ?"

As computer science students, we were graded on the quality of our comments almost as much as the correctness of our code. High quality comments were the sign of a professional developer and comment free code was evidence of a rank amateur or someone who had spent too many hours at the bar the night before. Comments were among the universal truths of software development, as critical as proper requirements definition and effective testing.

Imagine my shock when Paul Kimmel, author of multiple computer books and a long-time technology columnist, told me that he rarely if ever comments his source code. His stated approach is to write only very small, well-named methods that are so self-evident in their purpose that comments are unnecessary in his opinion. Since then I have heard statements like "Comments are evil," "No good comment goes unpunished," and similar disparaging remarks.

Let me try to distill the debate to three pro-comment and three anti-comment points:

### Pro-Comment Point #1: It's important to communicate what the code SHOULD be doing

Source code must follow the syntactic tenants of the computer language. While language designers make significant efforts to define a readable syntax, at its core the language syntax exists for the compiler or interpreter and not the developer. Thus, comments are required to communicate the intent of the source apart from its functionality. When reading source code, it is extremely difficult to be absolutely certain of what the code is doing, as well to be certain as to what the original author intended. Comments should clearly communicate the developer's intent and if needed, an explanation as to how the source code algorithm accomplishes that intent.

### Pro-Comment Point #2: Comments show respect for the next developer to read your code

The Golden Rule applies in source code as well; do unto the next developer as you would have them do unto you. Source code should be written in the way that you yourself would most like to encounter unfamiliar code. It should be well-structured with a clear logic flow, and be both efficient and effective. Comments enhance the readability of the code, so that its intent and approach are immediately apparent with a clean appearance.

### Pro-Comment Point #3: Comments indicate potential problem areas to avoid

Comments should mention factors that may be of concern for the developer or tester. Boundary conditions, valid argument ranges, and corner cases are all important factors to mention in comments for the benefit of future developers and testers.

### Anti-Comment Point #1: Comments take time and have cost but do not influence runtime behavior

It is true that comments have zero impact on the output of the compiler. Eliminating all comment lines is one of the very first steps performed by the compiler or interpreter. Clearly the existence of comments is solely for the benefit of the reader. The creation and maintenance of comments carries a cost, and that cost is justified only if it provides a benefit greater than that cost. The presumed benefit is easier maintenance in the future, but that maintenance can be just as easy with comment-free well-crafted source code.

### Anti-Comment Point #2: Comments are not properly maintained

Since comments have no impact on the runtime results, they are sometimes neglected when the source code is updated. Source code maintenance as a result of a production bug is often done under time pressure and maintaining comments is seen as an unnecessary delay. There may not be any particular standard for maintenance of comments in production source code and it is left to the discretion of the individual developer.

### Anti-Comment Point #3: Comments may be unrelated or offensive

Comments are just that: comments. And sometimes those comments reflect the developer's frustration with the code in ways that, well, should not be repeated in polite company. Sometimes comments are written by developers that misunderstand the code and reinforce that misunderstanding through incorrect or misleading text. The feeling is that bad comments are worse than no comments.

## An Issue Worth Study

Unfortunately, I am not aware of any scientific studies that have been done to measure the effectiveness of various coding or comment styles. Considering the tremendous amount of money invested into software development each year, the financial benefits of optimizing coding standards based on a critical analysis could be substantial.

I would like to see such a study performed. I envision that the study would start with a series of common code comprehension tests for all participants to serve as a baseline and then the various coding styles for a series of solutions would be spread across the participant pool with comprehension speed and quality measured. When normalized against the results of the baseline tests, I am hopeful that useful trends could be drawn from the results. Are there any researchers willing to take up the challenge for such a study?

Where do I fall in the debate?

I have been developing production software since 1981, when adding comments had a very physical manifestation, literally keypunching an additional card in the punch card deck for each comment line. Over the last 30 years I have read source code from hundreds of developers across the full spectrum of coding and comment styles in multiple languages. I have seen the good, the bad and the ugly of software source code.

I generally fall into the pro-comment camp. The software blocks that I have found easiest to understand are those which have a multi-line block comment at the top to explain the general approach and intent of the developer and then specific single line comments throughout the code at the start of each new logical step of the algorithm. This is how I comment when I write production code.

Comments have value and are a justified expense. Comments need to be maintained with the same diligence as executable source code. Comments should be treated as a professional responsibility and offensive comments should be treated the same as offensive verbal speech. Company policy and code reviews should enforce this approach.

**As a useful tool, I would like to see a program made available that produces API like documentation from source code but also includes all the inline comments as a separate section of the documentation page. High quality comments would give a clear picture of the purpose of the routine and a natural language narrative the specific algorithm contained with the method. This would be very helpful when provided in addition to the information normally provided by API documentation tools. Comments could be independently reviewed for quality and standards compliance.**
