
<!-- https://www.reddit.com/r/excel/comments/4trjrq/vba_essentials_writing_clean_code/ -->

# VBA Essentials: Writing Clean Code

This topic is a great way for beginner users to get introduced to what good code looks like, and why it looks like it does.

## Introduction

You’re going to run into errors no matter how long you’ve been coding, but luckily there are a few things you can do to bring the error count to a minimum. One of those things is to write Clean Code, and that’s the topic of this post.

Many users begin their VBA journey by recording macros and going in after for small tweaks and edits. This is a great way to introduce yourself to the world of macro writing, but it is a terrible example of the type of code you should be writing.

## Naming, Declaring, Setting

You’ve sat down to write yourself a macro. Great! What are we going to name it? Who cares?…..**WRONG!** The name of your macro should give an idea of what task the code performs. My macro is going to find today’s date and copy that row to another workbook. My first keystroke will be…

```vb
Option Explicit

Sub findToday_moveRow()
```

Notice that my first line is Option Explicit; this tells the macro not to run unless I’ve declared all my variables. We do this to help keep up with our variables and to keep an all-together tight macro. Keep note that there is a line break between Option Explicit and the start of the macro; this is for aesthetics and ease of reading; clean code looks good.

Moving on to declaring/setting our variables. Often times when I write macros I don’t know exactly what variables I am going to use until I get in and start writing and problem solving; when this is the case, after I use a new variable I immediately go to the top of my code and declare it. In this example we already know what variables we need.

```vb
Option Explicit

Sub findToday_moveRow

    Dim chkCell as Range
    Dim pasteRow as Long
    Dim firstAddress as String
    Dim myBook as Workbook, pasteBook as Workbook

    Set myBook = ThisWorkbook

    On Error Resume Next
    Set pasteBook = Workbooks(“TodaysDate.xlsx”)
    If pasteBook is Nothing Then
        Set pasteBook = Workbooks.Open(“C:\iRchickenzFolder\TodaysDate.xlsx”)
    End If
    On Error Goto 0
``` 

Let’s look at the format. I have a line break between the macro name and my declarations, between my declarations and setting my first object variable, and between my first variable setting and the second one. These line breaks are to signify that we’re moving from one part of the code to the next. Although setting the object variables is generally done without a line break, I have to do something a bit special for the second set so I make it stand alone; this also helps identify my first setting.

I formatted my declarations in a way that creates a stair-step from the shortest line to the longest line; I’ve also combined like declarations to prevent my macro from having a wall of text. Doing this makes the macro visually appealing and easier to read.

Anything after the first line should be indented(tab) at least once. We’ll indent more as we step through the macro.

Variables should be named for their purpose or for what they will hold.

chkCell – check cell – this will be the range object, single cell, that loops through our range of cells to look for todays date.

firstAdress – first address – this will be the address of the first found date.

pasteRow – paste row – this will be the row we are pasting into.

myBook – my book – this is the workbook that the macro is in.

pasteBook – paste book – this is where we will be pasting our found data.

Variables not only should describe what they hold, but should be formatted like oneTwo with the second “word” beginning with a capital letter. Often times the first “word” is an abbreviation.

The macro will throw an error if the pasteBook is not open when I try to set it so I handle that by resuming next because I’ve put an If statement to open the workbook directly after the line that could possibly throw an error. Immediately after this statement I revert back to normal error conditions, On Error Goto 0. I did not line break for my error statements because I want to make it clear that these error handlers are specifically for the piece that they enclose.

The If statement could be done on a single line which would save us two lines of code, but it is easier to read and understand when we have the full If/End If present. Notice also that my line between If/End If is indented once.

Now we can get to the meat of the macro.

```vb
The Rest of the Code
Let’s take a look.

Set chkCell = myBook.Sheets(1).Range(“A:A”).Find(Date, , ,xlWhole)
        
If Not chkCell is Nothing Then

    firstAddress = chkCell.Address

    Do
        pasteRow = pasteBook.Sheets(1).UsedRange.Rows.Count + 1
        chkCell.Resize(1,5).Copy pasteBook.Sheets(1).Range(“A” & pasteRow)
        Set chkCell = myBook.Sheets(1).Range(“A:A”).FindNext(chkCell)
    Loop Until chkCell.Address = firstAddress

End If
``` 

So there’s quite a bit going on here but luckily the formatting is top notch so it’s going to be easy to decipher. In VBA Date returns todays date!

Everything inside the If is indented once and then everything within the Loop is indented once more. I’ve done a bit of line breaking as well. Notice I’ve broken up some of the statements in the If statement to make it easy to see what’s going on.

What is this part of the code doing?

Set chkCell = first cell (range object) that today’s date is found.

If Not chkCell is Nothing Then just means “if chkCell has a value then”.

If the date is found we continue.

Record the first address that we found the date into a variable; we’ll need this for our loop.

Enter a Do Loop Until statement that will loop through the range until we get back to the first address.

Record the row number of the first empty row in our pasteBook; we’ll need this to place our new data without overwriting previous data.

chkCell.Resize takes our chkCell range and expands it by 4 columns. The syntax here is (1,1) would represent the cell itself and any additions expands the range by one in either the vertical or horizontal direction; That’s why we have 5 to expand by 4.

Copy the resized range.

Instead of putting the paste range on the next line, as long as you don’t need to paste special values, you can put the destination range right after the copied range separated by a space.

Paste into first empty row of pasteBook

Set chkCell = next range where today’s date is found.

Here is the macro in its entirety…

```vb
Option Explicit

Sub findToday_moveRow

    Dim chkCell as Range
    Dim pasteRow as Long
    Dim firstAddress as String
    Dim myBook as Workbook, pasteBook as Workbook

    Set myBook = ThisWorkbook

    On Error Resume Next
    Set pasteBook = Workbooks(“TodaysDate.xlsx”)
    If pasteBook is Nothing Then
        Set pasteBook = Workbooks.Open(“C:\iRchickenzFolder\TodaysDate.xlsx”)
    End If
    On Error Goto 0

    Set chkCell = myBook.Sheets(1).Range(“A:A”).Find(Date, , ,xlWhole)
        
    If Not chkCell is Nothing Then

        firstAddress = chkCell.Address

        Do
            pasteRow = pasteBook.Sheets(1).UsedRange.Rows.Count + 1
            chkCell.Resize(1,5).Copy pasteBook.Sheets(1).Range(“A” & pasteRow)
            Set chkCell = myBook.Sheets(1).Range(“A:A”).FindNext(chkCell)
        Loop Until chkCell.Address = firstAddress

    End If

End Sub
``` 

## Conclusion

There are two major concepts here: naming convention, and formatting. Naming your macro and variables in a way that describes what they do will make it much easier to identify what they are doing, or what they hold. Formatting will make it all around easier to read the code and understand what is going on by sectioning the different parts of the macro.

If you’re going to be writing macros it’s a good idea to have some sort of convention or process by which you write all of your macros. I hope you can take some, or all, of the concepts here and begin to write Clean Code!
