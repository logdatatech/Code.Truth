# Ten Habits of a Good Programmer

http://hintjens.com/blog:98

> Good programmers are born and then made. You need talent and passion, and you need experience. I was lucky to learn from the best, and have lots of opportunity to practice. I'm going to summarize ten of the top habits I've always applied to my work. Cause or correlation? You tell me.

## 1. If it works and is still useful, don't throw it out.

This means writing portable code, and making reusable pieces. Libraries, APIs, whatever it takes. Be your own client. Layer your work.

## 2. Never solve the same problem twice in parallel.

This means making tools. Adopt the Unix philosophy: command-line tools that do one thing and do it well. Learn about pipes. While you're at it, use Linux (or a BSD) as your development box.

## 3. Solve the same problem often in serial.

This means being willing to throw out your code and rewrite it when you find better solutions. If you work towards minimal APIs rather than features, this works better.

## 4. Write code, and repeat, until you are fluent in your language.

Using a small language makes this easier. It takes years to become really fluent in a programming language.

## 5. Learn to use code generators.

I've spoken of GSL before. A general-purpose code generator is an essential tool for a serious programmer. There are a few options. Try them, choose one.

## 6. Work with others.

Learn the techniques of collaboration. A good way is to contribute to an open source project. Or even better, start your own. Read Chapter 6 of the ZeroMQ Guide. It will enlighten.

## 7. Technology is a tool, not a tribal affiliation.

Never turn pragmatic choice of tools into a belief system. I have written editors and code generators in COBOL 74. The language matters little.

## 8. Aim for this cycle: learn, play, work, teach.

It is the fastest way to get better and deliver code that others can use and trust. Avoid this cycle: imagine, argue, agree, work. It is the fastest way to deliver junk.

## 9. Get your edit-compile-run-fail cycles down to seconds.

If your language offers a REPL that's cool. If not, make a shell script that runs the loop for you. Your goal is that after every edit, your code self-tests and passes or fails. Use asserts or equivalent to challenge your own code.

## 10. If you need debuggers, you're doing it wrong.

Make one change, test one change. Layer your code and write self-tests so that when it works, it always works. Use print statements. Aim towards APIs that are fully testable. Avoid language patterns that deliver fuzzy, unclear internal APIs.