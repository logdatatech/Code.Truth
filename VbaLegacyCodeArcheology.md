
# VBA Legacy Code Analysis/Archaeology

<!-- ORIGIN:http://www.aivosto.com/articles/legacycode.html -->

## Deliverables

* Cross-references
* Call trees
* Called-By lists
* Flowcharts (for Non Trivial/Self Documenting)
* Metrics

Are all useful techniques for understanding existing legacy applications.

> Aargh! I just inherited a mess of projects from a team who left the company 3 years ago. I can't even touch that code without breaking anything. What do I do know?

You don't need to be a trained Legacy Systems Archaeologist to overtake an existing project. The solution is legacy code analysis. This article introduces you to various legacy analysis techniques.

## Why should I analyze legacy code

Maintain an existing application. Before changing a program, you must understand what it does. If you don't, you're likely to make bad fixes and introduce **new** errors.

## Document Old code

Analyzing legacy code and documenting it as you go is good idea. Not only you learn what the code does, you will also help others learn it. Besides, you'll forget anyway. Without the docs, you'll have to analyze again next year.

Determine reuse possibilities. See if the code can be turned to new uses by changing it. **Find reusable components** for other programs.

Determine locations for improvement. Any program is likely to contain bad code. Unless it's really hopeless, you can improve it with a stepwise approach.

Refactor or restructure. Fix here and there. You don't necessarily need to rewrite everything from scratch to make it far better.

## Techniques for legacy code analysis

Efficient legacy analysis requires **lots** of code reading. Here we assume that all the old developers have left the company and left no documentation whatsoever. All you have is the code.

Code analysis is a time-consuming task. To focus on the brainwork and and not the manual side of it, consider the use of automated code analyzers. Based on the source code, they can extract lots of the information for you to process.

<!-- PA This sign denotes that Project Analyzer contains a feature to help with a particular task. Project Analyzer is a VB, VBA and VB.NET source analyzer designed to help with legacy applications. -->

## List what you have

To start, list the code you have. List the names of files and the modules and classes in them. List the procedures. For each module, list its interface: public methods, public data and so on. List the global variables and constants. If you can, get an alphabetical dictionary of all the names in the system. The listings will be useful if the code is all new to you.

<!-- PA Project Analyzer creates a comprehensive selection of listings. -->

## Understand procedures

Procedures (sub-procedures, functions, property accessors) are where the action is.

Review a procedure to see what it does. List the functions it calls and the classes it uses. List the variables it reads and the ones it writes. 

Review the parameters. Understand which one is an "in" parameter and which one returns an "out" value. Does the procedure have any side effects, that is, does it write to any global or module-level variables or data structures?

## List procedure callers

Who calls me? Is this function called by other functions, or is it dead? Is this function called by just a single procedure or is it being reused throughout the project?

Determine the uses of function return values. Is this function's return value actually used somewhere? Do the callers take any action on the return value or is the return value essentially dead?

PA Project Analyzer shows procedure calls and called-by information. Select a procedure and view its call trees (Forward: What do I call? and Backward: Who calls me?). Determine unused procedures. They should probably be removed later. Project Analyzer also lists unused function return values and unused parameters, if any are found.

## Draw flow charts to understand the logic

A flow chart visualizes the conditional branches, loops and jumps. You can draw flow charts manually (bad)
or use [Visustin](http://www.aivosto.com/visustin/help/info.html) (good) for automated diagramming.

## Understand variables

Certain global variables or arrays may be significant to the application. 

When analyzing legacy code, one of the tasks is to spot the key data structures and variables and determine how they are being used.

Determine variable reads. Understand the locations where a variable's value is required.

Determine variable writes. Understand where and how the variable gets its value and how it changes. Does it change in one location only? Can it change unexpectedly as a side effect of some exotic function?

Determine array allocation and deallocation. Does the code allocate more space for the array, or is it fixed size? Does unused space ever get deallocated?

Determine object instantiation and clearance. Is this object variable assigned a new instantiated object, or does it receive pointers to objects created elsewhere? Where is the object released, or is it released at all? Not releasing objects may result in memory leaks, depending on the language and run-time environment.

PA Project Analyzer shows you variable cross-reference information. Right-click a variable to access the reference list. For each reference, you get to know the type of the reference (read, write, read+write, write+read, instantiation, allocation, clearance) and where it is.

## Understand constants

Constants and enumeration constants should not be overlooked. Are they given the correct values in the first place? Where are they actually used? Are there any unused dead constants? Does the program define the same constant over and over again, possibly with differing values each time?

[PA Project Analyzer](http://www.aivosto.com/project/vba.html) lists constants for you and determines whether they are used or dead. Right-click a constant to access the list of use locations.

## Understand module dependencies

More often than not, a program consists of a large number of interdependent modules, such as classes, standard modules, interfaces, data structures, controls and binary modules. Understanding a single module is often impossible without understanding the links to other modules. Modules are often heavily coupled to other modules, even too heavily for easy understanding.

## Control flow trees

Which module calls what other modules? How does the flow of control go from module to module? What other modules does this module call? What modules call this module, or is it dead altogether?

## Data flow trees

Which module passes data to what other modules? Does the data flow in one direction or forward and back?

## Class inheritance trees

What are the child classes of a parent? What interfaces does this class implement? Which classes implement this interface, if any?

Form show trees. In which order are the program's forms being shown? What sub-dialogs does a dialog display? From which locations can the user access a given dialog?

## File dependency trees

What files does this file require to compile? Is this file independent of other files (library module)?

## Circular dependencies

Are there any circular file dependencies? A circular dependency happens when a file needs another and the other file also needs the first one. Neither of them can be used alone. A circular group can consist of many, many files, not just 2. If you remove any of the files, the entire group becomes useless because it doesn't compile or run. Circular dependencies are detrimental to code reuse. The circular group is heavily coupled. It is hard to use the files in other programs unless you restructure the logic or reuse the entire circular group.

PA Project Analyzer shows module dependencies with graphical views. Its Project Graph feature lets you pick any module or file and make a chart of the found dependencies. A File dependency analysis report lists the circular dependencies. What is more, dead modules are reported as well.

## Understand with metrics

If you're faced with a large amount of unknown code, it helps to know what the important code locations are. Here are some tips to find crucial code.

[wikipedia.org/Programming_complexity](https://en.wikipedia.org/wiki/Programming_complexity)

Find the largest modules and procedures. Simply sort them by the number of lines or statements and pick the biggest ones. Big code does big things, usually.

### Find the most used procedures

If a procedure has 50 callers, it should be important. The number of callers is the [structural fan-in metric](https://www.aivosto.com/project/help/pm-sf.html) **(SFIN)**.

### Find the complex procedures

A procedure with a large number of branches or deeply nested conditionals is a complex one. Often, a complex procedure contains lots of internal logic, indicating it does important tasks.

The metrics in question are the [cyclomatic complexity (CC)](https://www.aivosto.com/project/help/pm-complexity.html) and depth of conditional nesting (DCOND).

### Find the procedures that execute the most code

A procedure at the top of its call tree executes the most code in that tree. This is because it executes each sub-procedure and itself. When you count the lines in the call tree (LLOCt) and sort the procedures by this metric, you can spot the entry procedures into the system.

### Find the data-intensive procedures

A procedure that reads and writes lots of data is a likely stress point in the system.

You measure the data flow in terms of information

- fan-in (IFIN),
- fan-out (IFOUT), 
- fan-in * fan-out (IFIO) and 
- informational complexity (IC1). 

Procedures with high informational values are data-intensive and worth a look.

### Find the most connected modules

A module that connects to other modules may be really important for the functionality of the system.

Connection metrics include 
the structural fan-in (SFIN, number of users) and structural fan-out (SFOUT, number of files this file depends on). 

For object-oriented class-based systems you can use the coupling between object classes metric (CBO), the number of children metric (NOC) or the response for a class metric (RFC, number of external methods).

[PA Project Analyzer](http://www.aivosto.com/project/vba.html) knows about VB metrics. Its Project Metrics feature calculates a large number of code metrics, including the ones mentioned in this article.
