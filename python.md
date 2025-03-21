# From Java to Python to Java :)

## Intro

### Some history

Guido van Rossum invented Python in the **late 1980s**. 
The **first** publicly available version of Python was **0.9.0**, which was released in **1991**. 

Van Rossum’s **work** on **Python** was an important contribution to software development and technology in general. 
Today, Python is one of the most commonly used programming languages.

Python was heavily influenced by the ABC programming language. Guido van Rossum invented Python after working with ABC for a number of years. He found some issues with ABC and things he didn’t like, so he decided to come up with an alternative.

> Java was designed by James Gosling at Sun Microsystems. 
> It was released in May 1995 as a core component of Sun's Java platform. 
> The original and reference implementation Java compilers, virtual machines, and class libraries were released by Sun under proprietary licenses.

### Community driven

Today, Python is among the world’s most popular and commonly used programming languages.

**No one** really owns **Python** per se because it's an open-source programming language (although Guido Van Rossum is working for Microsoft nowadays). 

The **Python Software Foundation** (PSF) holds the intellectual property rights for the language.
This non-profit organization was founded in March 2001 and lists its aims as promoting and advancing Python.


### Why should you learn Python (as a Java-dev)

* Its ease of use, **versatility**, and **flexibility** make it ideal for a broad variety of tasks.
* It's always interesting to **learn** a new **language**, makes you a better coder...
* It's very **easy to learn**
* **Cross-Platform** and Open Source
* Supports different programming paradigms (Procedural, OO, Functional, ...)
* An enormous **community-coverage**, specifically in the not typically web-app topics
  * Data Science (pandas, matplotlib, numpy)
  * AI and Machine Learning (scikitlearn, tensorflow)
  * Scripting and Automation (cross-platform alternative to Bash and Powershell)
  * Computer Graphics, OpenCV
  * ...
* **Carreer-opportunities**, check https://www.tiobe.com/tiobe-index/, nowadays it's considered the most popular language
* ...

### Approach and objectives

The concept of this course and presentation is simple, provide a minimum but sufficient knowledge on Python toward Java-dev.  

Basically it's inspired on one of my courses I teach at UCCL, the content can be find at [github](https://github.com/bartvoet/pythoncourse).

Basically I adapted the course for this presentation:

* Removed the code-teaching for novel programmers
* Minimized to an introduction (given in the 1st quarter)
* Translated to English
* Enriched with Java-samples

In this course we will cover what I normally teach in about 8 weeks to novel programmers:

* Language basics (variables, conditions, loops, ...)
* REPL
* Collections (lists, dictionaries, sets, tuples)
* Input/Output
* OOP
* Functional programming

Pay attention, is just to set you up, a lot of the exiting stuff is not covered but it should provide you sufficient basics to read and write simple Python-code

### Installation

#### Linux

Most Linux-distro's include **Python by default** as it is used for a lot of applications in GNU/Linux.  
In case **not** **installed** you can use your **package-manager** in order to install Python.

#### Microsoft Windows

For Microsoft install throug https://www.python.org/downloads/ or the Microsoft store

#### Mac

The preferred way of installing in to Mac is through the brew-package manager

~~~
% brew install python
~~~

### Testing the installation

**Step 1**: write a file with the content:

~~~python
print("Hello World")
~~~

And save it as hello.python

**Step 2**: Navigate to the directory where the file is located on the command line

**Step 3**: Run the script by passing the file to the Python-interpreter

~~~bash
$ python3 hello.python
Hello World
$
~~~

Depending on the installation (on Windows) you might need to replace python3 with python or py...

## Getting started with a "Hello World"

### Let's start with Java...

We start of at the classic "Hello, World!" in **Java**.  
Basically you store the underlying snippet (bypassing packages for simplicity) in a file Hello.Java...

~~~java
public class Hello {
    public static void main(String[] args) {
        System.out.println("Hello, World!"); 
    }
}
~~~

...and after this you can run - the main-function - a Java-program.  
Without the help of an IDE or Gradle/Maven this is performed in 2 steps:

~~~bash
$ javac Hello.java
$ ls
Hello.class  Hello.java 
$ java Hello
Hello World!
$
~~~

### And now in Python...

In **Python** you **write** this as a **one-liner**

~~~python
print("Hello, World!")
~~~

Python-scripts are stored in files with py as extension.  
Let's store the snippet in file hello.py and run it.

As it was with **writing**, **running** a Python-script is also **one-liner**

~~~bash
$ python3 hello.python
Hello World!
$
~~~

> Note: Depending on the system and how you've installed the python-interpreter can be referenced with python, python3 or py.  
> The examples in this case are tested on a Linux-distro where you most commonly refer "Python 3" with python3.

### Some first observations

#### Python is a scripting-language in nature

Obviously Python is a **scripting language**, you can run the code in place **without** **intermediate build** phases

Just like other scripting language you just write the script and feed it directly to the interpreter.

#### Python is a hybrid language

You can **run** command line-programming without defining a class without defining a main-function (like in other languages like Java, C, C++, ...).  

Python - as you will see later - has quite good **support** for both **OOP** and **FOP** but scales perfectly to basic **procedural scripting-style**.

You don't need to use an class-system to perform typical day-to-day features like a simple print-function, reading a file, requesting input...  
The print-function is a first class member and directly accessible (without static import)

#### Buy buy semicolons ";"

**No semicolons** are required.  
Simple statements can be distinguished from each other by new lines

~~~python
print("Hello, World!")
print("Greetings from Python")
~~~

Note:  
Actually they are allowed in Python, you could do the following in Python but 
it doesn't make to much sense in the Python-philosophy as you will see with the concept of blocks. 

~~~python
print("This is something allowed");
print("But which is never used in Python");
~~~

#### Similarities to java

The syntax in calling functions is similar to how you invoke them in java Java.

## REPL - interactive Python

Python code can be executed in 2 ways:

* **File-based:** execute python statements from inside a file
* **Interactive:** from within a shell execute statement by statement and do instant results

### Interactively execute code (or REPL)

A **REPL** is provided for some programming languages -and/or environments.  
This stands for **R**ead **E**val **P**rint **L**oop:

* **R**ead: reading an expression from the user.
* **E**val: evaluation of this expression and ultimately its execution
* **P**rint: print out the result of this expression (if there is one)
* **L**oop: wait (continuously) again for the next expression or statement

You get immediate **feedback on your statements**, so to speak....

### Interactive "Hello World"

You simply open the REPL by typing the **python command** (python3 on Linux Mint in the example below)

~~~bash
$ python3
Python 3.4.2 (default, Oct 8 2014, 10:45:20) 
[GCC 4.9.1] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 
~~~

From that **>>>** appears (preceded by some system info) you can get started and run Python statement or commands.  
We will continue with some commands:

### Expressions

A first use is to call an expression

~~~
$ python3
Python 3.4.2 (default, Oct 8 2014, 10:45:20) 
[GCC 4.9.1] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 5 + 5
10
>>>
~~~

In this example, we will type a one expression *"5 + 5"* followed by a enter.   
The interpreter will:

* execute this expression 
* capture the result
* and print on the next line.  


~~~
$ python3
Python 3.4.2 (default, Oct 8 2014, 10:45:20) 
[GCC 4.9.1] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 5 + 5
10
>>>
~~~


### Valid code

Obviously, you must enter valid expressions and/or statements, otherwise an error message will remain.  

~~~
$ python3
Python 3.6.8 (default, Oct  7 2019, 12:59:55) 
[GCC 8.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 3 +
  File "<stdin>", line 1
    3 +
      ^
SyntaxError: invalid syntax
>>> 
~~~


What is interesting is that the interpreter does not terminate and you can retry your code.   
In file-based programming, the program would be terminated.... 

Previous example was an invalid syntax, next example is a valid syntax but referencing an undefined variable.

~~~
$ python3
Python 3.6.8 (default, Oct 7 2019, 12:59:55) 
[GCC 8.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> a = 5
>>> print(b)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'b' is not defined
>>> print(a)
5
>>>
~~~

After the error, you can correct the code, and print the correct variable - a-.

### Handy calculator

~~~python
>>> x = 5 + 2 - 3 * 2
>>> x
1
>>> x = 5 + (2 - 3) * 2
>>> x
3
>>> 5 / 2
2
>>> 5 // 2
2
>>> 5.5 / 2
2.75
>>> 2 ** 8
256
>>> 5 % 2
1
>>>
~~~

### Sequential implementation

In addition to pure expressions, you can enter ordinary statements just like a program.

~~~python
>>> message = "Hello World"
>>> print(message)
Hello World
>>>
~~~

In this case, we perform 2 statements:

* initialize a variable
* print this variable

These statements - as with file-based execution - are executed in the order that you entered them.

### More complex examples

In addition to sequential statements, you can also create more complex structures such as functions and block statements.   
The example below contains a function followed by a loop

~~~python
>>> def print_number(i):
...     print("hello " + str(i))
...
>>> loops = 5
>>> for i in range(loops):
...     print_number(i)
...
hello 0
hello 1
hello 2
hello 3
hello 4
>>>
~~~

When the interpreter recognizes that a block follows (at the function and for) the prompt changes to a **block mode**, you can recognize this by the **...** instead of the **>>**.  
In this mode you can type code without it not being executed after an entry.

To get out of this mode you have to type enter twice, then this code is executed (or in case of a function it is created and made available).

### Leaving the console

To exit the REPL, call the exit() function

~~~
$ python3
>>> exit()
$
~~~

### Tips...

The REPL is an incredibly useful tool that allows you to test or try something out in a short amount of time.  
We will come back to this in Part 3 with some additional tips and tricks, some things you can already try out:

#### Tab completion

Python completes code where possible when you type a tab....  

~~~
Python 3.6.7 (default, Oct 22 2018, 11:32:17)
[GCC 8.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> wh
~~~

If you type a tab after this wh appears 

~~~
Python 3.6.7 (default, Oct 22 2018, 11:32:17)
[GCC 8.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> while
~~~

If there are several possibilities, this one will be shown, for example if we type only w

~~~
Python 3.6.7 (default, Oct 22 2018, 11:32:17)
[GCC 8.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> w
while with
>>> w
~~~

#### History

The REPL omits the previous commands you typed, by using the arrow keys you can browse through the previously typed commands.

#### Help!!!

There is also a help function provided, if you call it without arment you will come to a new interactive console.  
A full explanation is beyond the scope of an introduction but on the basis of this initial comment you can already look up some things
You can exit with the keyword quit.

You can also include an argument to get more info about functions ...

~~~
>>> help("print")
Help on built-in function print in module builtins:

print(...)
    print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)

    Prints the values to a stream, or to sys.stdout by default.
    Optional keyword arguments:
    file:  a file-like object (stream); defaults to the current sys.stdout.
    sep:   string inserted between values, default a space.
    end:   string appended after the last value, default a newline.
    flush: whether to forcibly flush the stream.
(END)
~~~

Or data types

~~~
Help on class int in module builtins:

class int(object)
 | int(x=0) -> integer
 | int(x, base=10) -> integer
 |
 | Convert a number or string to an integer, or return 0 if no arguments
 | are given.  If x is a number, return x.__int__().  For floating point
 | numbers, this truncates toward zero.
 |
 | If x is not a number or if base is given, then x must be a string,
 | bytes, or bytearray instance representing an integer literal in the
 | given base.  The literal can be preceded by '+' or '-' and be surrounded
 | by whitespace.  The base defaults to 10.  Valid bases are 0 and 2-36.
 | Base 0 means to interpret the base from the string as an integer literal.
 | >> int('0b100', base=0)
 | 4
 |
 | Methods defined here:
 |
 | __abs__(self, /)
 | abs(self)
 |
 | __add__(self, value, /)
 | return self+value.
 |
 | __and__(self, value, /)
 | Return self&value.
 |
 | __bool__(self, /)
 | self != 0
 |
 | __ceil__(...)
 | Ceiling of an Integral returns itself.
 |
 | __divmod__(self, value, /)
 | Return divmod(self, value).
 |
 | __eq__(self, value, /)
 | Return self==value.
 |
:
~~~

> Om deze schermen te verlaten dien je "q" te typen.

## Variables and dynamic typing

Now we reviewed/compared a simple "Hello World".  
Let's now look at how variables are used in Python vs Java and that's a little different...

### Variables in Python vs Java

Let's change the previous example and store our message in a variable

~~~java
public class Hello {
    public static void main(String[] args) {
        String message = "Hello, World!";
        System.out.println(message); 
    }
}
~~~

Below you see the equivalent in Python and you observe directly a big difference...

~~~python
message = "Hello World"
print(message)
~~~

In Python you can **define** a **variable** just as in Java but you
**don't need** to **declare** a **type** (not even a keyword like var)

### References (handles) are dynamically typed

You might think the type of the reference is inferred like it
is with the var-keyword in Java...

~~~java
class HelloWorld {
    public static void main(String[] args) {
        var message = "Hello, World!";
        System.out.println(message); 
    }
}
~~~

...but that's not really the case  
In **Java** a **reference/handle** is actually **containing** some **type-information** on the object it's referring to (e.g. interface or class that the actual heap-object is implementing).  

In Python this is just a simple label (name) and a pointer to the object.  
This means that you can **change** the object it's pointing to an object of another type like in the example below...

~~~python
message = "Hello World"
print(message)
message = 1 + 3
print(message)
~~~

Important to not here is that in Python everything is an object which is not the
case in Java where primitives are not stored as references.

## Primitive datatypes

Now we know how Python treats variables, let's consider the basic built-in primitive types.  

Python has a relative simple type-system compared to Java.
The 5 primitive data structures are:

* Integers
* Floats
* Strings
* Booleans
* Complex Numbers

> Strings are indeed more complex compared to number being backed by a buffer...

### type-operator

Python has a built-in function (actually an operator) **type()** allowing 
you to identify the type.  

~~~python
a = "hello"
print(type(a))
a = 1
print(type(a))
a = True
print(type(a))
a = 5.5
print(type(a))
a = 1 + 2j
print(type(a))
~~~

If you run the snippet above you would see the following printout:

~~~
<class 'str'>
<class 'int'>
<class 'bool'>
<class 'float'>
<class 'complex'>  
~~~

> Interestingly enough it indicates the class keyword
> everything in Python in actually an object stored on the heap
> in contrast to Java that keeps it's primitives on the stack
> (when these are not attributes)

### Numbers

#### Floating point

**Java** contains **double (64-bit) and float (32-bit)** depending on the size you need.  
**Python** on the other hand has only one integer type **double**

Both Java and Python use floating point for theire decimal numbers...

~~~java
public class DoubleTest {
    public static void main(String[] args) {
        System.out.println(0.2 + 0.1); 
    }
}
~~~

~~~python
print(0.2 + 0.1)
~~~

...as illustrated hereunder in the execution

~~~bash
$ python double_test.py
0.30000000000000004
$ javac DoubleTest
0.30000000000000004
~~~

#### Integers

**Java** contains **byte, short, int or long** depending on the size you need.  
**Python** on the other hand has only one integer type **int**

#### Arbitrary precision integers

Where each type in Java has a specific length in python the precision is arbitrary.  
An integer is not limited by a number of bytes but is backed internally by a buffer.

If you e.g. define a very large number

~~~python
b = 1000000000000000000000000000000000000000000000000000000000000
c = b + 111
print(c)
print(c * b)
~~~

If you would run this it will execute without error

~~~
1000000000000000000000000000000000000000000000000000000000111
1000000000000000000000000000000000000000000000000000000000111000000000000000000000000000000000000000000000000000000000000
~~~

In Java this would be blocked by the compiler

~~~java
public class Hello {
    public static void main(String[] args) {
        int b = 1000000000000000000000000000000000000000000000000000000;
        String message = "Hello, World!";
        System.out.println(message); 
    }
}
~~~

When you would build the following class

~~~bash
$ javac Hello.java
Hello.java:3: error: integer number too large
        int b = 1000000000000000000000000000000000000000000000000000000;
                ^
1 error
$
~~~

> In Java you would use a BigInteger for these kind of scenario's

#### Operations

All types suport the following arithmetic operators identical to Java with
the **exception** of the **true-division** and **power-operator**

| Operator   |   Meaning            |
|------------|----------------------|
| +          | addition             |
| -          | substraction         |
| *          | multiplication       |
| /          | floor-division       |
| //         | true-division        |
| %          | remainder            |
| **         | power                |

~~~python
x = 10.5
y = -3

print("x + y =", x + y)                  # addition
print("x - y =", x - y)                  # subtraction
print("x * y =", x * y)                  # multiplication

print("x / y =", x / y)                  # normal division
print("x // y =", x // y)                # integer division
print("x % y =", x % y)                  # modulo

print("abs(y) =", abs(y))
print("int(x) =", int(x))                # convert to integer
print("float(y) =", float(y))            # convert to float
print("complex(x, y) =", complex(x, y))  # convert to complex

print("pow(x, 3) =", pow(x, 3))          # exponentiation
print("x ** 3 =", x ** 3)                # exponentiation (alternative syntax)
~~~

#### No increment operator

In most C-like languages (as Java is) the increment en decrement-operators are supported.  

~~~java
public class Hello {
    public static void main(String[] args) {
        int i = 1;
        System.out.println(i++); 
        System.out.println(++i); 
    }
}
~~~

Python however does not have such a special syntax.  
To increment x by 1 you're limited to the following

~~~python
i += 1 
i = x + 1 .
~~~

This is partly due to the fact that Python is not supporting the typical
for-loops we know from Java as we will see a little bit further.

#### True division operator

When dividing 2 integers in Java the result is a rounded integer

~~~java
class Hello {
    public static void main(String[] args) {
        System.out.println(5 / 2); 
    }
}
~~~

If you want an floating-point result you need an explicit cast on one of both integers.

~~~java
public class Hello {
    public static void main(String[] args) {
        System.out.println((double)5 / 2); 
    }
}
~~~

In Python however there are 2 operators

~~~python
print(5 // 2) # 2
print(5 / 2) # 2.5
~~~

### Strings

#### Declaring Strings

Strings in Python are very similar in Java.  
One important difference is that you can declare String with both single and double quotes

~~~python
print("hello")
print('hello')
~~~

This can come in quite handy if you want to print explicitly single of double quotes like hereunder.  Running the code below...

~~~python
print("'hello'")
print('"hello"')
~~~

...results in...

~~~
'hello'
"hello"
~~~

> Using both type of quotes is possible because you char's don't exist in Python

#### Concatenating strings

String concatenation is similar in Python compared to Java:

~~~java
public class StringConcatenation {
    public static void main(String[] args) {
        System.out.println("Hello " + "World " + "in Java");
        System.out.println(String.join("Hello ","World", "in Java"));
        System.out.println(new StringBuilder()
                                .append("Hello")
                                .append("World")
                                .append("in Java")
                                .toString());
    }
}
~~~

Both basic concatenation as a join-operation is provided in Python

~~~python
print("Hello " + "World " + "in Java");
print("".join("Hello ","World", "in Java"));
~~~

#### String formatting

In Java you can replace concatenation with typical String-formatting.  
e.g. the following example...

~~~Java
public class HelloFormatting {
    public static void main(String[] args) {
        String baseString = "Hello %s! This course takes about %d minutes.";
        String target = "World";
        int minutes = 120;
        String result = String.format(baseString, target, minutes);
        System.out.println(result);
    }
}
~~~

...results in the following output:

~~~
Hello World! This course takes about 120 minutes.
~~~

The equivalent in Python is:

~~~python
baseString = "Hello {target}! This course takes about {minutes} minutes.";
target = "World";
minutes = 120;

print(baseString.format(target = target, minutes = minutes ))
~~~

However starting Python 3.10 takes this one level further with fstrings which are introduced 

~~~python
target = "World";
minutes = 120;

print(f"Hello {target}! This course takes about {minutes} minutes.")
~~~

This binds basically directly variables or members of a class to the string
without the need of passing variables to a format method.

> Don't wory, one day a similar feature will be available in Java :)  
> See https://openjdk.org/jeps/430

~~~python
pi = 3.14159265359
print(pi)

# > 3.14159265359

print(f"{pi:.0f}")     # no decimal places
print(f"{pi:.2f}")     # two decimal places
print(f"{pi:.3e}")     # scientific notation

# > 3
# > 3.14
# > 3.142e+00

ratio = 0.25
print(f"{ratio:.1%}")  # percentage
~~~

## Code blocks: Java vs Python (buy buy braces)

Up till now we only demonstrated sequential code, this is code
without any conditions or repetitions.

Now we will start of complex statements with a basic if-statement
as we know this from Java:

~~~java
public class CodeBlockDemo {
    public static void main(String[] args) {
        int i = 5;
        if (i > 0) {
            System.out.println("I is bigger");
            System.out.println("Extra sysout just to demonstrate a block");
        }
        System.out.println("After the code block");
    }
}
~~~

The same code translated into Python renders into the following:

~~~python
i = 5
if i > 0:
    print("I is bigger")
    print("Extra sysout just to demonstrate a block")
print("After the code block")
~~~

The code is pretty readable for a Java-developer but there are some important differences:

In Python you don't use braces {} to demarcate a code block.  
Basically you just use tabs to indicate where a code block starts and ends

Beside that, before every code block there is a construct ending by a colon.  
This could be an if-clause (if + the boolean-expression) but you will see the same with functions.

~~~python
def hello_function():
    print("Hello")
    print("From Python")
hello_function()
~~~

> More on function in a while...

## Control (and code blocks)

Now we know how code blocks are used lets dive in control-constructs in Python

### Relational operators

| Operator   |   Meaning              |
|------------|------------------------|
| ==         | equals                 |
| !=         | not equals             |
| <          | smaller                |
| >          | greater                |
| <=         | smaller or equal       |
| >=         | bigger or equal        |

Same as in Java, Python compares 2 numbers/objects and returns a boolean as result

~~~python
a = 5
b = 6
c = a < b 
print(c)   # prints False
d = a > b
print(d)   # prints True
~~~

### Logical operators

The logical operators are different but with identical semantics:


| Operator   |   Java-operator      |
|------------|----------------------|
| and        | &&                   |
| or         | \|\|                 |
| not        | &&                   |


### if - else

Same as in Java you can use an else-clause

~~~python
x = 5
if x < 0:
    print("negative")
else:
    print("positive")
~~~

And basically you can nest an if (or something else) in these clauses...

~~~python
x = 0
if x < 0:
    print("negative")
else:
    if x == 0:
        print("zero")
    else:
        print("positive")
~~~


### elif

~~~python
x = 0
if x < 0:
    print("negative")
elif x == 0:
    print("zero")
else:
    print("positive")
~~~

### Ternary expression vs if expression

In Java there's is a **shorthand** for **if-else** you can use for retrieving values called
the ternary operator as shown below.

~~~java
public class Hello {
    public static void main(String[] args) {
        int i = 5;
        String result = i > 0 ? "positive" : "negative";
        System.out.println(result);
    }
}
~~~

The **counterpart** in **Python** is a **conditional expression** as shown **below**.

~~~python
i = 5
result = "positive" if i > 0 else "negative"
print(result)
~~~

The syntax of this construct seems to be pretty natural...


### Switch - case vs match - case

~~~python
choices = """
A. Choice A
B. Choice B
C. Choice C
"""

print(choices)
choice = input("Please give input: ")
match choice.upper():
    case "A": print("Choice A")
    case "B": print("Choice B")
    case "C": print("Choice C")
    case _ : print(f"Choice {choice} doesnt exists")
~~~

### while-loop (no do while)

* continue and break

### for-loop

~~~python
for i in range(5):
    print(i)
~~~

## Comments

In **Java** we distinguish **2 types of comments** (beside Javadoc):

* One line comments starting with slashes
* 2 line comments starting with 
  
~~~java
// One line comment
class HelloWorld {
    public static void main(String[] args) {
        String message = "Hello, World!";
        System.out.println(message); 
    }
}
/*
Multiline comment
*/
~~~

In **Python** one-line-comments are marked as indicated below

~~~python
# One line comment
message = "Hello World"
print("hello world")
'''
Multiline comments
over here
'''
~~~

Multiline comments are marked by 3 quotes (can be single or double)


## Some more input and output...

As Python is frequently used as a scripting-language, knowing how to read and write data to the command line is
very important...

### Printing to the console


~~~java
import java.io.Console;

public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
~~~

~~~python
greeting = "Hello"
name = "World"
print(greeting, name)
~~~

~~~java
import java.io.Console;

public class HelloWorld {
    public static void main(String[] args) {
        System.out.print("Hello ");
        System.out.print("World");
    }
}
~~~



~~~python
print("Hello", end="")
print("World")
~~~

### Reading input from command line

First thing, how to write to and read data from the command line?
In **Java**, there are multiple options:

* You could use e.g. a **BufferedReader**:

~~~java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;

public class ReadFromCommandLineReader {
    public static void main(String[] args) throws IOException {
        BufferedReader r = new BufferedReader(new InputStreamReader(System.in));
        
        System.out.println("Enter some text");
        String s = r.readLine();
        
        System.out.println("You typed: " + s);
    }
}
~~~

* Or use a the **Scanner**-class, allowing you directly reading numbers without explicitly parsing the values

~~~java
import java.util.Scanner;

public class ReadFromCommandLineScanner {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
       
        System.out.println("Enter a number");
        int number = scanner.nextInt(); //nextLine() for just strings...

        System.out.println("The number is: " + number);
    }
}
~~~

> (3rd option is the Console-class described further)

In **Python**, reading from the console is a first-class concept, just like for printing you don't need to use classes or objects, just use a simple function **input**.  

~~~python
name = input("Give name please: \n")
print(f"Hello {name}")
~~~

An extra nice thing about the input function is that it allows you to pass and accompanying text
that is printed to the console.

~~~python
text = input("Enter some text: \n")
print(f"Hello {text}")
~~~

~~~python
print("Enter some text: ")
text = input()
print(f"Hello {text}")
~~~

### Reading a password

Another (3rd) way of reading input from the console in Java is through the Console-class.  
The readLine() allows like Python passing a text you can introduce and this class allows you to read passwords from the command line without the input being echoed to the console.

~~~Java
import java.io.Console;

public class ReadFromCommandLinePassword {
    public static void main(String[] args) {
        Console console = System.console();
        
        char[] password = console.readPassword("Please provide you password: ");
        console.printf(String.valueOf(password));
    }
}
~~~

Evidently this functionality also exists in Python...

~~~python
import getpass

print("Please provide you password")
password = getpass.getpass()
print(f"Your password is {password}")
~~~

### Reading and writing text-files

Reading a text-file Java as shown below...

~~~Java
import java.io.BufferedReader;
import java.io.FileInputStream;
import java.io.IOException;
import java.io.InputStreamReader;

public class ReadAFile {

 public static void main(String[] args) throws IOException{
        BufferedReader fileReader = new BufferedReader(
                                        new InputStreamReader(
                                            new FileInputStream("sample.txt")));
        System.out.println(fileReader.readLine());
        fileReader.close();
    }
}
~~~

...is a little bit more **condense** in Python, no complex decorating of InputStream and Readers...

~~~python
read_file = open("sample.txt", "r")
print(read_file.read())
read_file.close()
~~~

After use, it is important to **close** this **file object** - as it is in Java - with the operation close.  
This is because the operating system can lock the file for use from other programs as long as this file object is open.

~~~python
filename = "test.txt"

write_file = open(filename, "w+")
write_file.write("Hello\n")
write_file.write("File!\n")
write_file.close()

read_file = open(filename, "r")
for line in read_file.read().splitlines():
    print(line)

print(read_file.closed, write_file.closed)
read_file.close()
print(read_file.closed, write_file.closed)
~~~

#### Relative vs absolute

Previous example opened a file that is in the same directory from which you run the python program.
You can also say that this file is **relative** to the path where your application is executed.

If there is a the file in a subdirectory from which your program is executed you can describe a path as follows:

~~~python
f = open("subdirectory/demofile.txt")
# Some operations...
f.close()
~~~

In addition if you want to describe an exact path

~~~python
f = open("/home/bart/demofile.txt")
# Some operations...
f.close()
~~~

(and to please the Windows users)

~~~python
f = open("c:\users\bart\demofile.txt")
f.close()
~~~

#### Modes


A first notion you need to know is the use of modes when opening a file:

* "r" - Read
* "x" - Create - creates a file and returns an error if the file already exists
* "a" - Append - creates a file if it does not exist, all writes are appends
* "w" - Write - creates a file if it does not yet exist, overwrites existing file

You can **pass** this **mode** as a **2nd** (optional) **argument**

~~~python
with open("demofile.txt", "r") as f:
  print(f.read()) 
~~~

If you don't add this **2nd argument**, the **default** mode is **r** (read-only) 

#### Binary mode

In addition to read/write/append you can use modes also to indicate text vs binary mode.  
At the first line in below code-snippet **b** is used to indicate that we want to read in binary mode

~~~python
read_file = open("test.txt", "rb")
print(f"Type when opening in binary mode: {type(read_file)}")
print(read_file.read())
read_file.close()

read_file = open("test.txt", "r")
print(f"Type when opening in text mode: {type(read_file)}")
print(read_file.read())
read_file.close()
~~~

If you look at the output of the snippet, you might see that open creates different implementations in the background
depending on the mode you passed around as argument...

~~~
Type when opening in binary mode: <class '_io.BufferedReader'>
b'Hello\nFile!\n'
Type when opening in text mode: <class '_io.TextIOWrapper'>
Hello
File!
~~~

### Reading from a text-file 

To demonstrate how to handle a text-file start by creating a file called **demofile.txt** with the following (meaningless) content:

~~~
Lorem ipsum dolor sit amet, consectetuer adipiscing elit. 
Aenean commodo ligula eget dolor. Aenean massa. 
Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. 
Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim. 
Donec pede justo, fringilla vel, aliquet nec, vulputate eget, arcu. In enim justo, rhoncus ut, imperdiet a, venenatis vitae, justo. Nullam dictum felis eu pede mollis pretium. 
Integer tincidunt. Cras dapibus. 
Vivamus elementum semper nisi. Aenean vulputate eleifend tellus. 
Aenean leo ligula, porttitor eu, consequat vitae, eleifend ac, enim. 
Aliquam lorem ante, dapibus in, viverra quis, feugiat a, tellus. Phasellus viverra nulla ut metus varius laoreet. 
Quisque rutrum. Aenean imperdiet. Etiam ultricies nisi vel augue. Curabitur ullamcorper ultricies nisi. Nam eget dui
~~~

#### Read out entire content

You can retrieve the entire contents of a text file via the read function.

~~~python
with open("demofile.txt", "r") as f:
  print(f.read()) 
~~~
The above will print the entire text (as above).

You can also limit yourself to the number of bytes (in case of text files the characters)

~~~python
with open("demofile.txt", "r") as f:
  print(f.read(5)) 
  print(f.read(5)) 
~~~

Bemerk ook dat de positie tot waar je al hebt gelezen wordt bijgehouden in het file-object

~~~
Lorem
 ipsu
~~~

#### Read line by line

You can also choose to read out line by line.

~~~python
with open("demofile.txt", "r") as f:
  print(f.readline())
  print(f.readline()) 
~~~

The above code will print the 2 first lines.

~~~
Lorem ipsum dolor sit amet, consectetuer adipiscing elit. 
Aenean commodo ligula eget dolor. Aenean massa.
~~~

#### Running through all lines

The file object can also behave like a list of lines;  
On this object you can then execute a loop through the entire file.

~~~python
with open("demofile.txt", "r") as f:
  for x in f:
    print(x) 
~~~

~~~
Lorem ipsum dolor sit amet, consectetuer adipiscing elit. 
Aenean commodo ligula eget dolor. Aenean massa. 
Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. 
Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.
...
~~~

### Writing to a a file

For writing to a file, there are 3 main modes we need to understand:

* Writing a new file => x (returns an error if it already exists)
* Overwriting an existing file => w
* Add to the end of a file => a

#### Creating a new file

The first scenario is that we want to create a new file.  
In this case, we use the mode **x**

~~~python
with open("hello.txt", "x") as f:
  f.write("This is a new file!!!")
with open("hello.txt", "r") as f:
  print(f.read()) 
~~~

If the file should not yet exist, a new hello.txt file will be created

~~~
$ python3 create_new_file.py
This is a new file!!!
$
~~~

Should this file already exist, for example by running the program a 2nd time an exception will be raised by the open function

~~~
$ python3 create_new_file.py
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>.
FileExistsError: [Errno 17] File exists: 'hello.txt'
$
~~~

#### New file or overwrite existing file

If we change the same code to use the mode **w**:

* no error** will be raised if the **file already exists**
* but it will be **overwritten**
* if it does **not exist** it will be **created**

Code below:

~~~python
with open("hello.txt", "w") as f:
  f.write("This is a new file!!!")
with open("hello.txt", "r") as f:
print(f.read()) 

with open("hello.txt", "w") as f:
f.write("The file has been overwritten!!!")
with open("hello.txt", "r") as f:
  print(f.read()) 
~~~

* Will create the file first (if it doesn't already exist)
* And then overwrite the contents

~~~
$ python3 create_new_file.py
This is a new file!!!
The file has been overwritten

$
~~~

#### Add to the end of the text-file

~~~python
with open("hello.txt", "w") as f:
  f.write("This is a new file!!!")
with open("hello.txt", "r") as f:
  print(f.read()) 

with open("hello.txt", "a") as f:
  f.write("This line has been added!!!")
with open("hello.txt", "r") as f:
  print(f.read()) 
~~~

~~~
$ python3 append_to_file.py
This is a new file!!!

This is a new file!!!
This line has been added!!!
$
~~~

#### Check if the file exists

You can avoid this exception by checking if this file already exists, which you can do with the exists() function
Thus, you can improve the above code by shielding the remove() call with an if clause

~~~python
import os
if os.path.exists("demofile.txt"):
  os.remove("demofile.txt")
else:
  print("The file does not exist") 
~~~

#### Deleting a directory

To remove a directory you need to use the rmdir() function

~~~python
import os
os.rmdir("a_folder") 
~~~

* Note that this will fail if the directory does not exist 

~~~
...
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>.
FileNotFoundError: [Errno 2] No such file or directory: 'a_folder'
>>> 
~~~

> To avoid this you can use os.path.exists()

* If the directory is not empty you will also get an error

~~~
...
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
OSError: [Errno 39] Directory not empty: 'a_folder'
~~~

#### Further info

There are still many ways to edit files and directories.  
To learn about them please visit https://docs.python.org/3/tutorial/inputoutput.html#reading-and-writing-files


### With statement

In modern Java you're supposed to open **"closeable resources"** with a try-with-resources as shown below

~~~Java
public class Hello {
    public static void main(String[] args) {
        try (FileReader fr = new FileReader("hello.txt");
                BufferedReader br = new BufferedReader(fr)) {
            return br.readLine();
        }
    }
}
~~~

The **equivalent operation** in Python is:

~~~python
filename = "test.txt"

with open(filename, "w+") as write_file:
  write_file.write("Hello\n")
  write_file.write("File!\n")

with open(filename, "r") as read_file:
  for line in read_file.read().splitlines():
      print(line)
~~~

Same as in Java this will make sure **close** the **resource** automatically within the with-block

## Functions

Let's start with a simple static function.

> Don't worry, we will tackle OOP in a minute

~~~java
class HelloWorld {
    public static void printMessage(String message) {
        System.out.println(message); 
    }

    public static void main(String[] args) {
        String message = "Hello, World!";
        sayMessage(message); 
    }
}
~~~

As static function starts out with

* def-keyword
* function-label 
* followed by an argument

~~~python
def print_message(name, message):
    print("Hello", name, ", the message is", message)

name = "Bart"
message = "Hello World"
print_message(name, message)
~~~


~~~python
def print_message(message, name):
    print("Hello {name}, the message is {message}")

message = "Hello World"
print_message(message)
~~~

Function-arguments are as the variables not typed

### Function with arguments and return value

~~~python
def print_message(name, message):
    print("Hello {name}, the message is {message}")

def add(x, y):
    total = x + y
    return x + y

message = "Hello World"
print_message(message)
print(add(5,6))
~~~

### Passing arguments by name

~~~python
def print_message(name, message):
    print("Hello {name}, the message is {message}")

def add(x, y):
    total = x + y
    return x + y

message = "Hello World"
print_message(message="Hello", name="Bart")
~~~

### Empty function (pass-)

As Java uses braces it's easy to demarcate the start and end of a function like below

~~~java
class HelloWorld {
    public static void emptyFunction() {
        
    }
}
~~~

Python however requires at least one line to identify the start and end of a function or code block.

~~~python
def empty_function():
    pass
~~~

The same rule applies to if-else, loops, classes without content

### Default values

~~~python
def print_message(name, message = "Welcome") -> None:
    print("Hello {name}, the message is {message}")

def add(x:int, y = 1:int) -> int:
    total = x + y
    return x + y

message = "Hello World"
print_message(message)
print(add(5))
~~~

### Function and type-hinting

~~~python
def print_message(name:str, message:str = "Welcome") -> None:
    print("Hello {name}, the message is {message}")

def add(x:int, y:int = 1) -> int:
    total = x + y
    return x + y

message = "Hello World"
print_message(message)
print(add(5))
~~~

### Explicit global

~~~python
a = 5

def change_a(b):
    a = b
    print(a)

change_a(10)

print(a)
~~~

~~~python
a = 5

def change_a(b):
    global a
    a = b
    print(a)

change_a(10)

print(a)
~~~

## Lists

Same as in Java...

~~~java
public class ListOfNumbersDemo {
    public static void main(String[] args) {
        List<int> listOfNumbers = List.of(1,2,3,4)
        
        for(int i : listOfNumbers) {
            System.out.println(i);
        }
    }
}
~~~

... provides Python support for Lists.

~~~python
listOfNumbers = [1,2,3,4]
for i in listOfNumbers:
    print(i)
~~~

A python list initialised with square brackets and provides support for objects belonging to multilple types

~~~python
x = [1.0, 2.0, 3.0]
y = ["a", "list", "or", "strings"]
z = ["a",1, "mixed",3.0, "list"]
~~~

Or you can create your a list of lists...

~~~python
x = [[1.0, 2.0, 3.0],["a",1, "mixed",3.0, "list"]]
~~~

> Python doesn't provide direct support for arrays (unless you're using frameworks like Numpy)

### Dimension of the list

A first action we can perform is to query the size or dimension of this list.  
For that, there exists a generic (not only for lists) function len()z

~~~python
x = [1.0, 2.0, 3.0]
y = ["a", "list", "of", "strings"]
z = []
print(len(x)) # prints 3
print(len(y)) # prints 4
print(len(z)) # prints 0
~~~

### Empty list

So an empty list is also possible ...

~~~python
x = []
len(x) # prints 0
~~~

which is then just a list of length 0

### Extracting data from a list (index)

To work with such a list you must be able to extract data from it.  
To address data from a list, we work with the concept of **indexing** as like it is with Java-arrays.

By **index** we mean the **position** of the **element within** this **list**.  

~~~python
x = [1.0, 2.0, 3.0]
y = ["a", "list", "or", "strings"]
print(x[0])
print(y[1])
~~~

Same as in other languages everyting is 0-indexed

### Indexering vs range

Stel dat je toch een index adresseert > n -1 zal Python een error genereren.

Volgende code ...

~~~python
x = [1, 2, 3]
print(x[3])   # raises IndexError
~~~

... genereert een IndexError

~~~
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
~~~

### Modify data in a list (index) 

You can modify an element of a list in a similar way.  
You again use the same indexing mechanism, but apply it in an **assignment-statement**

~~~python
x = [1.0, 2.0, 3.0]
print(x[1]) # prints 2.0
x[2]=10
print(x[2]) # prints 10
~~~

### Negative indexes

In Python you can also use negative indexes, here you simply reverse the indexing....  
The idea is that you subtract from the dimension or length...

~~~python
x = [0,1,2,3,4,5,6,7,8,9]
print(x[-1]) # prints 9 => position/index 10 - 1 = 9
print(x[-3]) # prints 7 => position/index 10 - 3 = 7
~~~

### Run through lists (retry...)

Indeed, you can also use the for-loop, which we used earlier in combination with range

~~~python
x = [0,1,2,3,4,5,6,7,8,9]
for n in x:
    print(n)
~~~


### Slicing

You can also take a piece from such a list, this is called slicing.

~~~python
x = [0,1,2,3,4,5,6,7,8,9]
for n in x[2:4]:
    print(n)
# prints 2 and 3
~~~

The first index is the starting index, note the **2nd index** is **not inclusive**!!!

#### Slicing with negative indexes

You can also use negative indexes here:

~~~python
x = [0,1,2,3,4,5,6,7,8,9]
for n in x[2:-2]:
    print(n)
# print from 2 to 7
~~~

#### Slicing with default

You can also leave out the first and second part of a slice like below

~~~python
x = [0,1,2,3,4,5,6,7,8,9]
for n in x[:-2]:
    print(n)
# print from 0 to 7
~~~

In the snippet below we leave out the last part...

~~~python
x = [0,1,2,3,4,5,6,7,8,9]
for n in x[2:]:
    print(n)
# print from 2 to 9
~~~

### List-operations

You can also expand a list once created:

* append(): add element to end of list
* extend(): add the same but another list or iterable at once 
* count(): number of elements with a certain value  
* index(): index the first element for a specific value
* insert(): add element at a specific position
* pop() : remove element on an inde
* remove() : delete first item with a specified value Removes the first item with the specified value
* reverse() : inverts the order of items/elements
* sort() : sort the list

See the following sequence in the console

~~~python
>>> car_park = ["Lada", "Skoda", "Lambo"]
>>> print(car_park)
['Lada', 'Skoda', 'Lambo']
>>> print(len(car_park))
3
>>> car_park.append("Ferrari")
>>> print(car_park)
['Lada', 'Skoda', 'Lambo', 'Ferrari']
>>> car_park.remove("Lambo")
>>> print(car_park)
['Lada', 'Skoda', 'Ferrari']
>>> car_park.pop(1)
'Skoda'
>>> print(car_park)
['Lada', 'Ferrari']
>>> car_park.insert(1, "Volvo")
>>> print(car_park)
['Lada', 'Volvo', 'Ferrari']
>>> car_park.reverse()
>>> print(car_park)
['Ferrari', 'Volvo', 'Lada']
>>> car_park.sort()
>>> print(car_park)
['Ferrari', 'Lada', 'Volvo']
>>> del car_park[:]
>>> print(car_park)
[]
>>>
~~~

### Concatenating lists

Concatenating 2 lists can be performed by the +-operator 

~~~python
print([0,1,2,3,4] + [5,6,7])
~~~

## Working with dictionaries

### Dictionaries => key and value

In the case of a list use the index as **key** to retrieve an element....  
For example, in case of students, it would be more natural to use the students' names to perform this mapping (then you don't have to remember the ids).  

There are **dictionaries** (equivalent in Java is Map) for this purpose.  
These are - like lists - **data structures** to which you can add **multiple objects or items**.  

The difference, however, is that each **value** you add must be accompanied by a **key**.  
You then use this afterwards to retrieve these values as demonstrated in the code below:

~~~python
student_points = {
  “John": 12,
  “Pete": 15,
  “Joris": 16,
  “Korneel": 18
}

print(student_points[“Jan”]) #prints 12
print(student_points)
~~~

The dictionary above (student_points) maps the students' names to points, we speak here of **keys** (or keys) vs. the **values** or values.

Upon execution of the code you see:

* You can retrieve the **value** **from an entry by placing the **key** **between** **square brackets**
* The following ouput prints the entire contents of the dictionarry

Both keys and values can be any type, there is **no restriction of type**.  
In this case we have used strings as keys but this can also be an integer or even an object.

### Keys are unique

What is important is that there **cannot be 2 different entries** with the same **key** **within** a **dictionary**.  
The code below demonstrates this:

~~~python
student_points = {
  “John": 12,
  “Pete": 15,
  “Joris": 16,
  “Korneel":18,
  “Jan":14
}

print(student_points[“Jan”]) # prints 14
print(student_points)
~~~

Jan is defined 2 times as a key here.  
The **last** value (14) will **override** the **first** value (12).

### Add value to a dictionary

You can also **add** a student to this **dictionary**, for example, below we add a student with the key (name) “Bart”

~~~python
student_points = {
  “John": 12,
  “Piet": 15,
  “Joris": 16,
  “Korneel": 18
}

print(student_points[“Jan”])
print(student_points)

student_points[“Bart”] = 12
print(student_points[“Bart”])
print(student_points)
~~~

Resulting in an additional student_points being **added**.

### Update value within a dictionary

You can **add** as well as **update** the same value.

~~~python
student_points = {
  “John": 12,
  “Pete": 15,
  “Joris": 16,
  “Korneel": 18
}

print(student_points[“Pete”])
student_points[“Pete”] = 16
print(student_points[“Pete”])
~~~

Here the **previous value** is going to be **overwritten** automatically....

~~~bash
$ python3 dictionary_demo.py
15
16
~~~

### Delete value from a dictionary

Besides **add** and **change**, you can also **delete** such a key/value pair.  
For this, the **keyword** **del** exists in Python.

Suppose we want to delete a student below, this can be done as follows:

~~~python
student_points = {
  “John": 12,
  “Pete": 15,
  “Joris": 16,
  “Korneel": 18
}
print ("Before: ”, student_points)
del student_points[“Pete”]
print ("After: ”, student_points)
~~~

After deleting the entry with the key Pete it disappears from the dictionary

~~~bash
$ python3 dictionary_demo.py
Before: {'Jan': 12, 'Piet': 15, 'Joris': 16, 'Korneel': 18}
After: {'Jan': 12, 'Joris': 16, 'Korneel': 18}
~~~

### What if the key doesn't exist?

We have now seen how to delete an entry....  
What if you retrieve a value with a **non-existent key** like the one below?

~~~python
student_points = {
  “John": 12,
  “Pete": 15,
  “Joris": 16,
  “Korneel": 18
}

print(student_points[“Hans”])
~~~

As you can see in the trace, an error will be raised in this case.  

~~~bash
$python3 dicationary_demo.py
Traceback (most recent call last):
  File “dicationary_demo.py”, line 8, in <module>
    print(student_points[“Hans”])
KeyError: 'Hans'
~~~

Python dictionaries require you to pass correct keys, if you don't do this it will return an error.  
How can you avoid this?

### Check if an entry exists within the dictionary

To avoid such situations you have 2 options.  
Either you catch this error via a **try-except construct**

~~~python
student_points = {
  “John": 12,
  “Pete": 15,
  “Joris": 16,
  “Korneel": 18
}

search_key = “Hans”

try:
    print(student_points[“Hans”])
except KeyError:
    print(search_key + “ does not exist”)
~~~

...resulting in...

~~~bash
$ python3 dicationary_demo.py
Hans does not exist
~~~

Either **avoid** this **error** by using the **in operator**

~~~python
student_points = {
  “John": 12,
  “Pete": 15,
  “Joris": 16,
  “Korneel": 18
}

search_key = “Hans”

If search_key in student_points:
    print(student_points[“Hans”])
else:
    print(search_key + “ does not exist”)
~~~

...with the same result...

~~~bash
$python3 dictionary_demo.py
Hans does not exist
~~~

Which one should you use now?  
The **in operator** in this case is the **preferred solution**, it is clearer here what the intent is in the program.  

This is a general rule in working with exceptions by the way, you are **really** trying to **prevent** rather than **heal**.
You try to avoid using exceptions if there is a way to check this in advance.  

Exceptions should only be used if you have no way to handle an “exeptional situation” (also have exceptions in some cases ).

## Set

~~~python
a = {1, 2, 3, 4, 5}
b = {4, 5, 6, 7, 8}

print("a | b =", a | b)  # union
print("a & b =", a & b)  # intersection
print("a - b =", a - b)  # difference

# > a | b = {1, 2, 3, 4, 5, 6, 7, 8}
# > a & b = {4, 5}
# > a - b = {1, 2, 3}
~~~

## Tuples

Tuples in Python are the **equvalent** of an **immutable List** .

In Java an immutable list is actually a list with the same operations.  
Basically it will throw an java.lang.UnsupportedOperationException in case you try to modify it...

~~~java
import java.util.Collections;
import java.util.List;

public class Hello {

 public static void main(String[] args) {
        List<String> immutableList = List.of("hello", "world") 
        // or Collections.unmodifiableList(List.of("hello", "world")); if you want to be sure
        System.out.println(immutableList.get(0));
        System.out.println(immutableList.get(1));
    }
}
~~~

In Python this is different type, you initialize this by using () in stead of []

~~~python
a_tuple = ("hello", "world")
print(a_tuple[0])
print(a_tuple[1])
~~~

As a list a tuple keeps its original ordering and can contain multiple datatypes.  


### Collection destructuring/unpacking

Like in other programming languages you can assign more then one variable at a time on a single line in Python

~~~python
first, last = "hello", "world"
~~~

This can be also used to unpac tuples (and other collections)

~~~python
first, last = ("hello", "world")
print(first)
print(last)
~~~

### Destructuring in for loops with enumerate

A nice sample of destructuring is enumerate.  
This function takes an iterable collection as an argument and returns 
an enumerate object containing a tuple for each item in the collection.  

Each tuple contains a counter value, which increments with each iteration, 
along with a value from the provided collection.

~~~python
punten = [15,16,8,9]

for i, punt in enumerate(punten):
  print(f'student {i} heeft {punt} punten')
~~~

~~~
student 1 heeft 15 punten
student 2 heeft 16 punten
student 3 heeft 8 punten
student 4 heeft 9 punten
~~~

### Named tuple

~~~python
from collections import namedtuple

Student = namedtuple('Student', ['name', 'age', 'DOB'])
a_student = Student('Bart', '49', '2541997')

print(f"The Student age using index is {a_student[1]}: ")
print(f"The Student name using keyname is {a_student.name}: ")
~~~

## Objects and classes

So far - collections aside - we have **only worked** with  **simple** data **types** that can hold a single value such as int, float, boolean, ... among others.

> Note: String was an exception to this considering that is actually a list of characters....

In this section we look at classes in python, which allow us to structure data in 1 data type

### Simple case: student application

Suppose you want to build an an application that wants to track grades for a course, as in the table representation below.


| id| Name    | First name | Lab    | Theory    |
|---|---------|------------|--------|-----------|
| 1 | Jan     | Janssens   | 15     |        16 |
| 2 | Piet    | Pieters    |   15   |    16     | 
| 3 | Joris | Jorissen | 15 | 16 |
| 4 | Korneel | Kastaar | 15 | 16 |


### Structured programming with classes

In Python, just like in Java you can do this like in Java with classes.  

### Class of student

Let's plug right in with our previous example to extend.  
Applied to a student such a data type looks like this, you start each time with:

* The keyword **class**
* Followed by a **name** for this type
  (Student in this case)
* Followed by a block-indicator **:**

~~~python
class Student:
    name = ""
    lab_points = 0
    theory_points = 0
~~~

Below the class-definition the 3 attributes are listed

* name
* lab_points
* theory_points

### Creating an object

When you create a variable of such type we call it an **object** as is shown in the snippet below
Instantiates an object of the Student-type

~~~python
class Student:
    name = ""
    lab_points = 0
    theory_points = 0

jan = Student()
~~~

An **object** is created by a special function (Student()) called the **constructor**. 

~~~python
class Student:
    name = ""
    lab_points = 0
    theory_points = 0

jan = Student()
jan.name = "Jan Janssens"
jan.lab_points = 15
Jan.theory_points = 17

print(jan.lab_points) # prints Jan Janssens
print(jan.lab_points) # prints 15
print(jan.theory_points) # prints 17
~~~

The attributes can be set of retrieved similar to Java through the dot-operator.

### Constructor - spot the difference

Same as in Java, Python use constructor in order to initialize the object (and it's state).  
The difference - in syntax - is that the new keyword as it is used in Java...

~~~Java
jan = new Student()
~~~

...is not used in Python...

~~~python
jan = Student()
~~~

This **constructor**:

* is a **function**
* that is **automatically** created**  
  (if you don't create it yourself, see directly)
* with **the same name** as the **class**
* which you **call** to create an **object** (or instance) of the class

In a moment we're also going to see that this constructor can be modified, but first let's do something with the object.

### Constructor with arguments

You can extend the constructor function with arguments and can use these arguments 
to initialize the attributes of the objects.

~~~python
class Student:
    def __init__(self,name,lab,theory):
        self.name = name
        self.lab_points = lab
        self.theory_points = theory

students = []

students.append(Student("Jan Janssens",15,17))
students.append(Student("Piet Pieters",15,17))

for student in students:
    print(student.name + ":")
    print(student.lab_points)
    print(student.theory_points) 
~~~

Also note that it is no longer necessary to define the attributes, it is sufficient to associate them with self.  
**self** is an alias/reference to the current instance of this class (Student) and is always required as the 1st argument to any **object method**.


### Constructor with default arguments

We can also assign default arguments to this....

~~~python
class Student:
    def __init__(self,name,lab=0,theory=0):
        self.name = name
        self.lab_points = lab
        self.theory_points = theory

students = []

students.append(Student("Jan Janssens",15,17))
students.append(Student("Piet Pieters",15,17))
students.append(Student("Student without theori",15))

for student in students:
    print(student.name + ":")
    print(student.lab_points)
    print(student.theory_points) 
~~~

### Classes and methods

In addition to attributes, you can also add functions to classes called methods.  
These are functions that are associated with an instance of an object; the constructor was a first special example.  

In the example below, we add a method that calculates the points of students (based on it's attributes).

~~~python
class Student:
    def __init__(self,name,lab=0,theory=0):
        self.name = name
        self.lab_points = lab
        self.theory_points = theory

    def points(self):
        return (self.lab_points + self.theory_points)/2

students = []

students.append(Student("Jan Janssens",15,17))
students.append(Student("Piet Pieters",15,17))

for student in students:
    print(student.name + ":")
    print(student.lab_points)
    print(student.theory_points) 
    print(student.points())
~~~

### __str__

Another special method (earlier we had already seen the constructor) is the string method.  
If you add the method __str__ it will be called automatically when you want to convert a to a string:

* By using the str() operator.
* By passing the object to the print function (which in turn calls str())

~~~python
class Student:
    def __init__(self,name,lab=0,theory=0):
        self.name = name
        self.lab_points = lab
        self.theory_points = 0

    def points(self):
        return (self.lab_points + self.theory_points)/2

    def succeeded(self):
        return points(self) >= 10    
        
    def __str__(self):
        return "Student {} has {} for lab and {} for theory, so average of {}".format(
            self.name, self.lab_points,self.theory_points,self.points())

students = []

students.append(Student("Jan Janssens",15,17))
students.append(Student("Piet Pieters",15,17))

for student in students:
    print(student)
    # or alternatively print(str(student))
~~~

Returns following result:

~~~
Student Jan Janssens has 15 for lab and 0 for theory, so average of 7
Student Piet Pieters has 15 for lab and 0 for theory, so average of 7
~~~

### __eq__

The equivalent in Python to the equal-method is called __eq__

~~~python
class Student:
    def __init__(self,name,lab=0,theory=0):
        self.name = name
        self.lab_points = lab
        self.theory_points = 0

    def points(self):
        return (self.lab_points + self.theory_points)/2

    def succeeded(self):
        return points(self) >= 10    
        
    def __str__(self):
        return "Student {} has {} for lab and {} for theory, so average of {}".format(
            self.name, self.lab_points,self.theory_points,self.points())

    def __eq__(self,other):
        return other.name == self.name

    
x = Student("Jan Janssens",15,17)
y = Student("Jan Janssens",10,11)
z = Student("Dan Danssens",10,11)

print(x==y)
print(x==z)
~~~

## Exceptions and error-handling

### Python uses exceptions

As in Java, Python uses exceptions to stop execution if specific conditions are met or not met
like the 0-division below.. 

~~~python
print("Hello")
a = 0/0
print(a)
~~~

...causing the following error...

~~~
Hello
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ZeroDivisionError: integer division or modulo by zero
~~~

In this case, we see that an **error** is also clearly indicated, in this case a **ZeroDivisionError**.  

### An exception stops the program

Do note that the **code** that comes **before the error** (a = 0/0) does **execute** (print("Hello")).

The program does **start** but stops** at the **indicated point of error**.

Unlike a syntax error, a python program cannot determine when parsing Python code that there is honor error.

### Exceptions and functions

There is also no difference if you generate this **error** within a function, this **error** is **propagated** as long as it is not caught.

~~~python
def divide(a,b):
  return a/b

print("Hello")
a = divide(0,0)
print(a)
~~~

resulting in

~~~
Hello
Traceback (most recent call last):
  File "tmp.py", line 5, in <module>
    a = divide(0,0)
  File "tmp.py", line 2, in divide
    return a/b
ZeroDivisionError: division by zero
~~~

### Catch exceptions

You can make sure in your code that these **exceptions** are **caught** without terminating the program.

This can be done via a **try-block** in combination with **except-block**  
In the code below, we are trying to print a variable that does not exist.  

~~~python
print("Before try-catch")
try:
  print(x)
  print("After error")
except:
  print("An exception occurred")
print("After try-catch")
~~~

We can do this using a default **except-block**, this is going to catch any error (other than SyntaxError).

This results in the following execution...

~~~
Before try-catch
An exception occured
After try-catch
~~~

We see here that:

* The **program** is **executed**
* The **try-block** is **interrupted** (at print(x))
* The **except** is **executed**
* The **code continues** running **after** the **except**

### Catch Exceptions by Type

You can also specify the **type of exception** you want to catch.  
In this case you limit the trapping to a specific error, the NameError

~~~python
print("Before try-catch")
try:
  print(x)
  print("After error")
except NameError:
  print("An exception occurred")
print("After try-catch")
~~~

It suffices here to define the type after the except keyword.

However, if you generate another error (for example, a ZeroDivisionError)...

~~~python
print("Before try-catch")
try:
  print(0/0)
  print(x)
  print("After error")
except NameError:
  print("An exception occurred")
print("After try-catch")
~~~

...However, this will not be caught...

~~~
ZeroDivisionError: integer division or modulo by zero
~~~

...and the program is terminated (prints thereafter are not printed)

### Multiple except blocks

To fix this problem - and accommodate multiple exceptions - you can place multiple except-blocks.  
By placing the following except-block on ZeroDivisionError you avoid terminating the program.

~~~python
print("Before try-catch")
try:
  print(0/0)
  print(x)
  print("After error")
except NameError:
  print("A NameError-exception occurred")
except ZeroDivisionError:
  print("A ZeroDivision-exception occurred")
print("After try-catch")
~~~

You can also add the the **default** except-block to this

~~~python
print("Before try-catch")
try:
  print(0/0)
  print(x)
  print("After error")
except  NameError:
  print("A NameError-exception occurred")
except  ZeroDivisionError:
  print("A ZeroDivision-exception occurred")
except:
  print("Another error")
print("After try-catch")
~~~

In that case, all error will be caught (but the message will be different in case of NameError or ZeroDivisionError)

### finally

As in Java, Python supports the finally-blocks allowing you to clean up

~~~python
try:
  print(0/0)
except:
  print("Something went wrong when writing to the file")
finally:
  print("Some cleaning")
~~~

In the case below the execution will fail (because of lacking the write-modus)

~~~python
try:
  f = open("demofile.txt")
  f.write("Lorum Ipsum")
except:
  print("Something went wrong when writing to the file")
finally:
  f.close() 
~~~

Take however into account that it's preferrable to use the with-statement

~~~python
try:
    with open("demofile.txt", "r") as f:
        f.write("Lorum Ipsum")
except:
  print("Something went wrong when writing to the file")
~~~

> Make sure in not putting the try-except inside the with-statement, otherwise the
> file will not close...

### else (vs finally)

Something that doesn't exist in Java is an else-block that can be added to a try-block.  
**else** is the **counter-part** of **expect** in that it will only execute it's code **only** 
when no excpetion occurs from the try-block

~~~python
try:
  print(0/0)
except:
  print("Something went wrong when writing to the file")
else:
  print("Only when no exeptions")
finally:
  print("Always")
~~~

This is **different** from **finally** as finally will always execute...

### Raise exceptions yourself

In addition to catching exceptions, you can also raise them yourself with the keyword **raise**.

Practically, suppose you create a function:

* That calculates the area of a circle.
* However, you do not want negative input

~~~python
import math

def circumference(radius): 
  if radius < 0:
    raise Exception("Sorry, no numbers below zero")
  return 2 * radius * math.pi

circumference(1) # prints +- 6,283...
circumference(-1) # raises error
~~~

The function call on the last line will crash and terminate the program.

~~~
6.283185307179586
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>.
  File "<stdin>", line 3, in circumference
Exception: Sorry, no numbers below zero
~~~

### Create your own (custom) exceptions

~~~python
import math

class RadiusException(Exception):
  pass

def circumference(radius): 
  if radius < 0:
    raise RadiusException()
  return 2 * radius * math.pi

circumference(1) # prints +- 6,283...
circumference(-1) # raises error
~~~

### And catch...

You can then catch this exception by type as we have seen before.

~~~python
import math

class RadiusException(Exception):
  pass

def circumference(radius): 
  if radius < 0:
    raise RadiusException()
  return 2 * radius * math.pi

try:
  circumference(1) # prints +- 6,283...
  circumference(-1) # raises error
except RadiusException:
  print("Problem with radius...")
~~~

Then suppose you would still raise another exception....

~~~python
import math

class RadiusException(Exception):
  pass

def circumference(radius): 
  if radius < 0:
    raise RadiusException()
  return 2 * radius * math.pi

try:
  a = 5/0
  circumference(1)  # prints +- 6,283...
  circumference(-1) # raises error
except RadiusException:
  print("Problem with radius...")
~~~

... this will not be catches ...

## Functional programming

Python supports the functional paradigm for a very long time (long time before Java).  
In this part we make a (quick) comparison with the Streams-functionality by revisiting some examples of:

* Streams.map
* Streams.filter
* Streams.reduce

to it's Python counterparts

### lambda-functions in Python

Let's start with lambda-functions in Java lambda's are defined and called 
as functional interfaces as shown below:

~~~java
import java.util.function.Function;

public class SampleFunction {

    public static void main(String[] args) {
        System.out.println(execute((n) -> n * 10, 5));
    }

    public static int execute(Function<Integer, Integer> function, int number) {
        return function.apply(number);
    }
}

~~~

In Python the same concept is applied

~~~python
def execute(a_function, number):
    return a_function(number)

print(execute(lambda x: x * 10, 5 ))
~~~

Basically you:

* Start with the lambda-keyword
* Followed by one or more arguments
* Followed by an expression


### Function reference

A lambda is anomynous function, in case an existing function already
provides for you can use a function-reference like below:

~~~java
import java.util.function.Function;

public class Hello {

    public static void main(String[] args) {
        System.out.println(execute(Hello::aFunction, 5));
    }

    public static int aFunction(int x) {
        return x * 10;
    }

    public static int execute(Function<Integer, Integer> function, int number) {
        return function.apply(number);
    }
}
~~~

In Python you just pass in the name of the function

~~~python
def execute(a_function, number):
    return a_function(number)

def a_function(x):
    return x * 10

print(execute(a_function, 5 ))
~~~

In case of a method you just pass on the member of the object:

~~~python
def execute(a_function, number):
    return a_function(number)

class Test:
    def aFunction(self, x):
        return x * 10

t = Test()

print(execute(t.aFunction, 5 ))
~~~


### Streams.map vs map

First one is map, allowing you transform a stream in another stream presenting other values (and even types).  
Let's start with a simple example that transforms an IntStream to it's multiplication by 2.

~~~Java
import java.util.stream.IntStream;

public class Hello {

 public static void main(String[] args) {
        IntStream numbers = IntStream.of(1,2,3,4,5,6,7,8,9);
        numbers.map((i) -> i * 2).forEach(System.out::println);
    }
}
~~~

In Python you don't need to convert to a Stream, but you call
directly upon the first class map()-operations

~~~python
l = [1,2,3,4,5,6,7,8]
for i in (map(lambda x: x * 2, l)):
    print(i)
~~~

As in Java map accepts a function (anomynous or reference)


### Stream to List

In Java you can collect or invoke directly toList() to collect the
result of a stream to a list.

~~~java
import java.util.List;
import java.util.stream.IntStream;

public class Hello {

 public static void main(String[] args) {
        IntStream numbers = IntStream.of(1,2,3,4,5,6,7,8,9);
        List<Integer> list = numbers.map((i) -> i * 2).boxed().toList();
        System.out.println(list);
    }
}
~~~

In Python this is supported a simple cast as shown below

~~~python
l = [1,2,3,4,5,6,7,8]
print(list(map(lambda x: x * 2, l)))
~~~


### Filtering

The next operation we use is filter.  
We extend the previous example with a filtering to a stream of numbers bigger than 4.


~~~java
import java.util.stream.IntStream;

public class Hello {

 public static void main(String[] args) {
        IntStream numbers = IntStream.of(1,2,3,4,5,6,7,8,9);
        numbers.filter((i) -> i > 4)
                .map((i) -> i * 2)
                .forEach(System.out::println);
    }
}
~~~

In Python this is done by wrapping the result of the filter as an argument of map

~~~python
l = [1,2,3,4,5,6,7,8,9]
for i in (map(lambda x: x * 2, filter(lambda x: x > 4, l))):
    print(i)
~~~

### Ranges

For convenience we swich to an range for this

~~~java
import java.util.stream.IntStream;

public class Hello {

 public static void main(String[] args) {
        IntStream.rangeClosed(1, 9).filter((i) -> i > 4)
                .map((i) -> i * 2)
                .forEach(System.out::println);
    }
}
~~~

Pay attention, a range in Python is non-closed

~~~python
for i in (filter(lambda x: x > 4, map(lambda x: x * 2, range(1,9 + 1)))):
    print(i)
~~~

### Reduce

Another key-concept of Streams is reduce, this allow you to collect or gather aggregates on streams.  
So imagine you want the total of the previous filter/map-combination you can can add a reduce-function.

~~~java
import java.util.stream.IntStream;

public class Hello {

 public static void main(String[] args) {
        System.out.println(
            IntStream.rangeClosed(1, 9).filter((i) -> i > 4)
                .map((i) -> i * 2)
                .reduce((a,b) -> a + b)
                .orElse(0));
    }
}
~~~

In Python the same function does exists with the same semantics as shown below

~~~python
from functools import reduce

print(reduce(lambda x,y: x + y,
             filter(lambda x: x > 4, 
                    map(lambda x: x * 2, range(1,9 + 1)))))
~~~

### reduce on empty streams (without initial value)

One of the the nice things in the Java-version is that it make use of **Optional** to indicate
the precense of data in the stream on which the reduce is applied.

~~~java
import java.util.stream.IntStream;

public class Hello {

 public static void main(String[] args) {
        System.out.println(
            IntStream.of().filter((i) -> i > 4)
                .map((i) -> i * 2)
                .reduce((a,b) -> a + b)
                .orElse(0));
    }
}
~~~

Python's reduce doesn't offer this feature so in case you pass an empty collection
an error will be spawn.

~~~python
from functools import reduce

print(reduce(lambda x,y: x + y,
             filter(lambda x: x > 4, 
                    map(lambda x: x * 2, []))))
~~~

...as it's shown below

~~~
Traceback (most recent call last):
  File "/home/bart/Projects/python-for-java/test.py", line 3, in <module>
    print(reduce(lambda x,y: x + y,
TypeError: reduce() of empty iterable with no initial value
~~~

> Python has a (less powerfull) **equivalent** of Java's Optional called **union**

### reduce on empty streams (with initial value)

However for Python there is the possibility of passing in an start-value.  
In this case, this initial value will be returned in case of an empty collection
(in stead of the error).

~~~python
from functools import reduce

print(reduce(lambda x,y: x + y,
             filter(lambda x: x > 4, 
                    map(lambda x: x * 2, [])), 0))
~~~

By the way, Java **supports** the **same** **feature** and will not return an **Optional**
in case an **initial** value is passed along to reduce.

~~~java
import java.util.stream.IntStream;

public class Hello {

 public static void main(String[] args) {
        System.out.println(
            IntStream.of().filter((i) -> i > 4)
                .map((i) -> i * 2)
                .reduce(0, (a,b) -> a + b));
    }
}
~~~

### List comprehensions

~~~python
l = [1,2,3,4,5,6,7,8]
print([x for x in l if x > 4 ])
~~~

~~~python
data = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
column = [row[1] for row in data]
print(column) # output: [2, 5, 8]
~~~ 



~~~python
data = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
column = [row[1] for row in data]
print(column) # output: [2, 5, 8]
~~~



~~~python
print(sum(filter(lambda x: x > 4, map(lambda x: x * 2, l))))
~~~

~~~python
list(
     map(
         lambda a, b, c: a + b + c,
         [1, 2, 3, 4],
         [10, 20, 30, 40],
         [100, 200, 300, 400],
     )
)
~~~
