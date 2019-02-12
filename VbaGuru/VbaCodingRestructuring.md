<!-- LINK:http://www.aivosto.com/vbtips/restructuring.html -->

# Restructuring Visual Basic code

<!-- TOC -->

- [Restructuring Visual Basic code](#restructuring-visual-basic-code)
  - [Add modularity](#add-modularity)
  - [Go object-oriented](#go-object-oriented)
  - [Encapsulate data access](#encapsulate-data-access)
  - [Limit visibility by scoping](#limit-visibility-by-scoping)
    - [HOWTO Add Modularity](#howto-add-modularity)
      - [Suggested Module Names](#suggested-module-names)
      - [Suggested Module Naming Schemes](#suggested-module-naming-schemes)
    - [HOWTO Go object-oriented](#howto-go-object-oriented)
      - [Convert a module to a class](#convert-a-module-to-a-class)
    - [HOWTO Encapsulate data access](#howto-encapsulate-data-access)
    - [HOWTO Limit visibility by scoping](#howto-limit-visibility-by-scoping)

<!-- /TOC -->

<!-- @NK experimenting with internal anchors vs TOC -->

You can greatly improve the quality of existing code by restructuring it.

By restructuring we mean arranging the code in logical modules and classes, grouping related functions and data together, and using scope rules to achieve better legibility and maintainability.

Spaghetti may be delicious, but not when you find it in your code. It's often necessary to rewrite code to reuse it, to understand how it works, to modify it, or to throw away unnecessary code and write new functionality. Let's learn a few simple ways to restructure code to achieve better quality.

## [Add modularity](#howto-add-modularity)

## [Go object-oriented](#howto-Go-object-oriented)

## [Encapsulate data access](#howto-Encapsulate-data-access)

## [Limit visibility by scoping](#howto-limit-visibility-by-scoping)

---

### HOWTO Add Modularity

Think of a module as a group of related procedures. What you'd want to do is to find groups of procedures that belong together, and put them all to a single module.

The goal is to minimize the number of dependencies between modules. When a module calls procedures from another module, these modules are coupled. Coupling also occurs when a procedure uses variables, constants, declare statements or other elements of another module. You want to keep coupling to a minimum, to make it easier to read the code, and also to make the module a better candidate for reuse in another program.

So how do you find a group of related procedures? That's a tough question. If you know your code (and you should), you probably already have an idea which procedures are related. Now, find out which procedures call these procedures, and where the calls eventually lead to. A call tree is your primary source of calls/called by information. Another thing to consider are the variables, constants and other elements required. PA

There's no single solution to the module division problem. It's more like a trade-off between minimal coupling and optimal module size. You don't want to group all of your procedures into a single giant module, even though that minimizes coupling. It's better to get an idea of a good module size. You'd want modules to contain, say, max 30 procedures (that's not a recommendation, just an example). If the module becomes larger, you might want to consider splitting it into two - even if it increases coupling.

#### Suggested Module Names

- AllPublicDeclarations (Shows Top of Module list)

#### Suggested Module Naming Schemes

- mod%TheRest%

### HOWTO Go object-oriented

Once you've found a group of related procedures, it's time to decide whether you really want a build a new module or rather a new class. You'd want to use a class if the procedures work intensively on a certain set of data. A module is better if the procedures don't work on the same data, or if you can live by passing the data as procedure parameters.

Object-oriented programming may be a way of life, but it's also a practical means to improve the quality of code. We're not going into the details when to use or not to use object-oriented programming. When you suspect you should go object-oriented, you should try it.

#### Convert a module to a class

Even though classes and modules are different, going from a module to a class may actually be quite simple, provided that the code is suitable.

Before creating your class you should verify that most, if not all, data access is already limited to happen inside the module. By this we mean that no other parts of your program will read or write the variables declared in the module (that will become your class). You ensure this by declaring all variables private. Verify that your project compiles. If it doesn't, you're accessing the variables from outside. You'll need to provide accessor methods to set or get the data. In VB, you build Public (or Friend) properties to get/set the values of private variables.

If your code doesn't compile when your variables are Private, turn them back to Public for now. Write the properties once you have your class ready.

You also need to get rid of public constant and type declarations. Classes don't define public constants or data types. Either change them to Private, or move them to a module that you keep for project-level declarations.

Public Enums are good to leave in the class. That's true if they're required by public methods or properties of your class, but not used in other ways outside of the class. If you can, turn your Enums to Private.

Steps to create a class:

1. Create a new empty class
2. Copy all the code "as is" from the module to the new class
3. Remove the module from the project - but don't delete it yet!
4. Compile & fix repeatedly until your code works. You'll need to fix all the places that reference your old module to references to your new class.

The last step should take the most time. You'll need to create object variables to hold instances of your new class, create the instances with the New keyword, and turn procedure calls to object.method syntax.

If you're working in VB classic (6.0), try not to declare your new object variables like this:

```vb
Dim obj As New Class
```

This is a slow way to program. Everywhere you use the variable obj, VB will check if it's already been instantiated or not. This slows down your program. Instead, declare the variable without the New keyword, and instantiate it separately in a sensible place.

```vb
Dim obj As Class  
Set obj = New Class
```

You may find out that it did not make sense to go object-oriented. If this happens, just revert back to your original module. You did take a backup copy, didn't you?

### HOWTO Encapsulate data access

Classes shouldn't usually allow variable read/write from outside of the class. Instead, you should provide accessor properties that will set and get the variable values.

Encapsulated variables should be declared Private. The use of inheritance in .NET might also justify a Protected variable. The accessor properties are usually Public or Friend depending on your project.

What's so good about encapsulated data? First of all, you can make data read-only (or write-only). So how do you make data read-only (or write-only)? In VB classic, set the Property Let/Set part Private, and you have property that only gets its values from inside the class. In VB.NET you can use the special ReadOnly keyword. Similarly, if you want to create a write-only property, create a Private Property Get, or use VB.NET's WriteOnly keyword.

It's advisable to check the data in the Property Set block before you store it. For example, you can make sure that a numeric value is within acceptable bounds.

So what if you need to change the way you store your data? With properties, no problem. You just rewrite the properties to access the new data storage. No need to touch the code that accesses the properties.

Encapsulation example
Here you can see one example of variable encapsulation. Here the data is read/write, and the acceptable values are from 0 to 130.

```vb
Private mAge As Integer ' Encapsulated variable

' Accessor property to retrieve the value
Public Property Get Age() As Integer
    Age = mAge
End Property

' Accessor property to set the value, verifying that
' the value is in pre-defined limits
Public Property Let Age(ByVal newAge As Integer)
    If newAge >= 0 And newAge <= 130 Then
        mAge = newAge
    Else
        ' Age not in limits, raise a customer error
        Err.Raise 12345, "MyClass.Age [Let]", "Invalid age"
    End If
End Property
```

### HOWTO Limit visibility by scoping

Not all code should be accessible from everywhere in your project(s). You should hide the details and only give a limited number of points of access to any module or class.

Scoping rules are simple. There are only 2:

1. Use as limiting scope as possible. A limited scope enforces modular programming and encapsulation. You access code only via well-defined interfaces and get rid of unpleasant surprises caused by someone accessing code that's not written to be accessed from outside of its context. Use Private whenever possible.

2. Always declare a scope. The VBA default scoping rules are somewhat complicated. If you don't give a scope the declaration can be anything from Public to Private, depending on where you wrote it. When you always write a scope you can't misdefine or misunderstand it. So instead of Dim write Private, instead of Sub write Public or Private Sub, instead of Class write Public/Friend/Private Class. The use of Dim is particularly worth noting. You should use Dim only inside procedures, but never outside of them.

Scope Availability Use

Public Everywhere Use when you need to give access to the whole project, or expose the code to other projects.

Friend In the declaring project Friend is required when building projects that expose an interface to other projects. Use Friend to keep other projects from accessing the code.

Private In the declaring class/module Use for implementation procedures, all data, and enum/user-defined type definitions required only inside the class/module.