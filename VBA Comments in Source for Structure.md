[// LINK:http://www.aivosto.com/vbtips/codedoc.html]: COMMENT

# Comments are an ideal way to document source code

We present a lightweight comment format that is easy to learn, clear to read and powerful in describing procedures and modules. It also allows automatic document generation by a source code analyzer.

## Purpose of comments

Comments amend source code to make it more understandable. They serve as inline documentation that help to read, reuse, understand and maintain existing code.

The alternatives to commenting are self-documenting code and separate code documents. In reality, few pieces of code are entirely self-documenting. Separate code documents, if ever written at all, are often incomplete. What is more, they go out of date easily as the code gets modified. On the contrary, comments are there to read and update when the code is worked on.

Here we present a lightweight, yet powerful way to write comments in code. We use as few formal rules as possible. First we go into what should be in the comments, then we suggest a comment format. Last we suggest how to use the comments to generate project documentation.

## Module comments

For the purposes of commenting, a module is any source code file
* Standard module
* Class
* UserForm
* an interface definition eg ThisWorkBook.,ThisDocument.

## What should module comments include ?  
### **Purpose** A few lines about what the module does.
### **Author** Who wrote the module, and when. Also list major updates and who made them.
### **Requirements** What other modules or libraries the module requires to compile and run.
### **Usage** How you use the module.

Is there a special way to instantiate objects of this class? Is there a required calling sequence? How should you dispose of the object? If there are certain key procedures in the module, mention them too.
Limitations. Are there any special limitations to the use of the module?

### Module comment sample

Module comments should start immediately at the start of the module.
We Recommend Option Explicit as first line then comments from line 2  and should be consequtive. An empty line ends the comments.

```vb
Option Explicit
' SystemInfo class for Advanced System Monitor
' This class reads Windows system information
' ©2002 Developer Name, Company Name, www.company.com
'
' Requirements:
' Requires advapi.dll and Windows 98/NT+
'
' Usage:
' Dim WithEvents SystemInfo As SystemInfo ' as a class-level object variable
' Call Init
' Handle the events.
' Destroy to release system resources when no longer required.
'
' Limitations:
' Does not support multi-processor systems.
```

As you can see, an empty comment indicates a paragraph break. Sub-titles end in a colon. No other special formatting rules are required.

## Procedure comments

Every procedure should be commented. By procedure we mean Sub, Function, Property block, or Event declarations.  

Declare statements need no commenting if decent API documentation is at hand.

> What should procedure comments include ?

**Purpose:** One or two lines describing what the procedure does.

**Parameters:** Describe each parameter individually. What values do they accept? For each parameter, indicate if it's for input or output (in/out). If a parameter returns a value, describe it as you would describe a function return value.

**Function return value:** Describe what values will be returned, and in which range. For a boolean or enum return value, describe what the individual return values mean. Mention any special error values.
Side effects. Does the procedure update any variables?

**Error conditions:** If an error condition may arise, describe if the procedure will handle the error, or let the caller handle it. Does the function return an error code? Should the caller be prepared with an error handler? Should the caller read the Err object?
Pre-conditions. Are there any conditions that must be met before calling this procedure? Should you call the procedures in a certain order? Should you set some variables?

**Algorithm:** If the procedure implements a complex algorithm, it may be worth describing it too.

**Callers:** If the procedure is called by a known set of procedures, list them. If the set of callers is unknown or can change, listing them makes no sense as the information may go out-of-date. For an Event, all cases when the event is raised should be listed.

> Do not put repetitive information, such as author and date, in a procedure comment.

This information is best kept at the module level. If needed, this information can be put in the procedures that differ from the values of the whole module.

#### Procedure comment sample
Here is a sample function with the suggested commenting scheme used.

```vb
' Prints text on the screen at coordinate (x, y).
' [x] In/out - The x-coordinate in pixels.
' [y] In/out - The y-coordinate in pixels.
' [Text] In - The string that will be displayed. ByRef for speed.
'
' Return value:
' True if successful.
' False in case an error occurs.
'
' Side effects:
' Updates x and y to contain the coordinate after the printed string.
' No update if return value is False.
'
' Remarks:
' Raises error 12345 if coordinate outside of visible area.
Function PrintText(ByVal x As Integer, ByVal y As Integer, ByRef Text As String) As Boolean
```
Procedure comments start immediately before the procedure header. Sub-titles end in a colon.

Each parameter is enclosed in square brackets to make it stand out. Parameters are described with a single line. In indicates a parameter whose value is read. Out indicates a parameter that returns a value.
Comment format remarks

We haven't included any indentation in the format. All comments should start with ' and a space. Empty lines are useful for grouping things and separating paragraphs. An empty line should be written as an empty comment (' ) to indicate that the comment block continues. Do not indicate the end of the comment block in any Particular way the VBE IDE can distinguish the comments from the Code.

We don't think it's necessary to include separators, such as  
```vb
'--------------------------------------------------
```
in comments. They don't have any meaningful content in them. They just take space and add work. You can use them if you want, but they are not really useful.

The colon (:) is reserved for the indication of a sub-title. If a colon is in the middle of a line, the start of the line is the sub-title and the rest is text. If a colon is at the end of a line, the whole line is a sub-title.

## Automatic document generation

This comment syntax is supported by Project Analyzer. Project Analyzer is a Visual Basic source code analyzer that contains automatic documentation features. The Project Printer add-in of Project Analyzer is able to generate a Comment manual based on code syntax and comments in the code. A comment manual includes module comments, as well as description of procedures and their calling syntax in the module. Project Analyzer includes calls/called by information in the document, so it's not required to manually write this information in the comments.

Writing comments is important if you want people (including yourself) to understand your code. By following a comment standard you make it possible to utilize the comments programmatically when the project is ready. The standard described in this article is one that is readable by both humans and documentation tools, making it ideal for everyday use.
