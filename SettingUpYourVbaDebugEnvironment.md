<!-- https://christopherjmcclellan.wordpress.com/2014/11/21/setting-up-a-debug-environment-for-vba/ -->

# Setting Up Debug Environment for VBA

VBA supports Conditional Compilation.

Most often this is used to switch between different methods based on whether the installed version of Office is 32 or 64 bit, but it can also be used to set up a kind of debugging environment.

Today we’ll take a look at what exactly conditional compilation is, and how to leverage it to make our programs behave differently while we’re developing.

VBA has what is called an #If…Then…#Else directive. This special “If” statement allows us to execute different code based off of the environment the code is executing in.

The behavior of the #If…Then…#Else directive is the same as the If…Then…Else statement, except that there is no single-line form of the #If, #Else, #ElseIf, and #End Ifdirectives; that is, no other code can appear on the same line as any of the directives. Conditional compilation is typically used to compile the same program for different platforms. It is also used to prevent debugging code from appearing in an executable file. Code excluded during conditional compilation is completely omitted from the final executable file, so it has no size or performance effect.

We could use some of the built in constants to execute different code based on the version of Office like this.

```vb
#If Win32 Then
    ' execute code for 32 bit office
#ElseIf Win64 Then
    ' execute code for 64 bit office
#ElseIf Win16
    ' execute code for 16 bit office
    ' And by the Way did Time Travel get invented ?
#End If
```

That is certainly handy if you have to develop for users on different bit versions of Office. That’s not what we’re here to talk about though. There are plenty of examples of that out there already. Let’s see what other ways there are for us to make our lived easier with this. One way we could use this is to skip over Debug.Assert() statements when we deploy a project to production.

```vb
#If DEBUGMODE Then
    Debug.Assert False
#End If
```

Of course, DEBUGMODE isn’t one of the built in constants. In order to use the code above, we have to define it ourselves. There are two options to do this, each has it’s pros and cons.

1. Define a module level constant using the #Const directive.
2. Define a project level Conditional Compilation Argument.

The former is certainly the easier of the two, but only has an effect on the current module. So, we could define it at the top of each module in our project like this.

```vb
Option Explicit

#Const DEBUGMODE = 1

Public Sub Foo()
    #If DEBUGMODE Then
        Debug.Print "I'm in developer mode."
    #End If
    Debug.Print "I always happen."
End Sub
```

That’s not very DRY though. We would have to copy and paste that declaration into every module in our project. Worse, we would have to go through each module of our project and change 1 to 0 when we’re ready to deploy. That seems like an accident waiting to happen to me. So, let’s go about this with a compilation argument.

In the VBA IDE, go to Tools>>[Your Project Name] Project Properties. This will bring up the project properties dialog box where we’ll enter the constant declaration.

In the “Conditional Compilation Arguments” box,type in DEBUGMODE = 1.
  
It’s that easy. Now it’s a breeze to switch between what files, or database connections we use while developing.

```vb
#If DEBUGMODE Then
    Const filepath As String = "C:\Users\UserName\Path\To\File.txt"
#Else
    Const filepath As String = "\\server\share\path\to\file.txt"
#End If
```

When you’re ready to deploy, just go back into the project properties and change the argument to DEBUGMODE = 0. If you find yourself in need of more than one constant, just separate them with a colon.