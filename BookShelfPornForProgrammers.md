
# BookShelf Porn For Programmers

> Some very worthwhile books - in no particular order

## [Code Complete 2 – Steve McConnell](https://www.amazon.com/Code-Complete-Practical-Handbook-Construction/dp/0735619670/)

The bible of high quality software development. If you read nothing else read this book. All sections are clearly described with plentiful references to further works that are well worth following up. I use this as my directory for what to read next.

...

The most important advice in my view is to write software for people first and computers second. Super fast, super elegant code that does not work, or can’t be tested or adapted to changing needs is less use than simple to understand potentially slightly slower code. Indeed with modern optimising compilers the performance impact of different coding structures is notoriously difficult to predict.

---

## The Pragmatic Programmer – Andrew Hunt and David Thomas

Superb book written with the simple goal of helping people write better software, and it works!
Discusses how to set up a professional software development environment, offers some great suggestions for the design phase, including design by contract, what to prototype, when, what and how to refactor, testing effectively, as well as details of tools that can help at all stages of a project.

The most important aspect to this book is the downright usability of the advice – this is stuff you can do today to make your software better, your project less painful and more rewarding.

My favourite quote is: If you see hoof prints, look for horses not zebras. They are talking about finding problems and where to start looking – generally in your own code or understanding somewhere –not the compiler, or the operating system.

---

## Pragmatic Unit Testing - Andrew Hunt, Dave Thomas

Another great book from those pragmatics. Many books have been written about unit testing, but this one gives you enough information to integrate this essential development practice into you projects right now.

Contains great advice on what to test, and just as importantly, what not to test. Also has useful pointers for where to go for information and additional resources. It also discusses how to refactor to facilitate unit testing for those that inherit their code from others who have not yet seen the light.

If you can see the benefits of unit testing but are not sure how to get going then this is the book for you. If you are not convinced of the benefits, then read the book anyway, maybe you will surprise yourself and change your mind based on the advice and the field anecdotes presented.

---

## Software Craftsmanship – Pete McBreen

Another agile school book, a simple proposition and an easy read. The argument is that software development is nearer the skilled crafts of old (think 3rd generation carpenter, or stone mason) than the modern professions like engineering. This leads to the suggestion that there should be a recognised apprenticeship, under a master, rather than purely college based education.

It’s a pretty convincing argument too, especially for smaller development projects. The book talks about ‘good enough’ (a key element of engineering – too good is ‘over engineered’ and therefore wasteful), compared to the craftsmanship approach of individual care, skill, commitment and responsibility.

A key element is the idea that software developers cannot just be interchanged as ‘human resources’, strengths and weakness and skill sets need to be carefully matched to the project requirements. Having experienced team members being exchanged without consideration of this, I heartily agree.
It contains an interesting discussion of the value of a good developer – probably 5-10 times more than an average developer, and certainly worth more than their manager.

---

## Facts and Fallacies of Software Engineering – Robert L Glass

A very readable book, discusses 55 facts about software – such as – ‘Error removal is the most time consuming phase of the life cycle’.

The facts cover all phases of the software development lifecycle and general management.

Many of the facts are pulled in from elsewhere and all come with full references to original sources.

Classic comments like F. Brookes – ‘Adding people to a late project makes it later’, are discussed along with any controversies or counter arguments.

He also covers a few fallacies – my favourite would be the fallacy that software development needs more methodologies. Especially as most commercial developers aren’t following a specific Methodology – they adapt to suit.

This is actually a very concise book that covers an incredible amount of ground in a couple of hundred pages. This is the stuff that everyone in the industry should know, but most don’t.

---

## In Search of Stupidity – Merrill R Chapman

This is more of a business book than a development book, it looks at some of the marketing disasters in the tech industry over the last 20 years.

If you ever wondered what happened to the household names of years gone by – here it is.

MicroPro – WordStar – remember them? Read about how they managed to go from software market leader to zero in 4 years.

He reviews about 10 different companies (well ex-companies in many cases) devoting 10 or 15 pages or so to each.

He covers Borland who have had a rather chequered past – at one time their Quattro-pro spreadsheet was considered the best of breed by a long way. Their current crop of developer tools (Delphi and C++ Builder) are also highly regarded. Bizarrely they recently announced they were leaving the development tools market – this has understandably sent panic though their once loyal dev community. Having read the book this move comes as less of a surprise.

The discussion of Microsoft is very interesting, in summary he suggests Microsoft have become so dominant because they haven’t made any massive blunders, whereas all their original competitors have made huge judgment errors that have, generally destroyed them.

Interestingly a common mistake seems to be re-writing products from scratch in search of some inner beauty rather than competing in the market by providing features customer want.

---

## Visual C++ for Visual Basic Developers – Bill Locke.

There are many reasons VB developers may desire a better understanding of C/C++. When you start bumping on the ceiling of native VB and need to work with various API’s a solid understanding of at least the different data types is useful.

This book is also very useful for making the move completely to C/C++ and/or C#.

The first section reviews the various strengths and weakness of VB and C++. It may come as no surprise that the 2 languages are actually complementary. With VBs rapid GUI development and the C++ flexibility and raw performance almost anything is possible.

The book also covers .net to an extent, although a lot has changed since 2002 (the VB6.0 to VB.net incompatibility story hasn’t unfortunately).

The book covers C basics first and then C++ basics, before moving onto the OO features of C++, many of which will be somewhat alien to ‘classic’ VB developers. All discussions are illustrated with VB explanations which is excellent as some C stuff just makes no sense on its own. However relating it to VB makes it that much clearer (eg pointers are very much like passing ByRef)
There is then a discussion of Windows and the message pump, if you have ever had to use the SendMessage API or hooking windows messages, this chapter should help to actually make it make sense.

Once the scene is set the next section looks at writing C dlls, but not in isolation. Dlls are actually discussed in the context of being called from a VB application – the tie up of the VB declares with the C prototype is enlightening.

The section on controls cover a brief overview of MFC and ATL including linking strategies with MFC, controls aren’t really my thing, but the ATL walk-though seemed to make sense.

The book finishes with a section on C# and .net which useful for context setting, and for many VB developers, learning C# may represent a smart move. Discussions I have had with VB developers suggest that C# may actually be easier to learn than VB.net. That may be because its so integral to .net and they can approach it with no pre-conceived ideas – the familiarity of VB.net actually works against the .net mindset. Your mileage may vary.

---

## Spreadsheet Check and Control - Patrick O'Beirne

Probably one of the most important spreadsheet books ever written.

Where many authors focus on unusual and obscure 'hacks' and tips and tricks, Patrick focuses on sensible down to earth risk reduction techniques.

These may not impress your friends and colleagues but your customers and boss will be delighted with the increased usability, accuracy and reliability his techniques encourage.

Finally there is a book that addresses quality in spreadsheet development in the real world.

Be aware that the pages are packed with useful and usable advice, so the 200 pages is probably equivalent to 500 pages in many other books once the verbose filler,irrelevant anecdotes and fancy graphics have been added.

---

## Excel Add-in Development in C/C++ - Steve Dalton

Finally here is a book with excellent coverage of the black art of xll development. It is mainly focused on worksheet functions, but it does provide good coverage of the (limited) user interface aspects of xlls too.
Anyone who has written worksheet functions in VBA (or VB6 or .net) will know about poor performance. It is generally accepted that there is only one way to get good performance – and that is through the C API that Excel exposes. Unfortunately this is only accessible to native win 32 code that languages such as C/C++ and Delphi produce.

The book goes step by step through discussing Excel functionality, working with VBA, creating dlls (for use with VBA Declares for example), the Excel Add-in Manager interface that enables Excel to understand the dll, passing data between Excel and your xll and managing memory, always in the context of writing high performance worksheet functions.

Later sections cover accessing Excel functionality (such as menus, events etc) to enable fully featured add-ins to be built. The miscellaneous chapter has a very interesting section on performance – comparing VBA to C for a range of activities, and also outlines some approaches to multithreading that could be extremely beneficial in multi core/processor environments. Excel 2007 is set to have multi-threaded calculation natively, but the xll approach will still be very relevant.

The book also comes with the authors C++ class structure source code to neatly wrap the gory details of the Excel C API.

---

## Professional Excel Development – Stephen Bullen, Rob Bovey, John Green.

At least one of these authors has been involved in pretty much every serious Excel development book ever written, so the pedigree is impeccable. This is THE current Excel developers textbook.

Sections include architecture and design, best practice, user interface, windows API, advanced VBA issues such as classes, interfaces and error management. There is a short section on working with relational databases, and good coverage of extending Excel programmatically. There is an excellent chapter on xlls which unusually is simple to follow, as well as chapters working with VB6 and .net (conclusion - .net is not ready for Excel (yet))
There is also coverage of XML and web services as well as packaging solutions for distribution.

PED comes with loads of great examples demonstrating all the techniques covered, with plenty of cut and paste code to get your own projects off to a flying start. The CD also contains some of the authors more popular (free) tools, to get you productive right away.
The book follows the development of a specific project, updating and upgrading to incorporate the technologies as they are introduced. It’s a good book and an essential read for any Excel developer who aspires to produce high quality spreadsheet based applications.

---

## Pivot Table Data Crunching - Bill Jelen, Mike Alexander

Pivot tables are probably the most important feature in Excel. Unfortunately they are also the most underused which represents a phenomenal waste of time and effort.

This book will help people find out what pivot tables can do for them and how to do it. It contains thorough coverage of all the main pivot table features in all Excel versions since '97. Good coverage of more advanced aspects such as calculated items and fields.

The chapter on External data sources could maybe have been a bit more in-depth, but where do you stop? As it is, it gives a good introduction to returning data from Access.

Also contains a good section on OLAP data sources and there is an offline cube to download and play with on their site. If you have SQL server, even better, as the example uses the foodmart 2000 sales cube so you can follow along.

The book also clearly and concisely identifies which type of pivot tables support which features, something lacking until now.

---

## Excel Advanced report Development – Timothy Zapawa

This book is based on a pretty simple premise – Excel is your window to the world of corporate data. It’s a practical handbooks with full ‘select this..’ ‘click that..’ instructions to unleash the full power of Excels very under-utilised data access technologies.

There are sections on pivot tables, data source types, using the query wizard, MS query and SQL There is also good coverage of OLAP cubes – a superb technology for analyst type users, but so often ignored.

It also has a section on native Excel data tools like subtotalling and grouping, as well as a good discussion on when to use pivot tables and when to use a tabular report. Much of the content is supported by downloadable videos and examples.

There is a chapter on using Office Web Components to publish Excel data to the web, which sensibly discusses some of the security (and licensing) issues too. The final section is an overview of SQL, and the book has many SQL queries scattered throughout.

There is no VBA in the book, all the techniques use the user interface that is built into Excel.

Overall the book enables and encourages a great way to work with Excel, using it for its strengths and passing some of the work that is better done in other components to those components. Many horrible spreadsheets are built by users trying to manipulate data in ways that are so simple in databases, and so tortuous in spreadsheets. By using the information in this book those same people could make their lives a lot less painful, and error prone, whilst releasing the true power of their data.

---

## This Isn't Excel, its Magic - Bob Umlas

Great set of tips and tricks for working with Excel. Everybody who works with Excel will find something that will save them time or pain or both in this book. Covers features, formulas, keyboard shortcuts, printing, VBA and Misc sections.

Has some great tips for selecting specific cells, for example to fill in blanks, and a clear explanation of the power of number formats.

Contains 85 assorted tips, anyone who knows Bob knows that means he has plenty left for a sequel (or 2)!

---

## About Face 2.0 – Alan Cooper, Robert Reimann

If your software is going to interact with human users you need to read this book. If you ever wondered why some dialog boxes seem easier to use than others, the explanation is in this book.
The authors go into the finest detail to explain what works, and for who and what does not work and why. Not only that, but they give the reader the knowledge to design their own software to play nicer with the human users.

The book starts with a discussion of goals for software interaction, separating the mental model from the implementation detail. It then discusses some broad issues around user experience levels before going into some detail of the use of ‘personas’ to drive the design. It then goes on to critique many of the common user interface features. Implications are discussed, and where appropriate, better alternatives are suggested. Having read this book, it becomes clear that many of our interactions with a computer have been thrown together rather than designed. The classic example being the Tools>>Options dialog in Excel (or Word).

I especially agree with the section about unnecessary confirmation dialog boxes (‘don’t ask – do’). I have read other books that recommend you always check with the user before doing anything- but does anyone really read those alerts? – No they just click ok, and are annoyed by the break in flow. Far better to follow Coopers advice and perform the action, but provide a simple way to undo it, a classic example being the recycle bin.

---

## Microsoft .Net Development for Microsoft Office – Andrew Whitechapel.

The inside line from Microsoft about how to combine their latest developer tools with MS Office to create powerful business solutions.

This book is aimed at .net developers looking to develop ‘Smart Client’ applications targeting Office, rather than Office developers wanting to work in .net.
From an introduction covering the basics of .net/COM office interoperability and a discussion of languages – VB.net is given the nod over C# for convenience, but all the examples are in C# (due to the finer grain of control available). For anyone with a VB/VBA background the syntax does get rather tortuous. C# and Office come from different eras, and have different design goals, some of which are clearly in conflict currently.

This book goes well beyond VSTO (Visual Studio Tools for Office) which is actually only a small piece of working with Office, and covers all the application patterns that are possible – with info about which Office versions support each. It covers such things as PInvoke, reflection, integrating with VBA, creating COM and automation add-ins, smart tags, smart docs, web services and data access. It also has useful section on security and appdomain isolation (COM shims – Andrew wrote the COM shim wizard). Of course it has a decent section on VSTO too, including a discussion of deployment.

The book is good and if you are determined to use .net with Office you definitely should read and inwardly digest its content. You should be aware that .net/Office is not really a compelling story at the moment and adoption has generally been fairly muted. Things are changing all the time though, so that may change. Of course if you value a stable technology base then .net may not be appropriate. This book refers to Visual Studio 2003.

---

## Visual Studio Tools for Office – Eric Carter, Eric Lippert.

The authors are senior developers on the VSTO team, and clearly know their technology inside out. The book provides in depth coverage of using Visual Studio 2005 and VSTO 2005 (now 2 separate products) with each of the main Office products.

The layout is good – it focuses on each Office product in turn so if you know you are targeting Excel, there is no ‘in Word…’ ‘, in Outlook...’, noise preventing you from getting quickly to the key points.

Although the title is VSTO, the book covers all the main patterns including add-ins. Again the code is C#.
The section about writing User Defined formulas in .net is especially good – clear and concise. It’s a shame the performance penalty of this approach is so significant . They also explain how they have fixed the locale ID issue which dogged VSTO 2003. This means VSTO 2005 Apps will work in non US English environments.

As well as the fairly in-depth look at Excel, Word, Outlook and Infopath, the book covers more general .net issues. Topics such as using rich .net forms, the action pane, smart tag, data islands, SeverDocuments and XML are all discussed as well as security and deployment.
The book is based on VSTO 2.0 (from the 2005 releases) this product is a significant improvement from VSTO2003, in particular the VSTO programming experience now hosts the Excel workbook, making it a similar experience to VBA or standard windows form development. VSTO is document level only in 2.0, 3.0 is in the pipeline though and it will support application level solutions like add-ins – hopefully without the COM interop layer.

---

## Writing Solid Code – Steve Maguire

Probably getting on a bit now this book – it was published in 1993 (maybe there is a later edition?). It mainly addresses C and some of the advice is only really useful for C programmers. However there are plenty of excellent tips for developers working in any language. The author worked on MS Word and Excel and has some interesting insights to developments at Microsoft. Knowing the products really brings the advice home.

Good solid ideas like using Asserts, unit testing, stepping through code, incorporating integrity checks in routines are all universally applicable. The discussion of risky constructs is slightly C focused but all languages have dangers – do you know what they are in your language? Do you still use them? If so the final section on attitude may be useful - especially the section on priorities. My favourite section is the one about interfaces – routines should do what they say they will and return a consistent value.
A very easy read, in an informal style with plenty of real world examples.

---

## Microsoft Excel 97 Developer’s Kit – Baarns Consulting Group

This is the classic in developing for the Excel C API and working with the biff .xls file format. Probably out of print now and desperately in need of updating (Steve Daltons book does that and more for the C API side of things).

Good general discussion of add-in design, a bit of a retro section (now) on moving from Excel 95 to 97 (I remember the pain) a good section on using C dlls from VBA, and using automation to control Excel. The main C API features are then documented and illustrated using the C framework code provided.

The main chunk of the book is given over to documenting the underlying file format used in .xls files. This is pretty thorough, but of course misses any of the new features added in 2000, 2002, and 2003. As it turns out that isn’t that many features, more up to date information is available from some of the open source projects that provide binary compatibility with the Excel file format.

There is no indication from Microsoft whether they will update this book to cover any new additions, although it looks unlikely as Excel 2007 will natively use XML, which is self describing.

---
