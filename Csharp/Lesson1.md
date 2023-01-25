# Lesson 1: Getting Started with C#                     

[Lessons](/category/lessons/)

This lesson will get you started with C# by introducing a few very simple programs. Here are the objectives of this lesson:

*   Understand the basic structure of a C# program.
*   Obtain a basic familiarization of what a “Namespace” is.
*   Obtain a basic understanding of what a _Class_ is.
*   Learn what the _Main_ method does.
*   Learn how to obtain command-line input.
*   Learn about console input/output (I/O).

### A Simple C# Program

There are basic elements that all C# executable programs have and that’s what we’ll concentrate on for this first lesson, starting off with a simple C# program. After reviewing the code in Listing 1-1, I’ll explain the basic concepts that will follow for all C# programs we will write throughout this tutorial. Please see Listing 1-1 to view this first program.

**Warning:** C# is case-sensitive.

##### Listing 1-1. A Simple Welcome Program: Welcome.cs

// Namespace Declaration
using System;

// Program start class
class WelcomeCSS
{
    // Main begins program execution.
    static void Main()
    {
        // Write to console
        Console.WriteLine("Welcome to the C# Station Tutorial!"); 
    }
}

The program in Listing 1-1 has 4 primary elements, a namespace declaration, a class, the _Main_ method, and a program statement. It can be compiled with the following command line:

 csc.exe Welcome.cs

This produces a file named _Welcome.exe_, which can then be executed. Other programs can be compiled similarly by substituting their file name instead of _Welcome.cs_. For more help about command line options, type “csc -help” on the command line. The file name and the class name can be totally different.

**Note for VS.NET Users:** The screen will run and close quickly when launching this program from Visual Studio .NET. To prevent this, add the following code as the last line in the Main method:

// keep screen from going away
// when run from VS.NET
Console.ReadLine();

**Note:** The command-line is a window that allows you to run commands and programs by typing the text in manually. It is often referred to as the DOS prompt, which was the operating system people used years ago, before Windows. The .NET Framework SDK, which is free, uses mostly command line tools. Therefore, I wrote this tutorial so that anyone would be able to use it. Do a search through Windows Explorer for “csc.exe”, which is the C# compiler. When you know its location, add that location to your Windows path. Then open the command window by going to the Windows Start menu, selecting Run, and typing _cmd.exe_. This blog post might be helpful: [How to set the path in Windows 7](http://geekswithblogs.net/renso/archive/2009/10/21/how-to-set-the-windows-path-in-windows-7.aspx).

The first thing you should be aware of is that C# is case-sensitive. The word “Main” is not the same as its lowercase spelling, “main”. They are different identifiers. If you are coming from a language that is not case sensitive, this will trip you up several times until you become accustomed to it.

The namespace declaration, _using System;_, indicates that you are referencing the _System_ namespace. Namespaces contain groups of code that can be called upon by C# programs. With the _using System;_ declaration, you are telling your program that it can reference the code in the _System_ namespace without pre-pending the word _System_ to every reference. I’ll discuss this in more detail in [Lesson 06: Namespaces](http://csharp-station.com/Tutorial/CSharp/Lesson06), which is dedicated specifically to namespaces.

The _class_ declaration, _class WelcomeCSS_, contains the data and method definitions that your program uses to execute. A _class_ is one of a few different types of elements your program can use to describe objects, such as _structs_, interfaces, _delegates_, and _enums_, which will be discussed in more detail in [Lesson 12: Structs](http://csharp-station.com/Tutorial/CSharp/Lesson12), [Lesson 13: Interfaces](http://csharp-station.com/Tutorial/CSharp/Lesson13), [Lesson 14: Delegates](http://csharp-station.com/Tutorial/CSharp/Lesson14), and [Lesson 17: Enums](http://csharp-station.com/Tutorial/CSharp/Lesson17), respectively. This particular _class_ has no data, but it does have one method. This method defines the behavior of this _class_ (or what it is capable of doing). I’ll discuss classes more in [Lesson 07: Introduction to Classes](http://csharp-station.com/Tutorial/CSharp/Lesson07). We’ll be covering a lot of information about classes throughout this tutorial.

The one method within the _WelcomeCSS_ _class_ tells what this _class_ will do when executed. The method name, _Main_, is reserved for the starting point of a program. _Main_ is often called the “entry point” and if you ever receive a compiler error message saying that it can’t find the entry point, it means that you tried to compile an executable program without the _Main_ method.

A _static_ modifier precedes the word _Main_, meaning that this method works in this specific _class_ only, rather than an instance of the _class_. This is necessary because when a program begins, no object instances exist. I’ll tell you more about classes, objects, and instances in[Lesson 07: Introduction to Classes](http://csharp-station.com/Tutorial/CSharp/Lesson07).

Every method must have a return type. In this case, it is _void_, which means that _Main_ does not return a value. Every method also has a parameter list following its name with zero or more parameters between parenthesis. For simplicity, we did not add parameters to _Main_. Later in this lesson, you’ll see what type of parameter the _Main_ method can have. You’ll learn more about methods in [Lesson 05: Methods](http://csharp-station.com/Tutorial/CSharp/Lesson05).

The _Main_ method specifies its behavior with the _Console.WriteLine(…)_ statement. _The console_ is a _class_ in the _System_ namespace._WriteLine(…)_ is a method in the _Console_ class. We use the “.”, dot, operator to separate subordinate program elements. Note that we could also write this statement as _System.Console.WriteLine(…)_. This follows the pattern “namespace.class.method” as a fully qualified statement. Had we left out the _using System_ declaration at the top of the program, it would have been mandatory for us to use the fully qualified form _System.Console.WriteLine(…)_. This statement is what causes the string, “Welcome to the C# Station Tutorial!” to print on the console screen.

Observe that comments are marked with “//”. These are single line comments, meaning that they are valid until the end-of-line. If you wish to span multiple lines with a comment, begin with “/\*” and end with “\*/”. Everything in between is part of the comment. Comments are ignored when your program compiles. They are there to document what your program does in plain English (or the native language you speak with every day).

All statements end with a “;”, semi-colon. Classes and methods begin with “{“, left curly brace, and end with a “}”, right curly brace. Any statements within and including “{” and “}” define a block. Blocks define the scope (or lifetime and visibility) of program elements.

### Accepting Command-Line Input

In the previous example, you simply ran the program and it produced output. However, many programs are written to accept command-line input. This makes it easier to write automated scripts that can invoke your program and pass information to it. If you look at many of the programs, including Windows OS utilities, that you use every day; most of them have some type of command-line interface. For example, if you type **Notepad.exe MyFile.txt** (assuming the file exists), then the _Notepad_ program will open your _MyFile.txt_ file so you can begin editing it. You can make your programs accept command-line input also, as shown in Listing 1-2, which shows a program that accepts a name from the command line and writes it to the console.

**_Danger!_** Regardless of the fact that I documented the proper use of command-line arguments before and after Listing 1-2, some people still send me to email to complain that they get an error or tell me there’s a bug in my program. In fact, I get more email on this one subject than any other in the whole tutorial. **Please read the instructions to include the command-line argument.** <Smile />

**Note:** When running the NamedWelcome.exe application in Listing 1-2, you must supply a command-line argument. For example, type the name of the program, followed by your name: **NamedWelcome YourName**. This is the purpose of Listing 1-2 – to show you how to handle command-line input. Therefore, you must provide an argument on the command-line for the program to work. If you are running Visual Studio, right-click on the project in Solution Explorer, select Properties, click the Debug tab, locate Start Options, and type **YourName** into Command line arguments. If you forget to enter **YourName** on the command-line or enter it into the project properties, as I just explained, you will receive an exception that says “Index was outside the bounds of the array.” To keep the program simple and concentrate only on the subject of handling command-line input, I didn’t add exception handling. Besides, I haven’t taught you how to add exception handling to your program yet – but I will. In [Lesson 15: Introduction to Exception Handling](http://csharp-station.com/Tutorial/CSharp/Lesson15), you’ll learn more about exceptions and how to handle them properly.

##### Listing 1-2. Getting Command-Line Input: NamedWelcome.cs

// Namespace Declaration
using System;

// Program start class
class NamedWelcome
{
    // Main begins program execution.
    static void Main(string\[\] args)
    {
        // Write to console
        Console.WriteLine("Hello, {0}!", args\[0\]);
        Console.WriteLine("Welcome to the C# Station Tutorial!"); 
    }
}

**Tip:** Remember to add your name to the command-line, i.e. “NamedWelcome Joe”. If you don’t, your program will crash. I’ll show you in[Lesson 15: Introduction to Exception Handling](http://csharp-station.com/Tutorial/CSharp/Lesson15) how to detect and avoid such error conditions.

If you are using an IDE, like Visual Studio, see your IDE’s help documentation on how to set the command-line option via project properties. i.e. in Visual Studio 2010, double-click the Properties folder in your solution project, click the Debug tab, and add your name to Command Line Arguments. The actual step can/will differ between IDE’s and versions, so please consult your IDE documentation for more information.

In Listing 1-2, you’ll notice an entry in the _Main_ method’s parameter list. The parameter name is _args_, which you’ll use to refer to the parameter later in your program. The _string\[\]_ expression defines the type of parameter that _args_ are. The _string_ type holds characters. These characters could form a single word or multiple words. The “\[\]”, square brackets denote an _Array_, which is like a list. Therefore, the type of the _args_ parameter is a list of words from the command-line. Anytime you add _string\[\] args_ to the parameter list of the _Main_ method, the C# compiler emits code that parses command-line arguments and loads the command-line arguments into _args_. By reading _args_, you have access to all arguments, minus the application name, that was typed on the command-line.

You’ll also notice an additional _Console.WriteLine(…)_ statement within the _Main_ method. The argument list in this statement is different than before. It has a formatted string with a “_{0}_” parameter embedded in it. The first parameter in a formatted string begins at number 0, the second is 1, and so on. The “_{0}_” parameter means that the next argument following the end quote will determine what goes in that position. Hold that thought, and now we’ll look at the next argument following the end quote.

The _args\[0\]_ argument refers to the first string in the _args_ array. The first element of an Array is number 0, the second is number 1, and so on. For example, if I typed **NamedWelcome Joe** on the command-line, the value of _args\[0\]_ would be “Joe”. This is a little tricky because you know that you typed NamedWelcome.exe on the command-line, but C# doesn’t include the executable application name in the args list – only the first parameter after the executable application.

Returning to the embedded “_{0}_” parameter in the formatted string: Since _args\[0\]_ is the first argument, after the formatted string, of the _Console.WriteLine()_ statement, its value will be placed into the first embedded parameter of the formatted string. When this command is executed, the value of _args\[0\]_, which is “Joe” will replace “_{0}_” in the formatted string. Upon execution of the command-line with “NamedWelcome Joe”, the output will be as follows:

Hello, Joe!
Welcome to the C# Station Tutorial!

### Interacting via the Command-Line

Besides command-line input, another way to provide input to a program is via the Console. Typically, it works like this: You prompt the user for some input, they type something in and press the Enter key, and you read their input and take some action. Listing 1-3 shows how to obtain interactive input from the user.

##### Listing 1-3. Getting Interactive Input: InteractiveWelcome.cs

// Namespace Declaration
using System;
// Program start class
class InteractiveWelcome
{
    // Main begins program execution.
    public static void Main()
    {
        // Write to console/get input
        Console.Write("What is your name?: ");
        Console.Write("Hello, {0}! ", Console.ReadLine());
        Console.WriteLine("Welcome to the C# Station Tutorial!"); 
    }
}

In Listing 1-3, the _Main_ method doesn’t have any parameters — mostly because it isn’t necessary this time. Notice also that I prefixed the _Main_ method declaration with the _public_ keyword. The _public_ keyword means that any class outside of this one can access that class member. For _Main_, it doesn’t matter because your code would never call _Main_, but as you go through this tutorial, you’ll see how you can create classes with members that must be _public_ so they can be used. The default access is _private_, which means that only members inside of the same class can access it. Keywords such as _public_ and _private_ are referred to as access modifiers. [Lesson 19: Encapsulation](http://csharp-station.com/Tutorial/CSharp/Lesson19)discusses access modifiers in more depth.

There are three statements inside of _Main_ and the first two are different from the third. They are _Console.Write(…)_ instead of _Console.WriteLine(…)_. The difference is that the _Console.Write(…)_ statement writes to the console and stops on the same line, but the _Console.WriteLine(…)_ goes to the next line after writing to the console.

The first statement simply writes “What is your name?: ” to the console.

The second statement doesn’t write anything until its arguments are properly evaluated. The first argument after the formatted string is _Console.ReadLine()_. This causes the program to wait for user input at the console. After the user types input, their name in this case, they must press the Enter key. The return value from this method replaces the “_{0}_” parameter of the formatted string and is written to the console. This line could have also been written like this:

string name = Console.ReadLine(); 
Console.Write("Hello, {0}! ", name);

The last statement writes to the console as described earlier. Upon execution of the command-line with “InteractiveWelcome”, the output will be as follows:

\>What is your Name?  <type your name here> \[Enter Key\]  
\>Hello, <your name here>!  Welcome to the C# Station Tutorial!

### Summary

Now you know the basic structure of a C# program. _using_ statements let you reference a namespace and allow code to have shorter and more readable notation. The _Main_ method is the entry point to start a C# program. You can capture command-line input when an application is run by reading items from a _string\[\]_ (string array) parameter to your _Main_ method. Interactive I/O can be performed with the_ReadLine_, _Write_ and _WriteLine_ methods of the _Console_ class.

This is just the beginning, the first of many lessons. I invite you back to take [Lesson 2: Operators, Types, and Variables](http://csharp-station.com/Tutorial/CSharp/Lesson02).
