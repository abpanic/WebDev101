# Lesson 2: Data Types- Operators and Variables 

[Lessons](/category/lessons/)

![Operators, Types, and Variables](./Lesson 1_ Getting Started with C# - C# Station_files/Operators-Types-and-Variables.jpg)

This lesson introduces C# data types, operators and variables. Its goal is to meet the following objectives:

*   Understand what a variable is.
*   Familiarization with C# built-in types.
*   Get an introduction to C# operators.
*   Learn how to use Arrays.

### Variables and Types

“Variables” are simply storage locations for data. You can place data into them and retrieve their contents as part of a C# expression. The interpretation of the data in a variable is controlled through “Types”.

C# is a “Strongly Typed” language. Thus all operations on variables are performed with consideration of what the variable’s “Type” is. There are rules that define what operations are legal to maintain the integrity of the data you put in a variable.

The C# simple types consist of the Boolean type and three numeric types – Integrals, Floating Point, Decimal, and String. The term “Integrals”, which is defined in the C# Programming Language Specification, refers to the classification of types that include sbyte, byte, short, ushort, int, uint, long, ulong, and char. More details are available in the Integral Types section later in this lesson. The term “Floating Point” refers to the float and double types, which are discussed, along with the decimal type, in more detail in the Floating Point and Decimal Types section. The string type represents a string of characters and is discussed in The String Type section, later in this lesson. The next section introduces the boolean type.

### The Boolean Type

Boolean types are declared using the keyword, _bool_. They have two values: _true_ or _false_. In other languages, such as C and C++, boolean conditions can be satisfied where 0 means false and anything else means true. However, in C# the only values that satisfy a boolean condition is _true_ and _false_, which are official keywords. Listing 2-1 shows one of the many ways that boolean types can be used in a program.

##### Listing 2-1. Displaying Boolean Values: Boolean.cs

using System;

class Booleans
{
    public static void Main()
    {
        bool content = true;
        bool noContent = false;
        Console.WriteLine("It is {0} that C# Station provides C# programming language content.", content);
        Console.WriteLine("The statement above is not {0}.", noContent);
    }
}

In Listing 2-1, the boolean values are written to the console as part of a sentence. The only legal values for the _bool_ type are either _true_ or _false_, as shown by the assignment of _true_ to _content_ and _false_ to _noContent_. When run, this program produces the following output:

It is True that C# Station provides C# programming language content.
The statement above is not False.

### Integral Types

In C#, an _integral_ is a category of types. For anyone confused because the word Integral sounds like a mathematical term, from the perspective of C# programming, these are defined as Integral types in the C# programming language specification. They are whole numbers, either signed or unsigned, and the char type. The char type is a Unicode character, as defined by the [Unicode Standard](http://www.unicode.org/). Table 2-1 shows the integral types, their size, and range.

##### Table 2-1. The Size and Range of C# Integral Types

Type

Size (in bits)

Range

sbyte

8

\-128 to 127

byte

8

0 to 255

short

16

\-32768 to 32767

ushort

16

0 to 65535

int

32

\-2147483648 to 2147483647

uint

32

0 to 4294967295

long

64

\-9223372036854775808 to 9223372036854775807

ulong

64

0 to 18446744073709551615

char

16

0 to 65535

Integral types are well suited for those operations involving whole number calculations. The _char_ type is the exception, representing a single Unicode character. As you can see from the table above, you have a wide range of options to choose from, depending on your requirements.

(adsbygoogle = window.adsbygoogle || \[\]).push({});

### Floating Point and Decimal Types

A C# floating point type is either a float or double. They are used any time you need to represent a real number, as defined by IEEE 754. For more information on IEEE 754, visit the [IEEE Web Site](http://www.ieee.org/ "Get information on the IEEE 754 standard supported by C# float and double formats."). Decimal types should be used when representing financial or money values. Table 2-2 shows the floating point and decimal types, their size, precision, and range.

##### Table 2-2. The Floating Point and Decimal Types with Size, precision, and Range

Type

Size (in bits)

precision

Range

float

32

7 digits

1.5 x 10\-45 to 3.4 x 1038

double

64

15-16 digits

5.0 x 10\-324 to 1.7 x 10308

decimal

128

28-29 decimal places

1.0 x 10\-28 to 7.9 x 1028

Floating point types are used when you need to perform operations requiring fractional representations. However, for financial calculations, the _decimal_ type is the best choice because you can avoid rounding errors.

### The String Type

A string is a sequence of text characters. You typically create a string with a string literal, enclosed in quotes: “This is an example of a string.” You’ve seen strings being used in Lesson 1, where we used the _Console.WriteLine_ method to send output to the console.

Some characters aren’t printable, but you still need to use them in strings. Therefore, C# has a special syntax where characters can be escaped to represent non-printable characters. For example, it is common to use newlines in the text, which is represented by the ‘\\n’ char. The backslash, ‘\\’, represents the escape. When preceded by the escape character, the ‘n’ is no longer interpreted as an alphabetical character but now represents a newline.

You may be wondering how you could represent a backslash character in your code. We have to escape that too by typing two backslashes, as in ‘\\\\’. Table 2-3 shows a list of common escape sequences.

##### Table 2-3. C# Character Escape Sequences

Escape Sequence

Meaning

\\’

Single Quote

\\”

Double Quote

\\\\

Backslash

\\0

Null, not the same as the C# _null_ value

\\a

Bell

\\b

Backspace

\\f

form Feed

\\n

Newline

\\r

Carriage Return

\\t

Horizontal Tab

\\v

Vertical Tab

Another useful feature of C# strings is the verbatim literal, which is a string with a @ symbol prefix, as in _@”Some string”_. Verbatim literals make escape sequences translate as normal characters to enhance readability. To appreciate the value of verbatim literals, consider a path statement such as _“c:\\\\topdir\\\\subdir\\\\subdir\\\\myapp.exe”_. As you can see, the backslashes are escaped, causing the string to be less readable. You can improve the string with a verbatim literal, like this: _@”c:\\topdir\\subdir\\subdir\\myapp.exe”_.

That is fine, but you have the problem where quoting text is not as easy. In that case, you would specify double quotes. For example, the string _“copy \\”c:\\\\source file name with spaces.txt\\” c:\\\\newfilename.txt”_ would be written as the verbatim literal _@”copy “”c:\\source file name with spaces.txt”” c:\\newfilename.txt”_.

### C# Operators

Results are computed by building expressions. These expressions are built by combining variables and operators together into statements. The following table describes the allowable operators, their precedence, and associativity.

(adsbygoogle = window.adsbygoogle || \[\]).push({});

##### Table 2-4. Operators with their precedence and Associativity

Category (by precedence)

Operator(s)

Associativity

Primary

x.y  f(x)  a\[x\]  x++  x–  new  typeof  default  checked  unchecked delegate

left

Unary

+  –  !  ~  ++x  –x  (T)x

right

Multiplicative

\*  /  %

left

Additive

+  –

left

Shift

<<  >>

left

Relational

<  >  <=  >=  is as

left

Equality

\==  !=

right

Logical AND

&

left

Logical XOR

^

left

Logical OR

|

left

Conditional AND

&&

left

Conditional OR

||

left

Null Coalescing

??

left

Ternary

?:

right

Assignment

\=  \*=  /=  %=  +=  -=  <<=  >>=  &=  ^=  |=  =>

right

Left associativity means that operations are evaluated from left to right. Right associativity means all operations occur from right to left, such as assignment operators where everything to the right is evaluated before the result is placed into the variable on the left.

Most operators are either unary or binary. Unary operators form expressions on a single variable, but binary operators form expressions with two variables. Listing 2-2 demonstrates how unary operators are used.

##### Listing 2-2. Unary Operators: Unary.cs

using System;

class Unary
{
    public static void Main()
    {
        int unary = 0;
        int preIncrement;
        int preDecrement;
        int postIncrement;
        int postDecrement;
        int positive;
        int negative;
        sbyte bitNot;
        bool logNot;

        preIncrement = ++unary;
        Console.WriteLine("pre-Increment: {0}", preIncrement);

        preDecrement = --unary;
        Console.WriteLine("pre-Decrement: {0}", preDecrement);

        postDecrement = unary--;
        Console.WriteLine("Post-Decrement: {0}", postDecrement);

        postIncrement = unary++;
        Console.WriteLine("Post-Increment: {0}", postIncrement);

        Console.WriteLine("Final Value of Unary: {0}", unary);

        positive = -postIncrement;
        Console.WriteLine("Positive: {0}", positive);

        negative = +postIncrement;
        Console.WriteLine("Negative: {0}", negative);

        bitNot = 0;
        bitNot = (sbyte)(~bitNot);
        Console.WriteLine("Bitwise Not: {0}", bitNot);

        logNot = false;
        logNot = !logNot;
        Console.WriteLine("Logical Not: {0}", logNot);
    }
}

When evaluating expressions, post-increment _(x++)_ and post-decrement _(x–)_ operators return their current value and then apply the operators. However, when using pre-increment _(++x)_ and pre-decrement _(–x)_ operators, the operator is applied to the variable prior to returning the final value.

In Listing 2-2, the _unary_ variable is initialized to zero. When the pre-increment _(++x)_ operator is used, _unary_ is incremented to 1 and the value 1 is assigned to the _preIncrement_ variable. The pre-decrement _(–x)_ operator turns _unary_ back to a 0 and then assigns the value to the _pre Decrement_ variable.

When the post-decrement _(x–)_ operator is used, the value of _unary_, 0, is placed into the _post Decrement_ variable and then _unary_ is decremented to -1. Next, the post-increment _(x++)_ operator moves the current value of _unary_, -1, to the _post Increment_ variable and then increments _unary_ to 0.

The variable _bitNot_ is initialized to 0 and the bitwise not _(~)_ operator is applied. The bitwise not _(~)_ operator flips the bits in the variable. In this case, the binary representation of 0, “00000000”, was transformed into -1, “11111111”.

While the _(~)_ operator works by flipping bits, the logical negation operator _(!)_ is a logical operator that works on _bool_ values, changing _true_ to _false_ or _false_ to _true_. In the case of the _logNot_ variable in Listing 2-2, the value is initialized to _false_, and the next line applies the logical negation operator, _(!)_, which returns _true_ and reassigns the new value, _true_, to _logNot_. Essentially, it is toggling the value of the _bool_ variable, _logNot_.

Furthermore
-----------

The setting of _positive_ is a little tricky. At the time that it is set, the _postIncrement_ variable is equal to -1. Applying the minus _(-)_ operator to a negative number results in a positive number, meaning that _positive_ will equal 1, instead of -1. The minus operator _(-)_, which is not the same as the pre-decrement operator (–), doesn’t change the value of _postInc_ – it applies a sign negation. The plus operator _(+)_doesn’t affect the value of a number, assigning _negative_ with the same value as _postIncrement_, -1.

Notice the expression _(sbyte)(~bitNot)_. Any operation performed on types _sbyte_, _byte_, _short_, or _ushort_ return _int_ values. To assign the result into the _bitNot_ variable we had to use a cast, _(Type)_, operator, where _Type_ is the type you wish to convert to (in this case – _sbyte_). The cast operator is shown as the Unary operator, _(T)x,_ in table 2-4. Cast operators must be performed explicitly when you go from a larger type to a smaller type because of the potential for lost data. Generally speaking, assigning a smaller type to a larger type is no problem since the larger type has room to hold the entire value. Also, be aware of the dangers of casting between signed and unsigned types. You want to be sure to preserve the integrity of your data. Many basic programming texts contain good descriptions of bit representations of variables and the dangers of explicit casting.

Here’s the output from the Listing 2-2:

pre-Increment: 1
pre-Decrement 0
Post-Decrement: 0
Post-Increment: -1
Final Value of Unary: 0
Positive: 1
Negative: -1
Bitwise Not: -1
Logical Not: true

In addition to unary operators, C# has binary operators that form expressions of two variables. Listing 2-3 shows how to use the binary operators.

##### Listing 2-3. Binary Operators: Binary.cs

using System;

class Binary
{
    public static void Main()
    {
        int x, y, result;
        float floatresult;

        x = 7;
        y = 5;

        result = x+y;
        Console.WriteLine("x+y: {0}", result);

        result = x-y;
        Console.WriteLine("x-y: {0}", result);

        result = x\*y;
        Console.WriteLine("x\*y: {0}", result);

        result = x/y;
        Console.WriteLine("x/y: {0}", result);

        floatresult = (float)x/(float)y;
        Console.WriteLine("x/y: {0}", floatresult);

        result = x%y;
        Console.WriteLine("x%y: {0}", result);

        result += x;
        Console.WriteLine("result+=x: {0}", result);
    }
}

And here’s the output:

x+y: 12
x-y: 2
x\*y: 35
x/y: 1
x/y: 1.4
x%y: 2
result+=x: 9

Listing 2-3 shows several examples of binary operators. As you might expect, the results of addition (+), subtraction (-), multiplication (\*), and division (/) produce the expected mathematical results.

The _floatresult_ variable is a floating point type. We explicitly cast the integer variables _x_ and _y_ to calculate a floating point value.

There is also an example of the remainder(%) operator. It performs a division operation on two values and returns the remainder.

The last statement shows another form of the assignment with the operation (+=) operator. Any time you use the assignment with operation operator, it is the same as applying the binary operator to the left hand and right-hand sides of the operator and putting the results into the left-hand side. The example could have been written as _result = result + x;_ and returned the same value.

### The Array Type

Another data type is the Array, which can be thought of as a container that has a list of storage locations for a specified type. When declaring an Array, specify the type, name, dimensions, and size.

##### Listing 2-4. Array Operations: Array.cs

using System;

class Array
{
    public static void Main()
    {
        int\[\] myInts = { 5, 10, 15 };
        bool\[\]\[\] myBools = new bool\[2\]\[\];
        myBools\[0\] = new bool\[2\];
        myBools\[1\] = new bool\[1\];
        double\[,\] myDoubles = new double\[2, 2\];
        string\[\] myStrings = new string\[3\];

        Console.WriteLine("myInts\[0\]: {0}, myInts\[1\]: {1}, myInts\[2\]: {2}", myInts\[0\], myInts\[1\], myInts\[2\]);

        myBools\[0\]\[0\] = true;
        myBools\[0\]\[1\] = false;
        myBools\[1\]\[0\] = true;
        Console.WriteLine("myBools\[0\]\[0\]: {0}, myBools\[1\]\[0\]: {1}", myBools\[0\]\[0\], myBools\[1\]\[0\]);

        myDoubles\[0, 0\] = 3.147;
        myDoubles\[0, 1\] = 7.157;
        myDoubles\[1, 1\] = 2.117;
        myDoubles\[1, 0\] = 56.00138917;
        Console.WriteLine("myDoubles\[0, 0\]: {0}, myDoubles\[1, 0\]: {1}", myDoubles\[0, 0\], myDoubles\[1, 0\]);

        myStrings\[0\] = "Joe";
        myStrings\[1\] = "Matt";
        myStrings\[2\] = "Robert";
        Console.WriteLine("myStrings\[0\]: {0}, myStrings\[1\]: {1}, myStrings\[2\]: {2}", myStrings\[0\], myStrings\[1\], myStrings\[2\]);

    }
}

And here’s the output:

myInts\[0\]: 5, myInts\[1\]: 10, myInts\[2\]: 15
myBools\[0\]\[0\]: true, myBools\[1\]\[0\]: true
myDoubles\[0, 0\]: 3.147, myDoubles\[1, 0\]: 56.00138917
myStrings\[0\]: Joe, myStrings\[1\]: Matt, myStrings\[2\]: Robert

Listing 2-4 shows different implementations of Arrays. The first example is the _myInts_ Array, which is a single-dimension array. It is initialized at declaration time with explicit values.

(adsbygoogle = window.adsbygoogle || \[\]).push({});

Next is a jagged array, _myBools_. It is essentially an array of arrays. We needed to use the _new_ operator to instantiate the size of the primary array and then use the _new_ operator again for each sub-array.

The third example is a two-dimensional array, _myDoubles_. Arrays can be multi-dimensional, with each dimension separated by a comma. It must also be instantiated with the _new_ operator.

Furthermore
-----------

One of the differences between jagged arrays, _myBools\[\]\[\]_, and multi-dimension arrays, _myDoubles\[,\]_, is that a multi-dimension array will allocate memory for every element of each dimension. A jagged array will only allocate memory for the size of each array in each dimension that you define. Most of the time, you’ll be using multi-dimension arrays, if you need multiple dimensions. You will only use jagged arrays in very special circumstances when you can save significant memory by explicitly specifying the sizes of the arrays in each dimension.

Finally, we have the single-dimensional array of _string_ types, _myStrings_.

In each case, you can see those array elements are accessed by identifying the integer index for the item you wish to refer to. Array sizes can be an _int_ type value. Their indexes begin at 0.

### To Wrap Up C# Data Types: Operators and Variables

A variable is an identifier with a type that holds a value of that type. Simple types include the integrals, floating points, decimal, and bool. C# has several mathematical and logical operators that participate in forming expressions. C# also offers the single dimension, multi-dimension and jagged array types.

Integer data type enables a variable to store numeric values. Character data type enables a variable to store only one character. Floating point data type consists of a float and a double. A float enables a variable to store decimal values.  Double data type permits up to 10 digits after the decimal. 

In this lesson, you learned how to write simple statements and code a program that works linearly from start to finish. However, this is not as useful as it can be because you need to be able to make decisions and execute different blocks of code depending on different conditions. I invite you to return for [C# If Statement: Control Selection in Lesson 3](http://csharp-station.com/Tutorial/CSharp/Lesson03), where you can learn how to branch your logic for more powerful decision making.

