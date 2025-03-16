# From Python to Java

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
        String baseString = "Hello %s! This course takes about %,d minutes.";
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


Same as in Java they compare 2 numbers and do return a boolean as result

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

In Java there's is a shorthand for if-else you can use for retrieving values called
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

The counterpart in Python is a conditional expression as shown below.

~~~python
i = 5
result = "positive" if i > 0 else "negative"
print(result)
~~~


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

### Reading and writing

~~~python
filename = "test.txt"

write_file = open(filename, "w+")
write_file.write("Hello\n")
write_file.write("File!\n")
write_file.close()

read_file = open(filename, "r")
for line in read_file.read().splitlines():
    print(line)
~~~

~~~python
filename = "test.txt"

with open(filename, "w+") as write_file:
  write_file.write("Hello\n")
  write_file.write("File!\n")

with open(filename, "r") as read_file:
  for line in read_file.read().splitlines():
      print(line)
~~~

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

## Collection


### List

~~~python
listOfNumbers = [1,2,3,4]
for i in listOfNumbers:
    print(i)
~~~

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

### Slicing

~~~python
l = [0,1,2,3,4]
print(l[1:])
print(l[1:3])
print(l[:3])
print(l[1:-1])
print(l[:-1])
~~~

### Concatenating lists

~~~python
print([0,1,2,3,4] + [5,6,7])
~~~

### Collection destructuring/unpacking

~~~python
a, b = 5, 8
print(a)
print(b)
~~~

### Enumerate

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

### Tuple

### Set

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

### Dictionary

In Java you have the Map-datatype with a couple of implementations you can choose from dependent on performance-characteristics.

~~~python
grades = {
    "Jan": 15,
    "Piet": 16,
    "Joris": 8,
    "Korneel": 9
}

grades = dict(Jan: 15, Piet: 16, Joris: 8, Korneel: 9)


grades["Jan"]
grades["Piet"] = 5 
grades["Joris"] = 4

# remove an element (will raise an error if the key does not exist)
if "math" in grades:
    del grades["math"]

grades.keys()              # get all the keys as a list
grades.values()            # get all the values as a list
~~~


### Named tuple

~~~python
from collections import namedtuple

Student = namedtuple('Student', ['name', 'age', 'DOB'])
a_student = Student('Bart', '49', '2541997')

print(f"The Student age using index is {a_student[1]}: ")
print(f"The Student name using keyname is {a_student.name}: ")
~~~

## Classes and OOP



~~~python
class Student:
    def __init__(self,name,lab=0,theory=0):
        self.name = name
        self.lab_points = lab
        self.theory_points = theory

    def points(self):
        return (self.lab_points + self.theory_points)/2

    def succeeded(self):
        return self.points(self) >= 10    
        
    def __str__(self):
        return f"Student {self.name} has {self.lab_points} for lab and {self.theory_points} for theory, so average of {self.points()}"

students = []

students.append(Student("Jan Janssens",15,17))
students.append(Student("Piet Pieters",15,17))

for student in students:
    print(student)
~~~

~~~python
import datetime

class Person:
    def __init__(self, name, birthYear):
        self.name = name
        self.birthYear = birthYear
        
    def age(self):
        return datetime.date.today().year - self.birthYear

class Student(Person):
    def __init__(self,name, birthYear, lab=0,theory=0):
        super().__init__(name, birthYear)
        self.lab_points = lab
        self.theory_points = theory

    def points(self):
        return (self.lab_points + self.theory_points)/2

    def succeeded(self):
        return self.points(self) >= 10    
        
    def __str__(self):
        return f"Student {self.name} with age {self.age()} has {self.lab_points} for lab and {self.theory_points} for theory, so average of {self.points()}"

students = []

students.append(Student("Jan Janssens", 1974, 15,17))
students.append(Student("Piet Pieters", 2004, 15,17))

for student in students:
    print(student)
~~~

## Exceptions

~~~python
print("Hello")
a = 0/0
print(a)
~~~

...causes the following error...

~~~
Hello
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ZeroDivisionError: integer division or modulo by zero
~~~


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
else:
    print("No problem")
finally:
  print("Some cleaning") 

print("After try-catch")
~~~

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
else:
    print("No problem")
finally:
  print("Some cleaning") 
~~~


~~~python
import math

def circumference(radius): 
  if radius < 0:
    raise Exception("Sorry, no numbers below zero")
  return 2 * radius * math.pi

circumference(1)  # prints +- 6,283...
circumference(-1) # raises error
~~~

## Objects and classes

So far - collections aside - we have **only worked** with  **simple** data **types** that can hold a single value such as int, float, boolean, ... among others.

> Note: String was an exception to this considering that is actually a list of characters....

In this section we look at classes in python, which allow us to structure data in 1 data type

### Simple case: student application

Suppose you want to build an an application that wants to track grades for a course, as in the table representation below.

~~~
+---+---------+------------+--------+-----------+
| id| Name    | First name | Lab    | Theory    |
+---+---------+------------+--------+-----------+
| 1 | Jan | Janssens | 15           |        16 |
+---+---------+------------+--------+-----------+
| 2 | Pieters | 15 | 16 |
+---+---------+------------+--------+-----------+
| 3 | Joris | 15 | 16 |
+---+---------+------------+--------+-----------+
| 3 | Korneel | 15 | 16 |
+---+---------+------------+--------+-----------+
~~~


### Structured programming with classes

In Python, you can do this like in Java with classes.  

A class is a **structured data type** that allows you to **group** different values (or subvariables) under a single **object**.  

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

Then you can have this followed by 1 or more **attributes** in this case this is:

* name
* lab_points
* theory_points

These attributes are **sub-variables** that are **connected** to an instance of a **class**.

> Note: later we will see that - besides attributes - we can also attach functions to a class type

### Creating an object

When you create a variable of such type we call it an **object**.  
The code below:

* Defines such a type
* Instantiates an object of this type

~~~python
class Student:
    name = ""
    lab_points = 0
    theory_points = 0

jan = Student()
~~~

An **object** is created by a special function (Student()) called the **constructor**. 

### Constructor

This **constructor**:

* is a **function**
* that is **automatically** created**  
  (if you don't create it yourself, see directly)
* with **the same name** as the **class**
* which you **call** to create an **object** (or instance) of the class

In a moment we're also going to see that this constructor can be modified, but first let's do something with the object.

### Working with attributes

An object consists of attributes (name, lab_points, theory_points), as they were described in the class.  
The example below illustrates how to use these attributes.

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

You can read and edit these variables via dot notation - object name followed by dot followed by name - just as you would with a regular variable.

### Multiple objects

Of course, you can then add multiple objects

~~~python
class Student:
    name = ""
    lab_points = 0
    theory_points = 0

jan = Student()
jan.name = "Jan Janssens"
jan.lab_points = 15
jan.theory_points = 17

piet = Student()
piet.name = "Piet Pieters"
piet.lab_points = 15
piet.theory_points = 17

print(jan.lab_points)
print(jan.lab_points)
print(jan.theory_points)

print(piet.lab_points)
print(piet.lab_points)
print(piet.theory_points)
~~~

In this example, you can clearly see that the attributes are associated with the object.  
jan.lab_points is not the same as piet.lab_points

### Multiple objects in a list

Let's combine the principle of classes with lists.   
This allows you to keep a dynamic collection of students.

~~~python
class Student:
    name = ""
    lab_points = 0
    theory_points = 0

students = []

jan = Student()
jan.name = "Jan Janssens"
jan.lab_points = 15
Jan.theory_points = 17
students.append(jan)


piet = Student()
piet.name = "Piet Pieters"
piet.lab_points = 15
piet.theory_points = 17
students.append(piet)

for student in students:
    print(student.lab_points)
    print(student.theory_points) 
~~~

### Constructor with arguments

You can extend the constructor function with arguments.  
You can use these arguments to initialize the attributes

~~~python
class Student:
    def __init__(self, name, lab, theory):
        self.name = name
        self.lab_points = lab
        self.theory_points = theory

students = []

jan = Student("Jan Janssens",15,17)
students.append(jan)
piet = Student("Piet Pieters",15,17)
students.append(pieters)

for student in students:
    print(student.name + ":")
    print(student.lab_points)
    print(student.theory_points) 
~~~

Also note that it is no longer necessary to define the attributes, it is sufficient to associate them with self.  
**self** is an alias/reference to the current instance of this class (Student) and is always required as the 1st argument to any **object method**.

### Constructor (2)

Since you keep a list, it is no longer necessary to keep separate variables.  
You can directly add student objects/instances to the list via the constructor.

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

### Constructor (3)

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
    print(student.theory_points) ) 
~~~

### Classes and Methods

In addition to attributes, you can also add methods.  
These are functions that are associated with an instance of an object; the constructor was a first special example.  

In the example below, we add a method that calculates the final points of students.

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


## Functional programming

~~~python
l = [1,2,3,4,5,6,7,8]
print(list(map(lambda x: x * 2, l)))
~~~

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
l = [1,2,3,4,5,6,7,8]
print(list(filter(lambda x: x > 4, map(lambda x: x * 2, l))))
~~~

~~~python
data = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
column = [row[1] for row in data]
print(column) # output: [2, 5, 8]
~~~

~~~python
from functools import reduce

reduce(lambda x,y: x + y,filter(lambda x: x > 4, map(lambda x: x * 2, l)))
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

