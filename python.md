# Python samples

https://github.com/blu3r4y/python-for-java-developers?tab=readme-ov-file

https://realpython.com/java-vs-python/

https://raygun.com/blog/java-vs-python/

https://python.pages.doc.ic.ac.uk/java/lessons/java/01-intro/03-example.html

https://www.javatpoint.com/basic-python-for-java-developers

https://stackoverflow.com/questions/63667488/is-there-assignment-expression-for-java-like-walrus-operator-in-python

vs walrus operator


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

Obviously Python is a scripting language, you can run the code in place without intermediate build phases

Just like other scripting language you just write the script and feed it directly to the interpreter.

#### Python is a hybrid language

You can **run** command line-programming without defining a class without defining a main-function (like in other languages like Java, C, C++, ...).  

Python - as you will see later - has quite good support for both OOP and FOP but scales perfectly to basic procedural scripting-style.

Also you don't need to use an class-system to use a simple print-function.  
The print-function is a first class member and directly accessible (without static import)

#### Buy buy semicolon";"

No semicolons are required.  
Simple statements can be distinguished from each other by new lines

~~~python
print("Hello, World!")
print("Greetings from Python")
~~~

#### Similarities in java

The syntax in calling functions is similar to how you invoke them in java Java.

## Comments

In java we distinguish 2 types of comments (beside Javadoc):

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

In Python one-line-comments are marked as indicated below

~~~python
# One line comment
message = "Hello World"
print("hello world")
'''
Multiline comments
over here
'''
~~~

## Variables and dynamic typing

A big difference between Java and Python is the way on how variables are defined and used.

### Variables in Python vs Java

Let's start with storing our message in a variable

~~~java
class Hello {
    public static void main(String[] args) {
        String message = "Hello, World!";
        System.out.println(message); 
    }
}
~~~

In Python you can **define** a **variable** just as in Java but you
**don't need** to **declare** a **type** neither do you need to use a var-keyword (in the case of type inference)

~~~python
message = "Hello World"
print(message)
~~~

## Handles are dynamicly typed

You might think the type of the handle is inferred like it
is with the var-keyword but that's not really the case

~~~java
class HelloWorld {
    public static void main(String[] args) {
        var message = "Hello, World!";
        System.out.println(message); 
    }
}
~~~

In **Java** a **handle** is actually **containing** some type-information on the heap-object it's referring (e.g.g interface or class that the actual heap-object is implementing) in 
Python this is just a simple label (name) and a pointer to the object

~~~python
message = "Hello World"
print(message)
message = 1 + 3
print(message)
~~~

## Primitive datatypes

Python has a relative simple type-system compared to Java.
The 5 primitive data structures are:

* Integers
* Floats
* Strings
* Booleans 

### type-operator

Python has a built-in function (actually an operator) allowing 
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

If you run this you would see

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
To increment x by 1 you have to write 

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
class Hello {
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

#### Format string (f-strings)

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

## Input and output

~~~python
name = input("Give name please")
print(type(name))
print(f"Hello {name}")
~~~

~~~python
print("Give name please", end="")
name = input()
print(type(name))
print(f"Hello {name}")
~~~

### Reading and writing

~~~python
filename = "m06_file_io.txt"

with open(filename, "w+") as f:
    f.write("Hello\n")
    f.write("File!\n")

with open(filename, "r") as f:
    for line in f.read().splitlines():
        print(line)
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


~~~java
public class Hello {
    public static void main(String[] args) {
        int i = 5;
        String result = i > 0 ? "positive" : "negative";
        System.out.println(result);
    }
}
~~~

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





## Function

Let's start with a simple static function.

> We will tackle OOP in a minute

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

### Empty function

~~~java
class HelloWorld {
    public static void emptyFunction() {
        
    }
}
~~~

~~~python
def empty_function():
    pass
~~~

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

### Enumerate

~~~python
punten = [15,16,8,9]

for i, punt in enumerate(punten):
  print(f'student {i} heeft {punt} punten')
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

### Collection destructuring

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


### Functional programming




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