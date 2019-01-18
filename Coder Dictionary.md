# Coder Dictionary

- [wikipedia.org/wiki/Feature_creep](https://en.wikipedia.org/wiki/Feature_creep)
- [wikipedia.org/wiki/Scope_creep](https://en.wikipedia.org/wiki/Scope_creep)

> **Creeping featuritis** is rampant in computer software and hardware. Creeping featuritis is also known as feature creep and featureitis. A creeping featuritis spoonerism is feeping creaturitis.

---

[wikipedia.org/wiki/Code_smell](https://en.wikipedia.org/wiki/Code_smell)

> a **code smell** is any characteristic in the source code of a program that possibly indicates a deeper problem. Determining what is and is not a code smell is subjective, and varies by language, developer, and development methodology.

The term was popularised by Kent Beck on WardsWiki in the late 1990s. Usage of the term increased after it was featured in the book Refactoring: Improving the Design of Existing Code by Martin Fowler. It is also a term used by agile programmers.

Bad code smells can be an indicator of factors that contribute to technical debt. Robert C. Martin calls a list of code smells a "value system" for software craftsmanship.

---

[wikipedia.org/wiki/Design_smell](https://en.wikipedia.org/wiki/Design_smell)

> **design smells** are "structures in the design that indicate violation of fundamental design principles and negatively impact design quality".

Design smells indicate the accumulated design debt (one of the prominent dimensions of technical debt). Bugs or unimplemented features are not accounted as design smells. Design smells arise from the poor design decisions that make the design fragile and difficult to maintain. It is a good practice to identify design smells in a software system and apply appropriate refactoring to eliminate it to avoid accumulation of technical debt.

The context (characterized by various factors such as the problem at hand, design eco-system, and platform) plays an important role to decide whether a certain structure or decision should be considered as a design smell. Many a times, it is appropriate to live with design smells due to constraints imposed by the context.

---

[wikipedia.org/wiki/Anti-patter](https://en.wikipedia.org/wiki/Anti-pattern)

More in [LogDataTech Anti-Patterns Article](./Anti-Patterns.md)

<!-- ![randofile.sh(./randofile.sh) <- How to Link to a local non Markdown file same as image. -->

> An anti-pattern is a common response to a recurring problem that is usually ineffective and risks being highly counterproductive. The term, coined in 1995 by Andrew Koenig, was inspired by a book, Design Patterns, which highlights a number of design patterns in software development that its authors considered to be highly reliable and effective.

The term was popularized three years later by the book AntiPatterns, which extended its use beyond the field of software design to refer informally to any commonly reinvented but bad solution to a problem. Examples include analysis paralysis, cargo cult programming, death march, `groupthink` and vendor lock-in.

<!-- @NK use `madeupword` to highlight made up words -->

---

[wikipedia.org/wiki/Software_bloat](https://en.wikipedia.org/wiki/Software_bloat)

> Software bloat is a process whereby successive versions of a computer program become **perceptibly slower**, use more memory, disk space or processing power, or have higher hardware requirements than the previous version—whilst making only dubious user-perceptible improvements or suffering from feature creep. The term is not applied consistently; it is often used as a pejorative by end users (bloatware) to describe undesired user interface changes even if those changes had little or no effect on the hardware requirements. In long-lived software, perceived bloat can occur from the software servicing a large, diverse marketplace with many differing requirements. Most end users will feel they only need some limited subset of the available functions, and will regard the others as unnecessary bloat, even if end users with different requirements require those functions.

Actual (measurable) bloat can occur due to de-emphasising software efficiency in favour of other concerns like developer productivity, or possibly through the introduction of new layers of abstraction like a virtual machine or other scripting engine for the purposes of convenience when developer constraints are reduced. The perception of improved developer productivity, in the case of practising development within virtual machine environments, comes from the developers no longer taking resource constraints and usage into consideration during design and development; this allows the product to be completed faster but it results in increases to the end user's hardware requirements to compensate.

## The term "bloatware" is also used to describe unwanted preinstalled software or bundled programs