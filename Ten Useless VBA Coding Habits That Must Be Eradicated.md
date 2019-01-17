# Ten Useless VBA Coding Habits That Can Be Retired

[ORIGIN-LINK: (http://www.bernardvukas.com/ten-useless-vba-coding-errors-that-must-be-terminated/)

Ten Useless VBA Coding Habits That Must Be Eradicated
Coders have long banned Hungarian notation from their VBA modules. It’s meaningless when the code editor is slick enough to show information about a variable.
But now a new crop of equally meaningless, over-used coding habits have begun to litter code modules… and these need to go, too.
In my work, I frequently encounter code from other people, and from time to time I catch myself making them. Nonetheless, it’s useful to know what they are, and how they cause problems, so that you can avoid them in the future.
Note: although I used VBA as an example, these errors also apply to other programming languages, such as C# and VB.NET.

## 1. Hungarian notation
If you’re wondering what is Hungarian notation, it’s an identifier naming convention in computer programming, in which the name of a variable or function indicates its type or intended use.
Let’s illustrate this with an example. In the function CalculateTotal() below, letters s, i and d are examples of Hungarian notation:

```vb
Function CalculateTotal(sProductId As String, iQuantity As Integer, dUnitPrice As Double) As Double
' etc.
End Sub
```

My problem with Hungarian notation is that it takes perfectly well written code, and then obfuscates it. It also makes your code less compliant with other standard coding conventions, such as those used 

```vb
Function CalculateTotal(productId As String, quantity As Integer, unitPrice As Double) As Double
' etc.
End Function
```

If you’re interested in learning more about the best practices in coding in the Microsoft ecosystem, have a peek at Microsoft’s Naming Guidelines for .NET Framework. LINK: ?

## 2. Long Sub and Function procedures

I also have a problem with long procedures. A procedure is supposed be short and manageable and do **one** thing only. If your procedure is too long, it’s probably doing many different things, invalidating its singular purpose.

To give you a good example of what I mean, try visualizing a procedure with 200 lines of code with multiple branching and conditional statements, as well as calls to other functions. It’s a giant nightmare. Instead of long procedures, I prefer using straightforward logic and flow-of-control.

What is the optimal length of a procedure? Ten lines or less is ideal. If it has more lines than that, it may be a good candidate for refactoring.

## 3. Meaningless naming of variables and procedures

There’s nothing worse than vague or meaningless naming of variables. When it comes to code reviews, bad variable names are a great thing to look for. A reasonable rule for coding is to never use meaningless variable names.

### Here’s an example

```vb
Sub Test()
    Dim data As String
    Dim data2 As Integer
    Dim foo As Boolean
    Dim wph As Integer
    Dim dummy as Long
' etc.
End Sub
```

Meaningless names make the code harder to read and comprehend.

## 4. Using error handlers, just for the sake of it

It’s not necessary to use error handlers everywhere and anywhere. If you’re copy and pasting error handlers just to fill every empty procedure, or to make nice formatting, it’s pointless. A better approach would be to replace such error handlers with data validation. After you’re completely happy with that, then you may consider adding error handlers.

## 5. Using comments, just for the sake of it

When you write short, self-documenting code, most of the time comments are unnecessary. Also, it’s annoying when your comment just states what’s obvious. Consider this example:

```vb
    i = i + 1 ' increment i by one
```

Generally, comments should describe what or why you are doing something, rather than how. Comments should be used to provide more value, not confuse you even further.

## 6. Not validating data

In simple terms, validation refers to ensuring entered data is valid. Determining whether or not data is valid can sometimes be a painstaking process as there are numerous tests that need to be thought of. If you have a habit of not validating your data, you risk the robustness and reliability of your program, as run-time errors will cause problems.
One example of where data validation is used extensively is in UserForms. If you have a TextBox that only accepts zip codes, you need logic to validate and reinforce it.
You could reinforce validation at the UI level; by using input masks, for example. However, using code to validate is also a good idea.
Besides validating in UserForms, it’s also beneficial to validate in Sub and Function procedures. If you’re passing around data from one procedure to another, you need to verify that the received format matches the expected. When data is validated properly, you’ll avoid run-time errors, as well as increase data integrity.

## 7. Too many parameters

When you define a Sub or Function procedure, you specify a parameter list in parentheses immediately following the procedure name. For each parameter, you specify a name and data type.
So how many parameters are too many ? Here’s a comment from a thread on StackOverflow:

> The ideal number of arguments for a function is zero (niladic).

> Next comes one (monadic)

> followed closely by two (dyadic).

> Three arguments (triadic) should be avoided where possible.

> More than three (polyadic) needs very special justification — then still avoid.

Let’s look at an example.

```vb
Function CreateProposal(clientName As String,
clientId As Integer,
title As String,
subtitle As String,
projectName As String,
reportDate As Date,
preparedBy As String,
reviewedBy As String,
authoredBy As String,
fontSize As Integer) As Boolean
' Logic goes here...
End Function
```

There are a few way to optimize this, and here’s one way:

```vb
Function CreateProposal(clientInfo As Client,
documentInfo As Proposal,
contributors As Authors) As Boolean
' Logic goes here...
End Function
```

## 8. Using magic values

A magic value is a value that’s usually hardcoded in such a way that doesn’t require a variable. Here’s a simple example (notice the number ‘7’; it’s considered a magic value):

```vb
Sub SetPassword(password As String)

    If (Len(password) > 7) Then
    ' Display error
    End If

End Sub
```

As your program grows, using magic values can cause problems, especially if the same value is defined in many places in your solution. Here’s how you can fix it:

```vb
Private Const PASSWORD_LENGTH As Long = 7

Sub SetPassword(password As String)

    If (Len(password) > PASSWORD_LENGTH) Then
    ' Display error
    End If
    
End Sub
```

## 9. Declaring variables wrong, HOW TO Make Everything a Variant

I see this one a lot, and it’s really annoying:

```vb
Sub CalculatePayroll()
    
    Dim a, b, c, d As Integer '' Incorrect
    
    '' Do this instead:
    
    Dim a As Integer
    Dim b As Integer
    Dim c As Integer
    Dim d As Integer
End Sub
```

On the line where a, b, c and d are defined, only d is of type Integer. All the other ones are Variants. To avoid this error, it’s best to initialize variables on each line separately.

## 10. Coding more than you have to

Coding is fun! But don’t let get carried away — a successful programmer is not measured by the number of lines of code.
If you’re writing more lines of code to express the logic than what is necessary, chances are you’re trying too hard. Don’t write more than you need to — your solutions will be easier to maintain in the future, and it won’t confuse people unnecessary.

## Conclusion

### The coding habits I covered are

* mis-using Hungarian notation
* long Sub and Function procedures
* meaningless naming of variables and procedures
* using error handlers and comments erroneously
* not validating data
* passing too many parameters
* using magic values
* declaring variables incorrectly
* and coding more than you have to

Changing your coding habits overnight can be hard, but knowing where to look can be a huge boost to your productivity. I hope that by giving these tips you’ll get inspired to eradicate habits that are slowing you down.