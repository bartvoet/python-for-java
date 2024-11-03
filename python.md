# Python samples

https://github.com/blu3r4y/python-for-java-developers?tab=readme-ov-file

https://realpython.com/java-vs-python/

https://raygun.com/blog/java-vs-python/

https://python.pages.doc.ic.ac.uk/java/lessons/java/01-intro/03-example.html

https://www.javatpoint.com/basic-python-for-java-developers

https://stackoverflow.com/questions/63667488/is-there-assignment-expression-for-java-like-walrus-operator-in-python

vs walrus operator

## Level 1

### Hello World

~~~python
class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!"); 
    }
}
~~~


~~~python
print("hello world")
~~~

* You can **run** a main without defining a class
* The equivalent of **System.out.println** in Python is the built-in **print**-functoin
* The syntax in calling functions is similar to how you invoke them in java Java
* No semicolon `;` required

### Variables

Let's add a variable

~~~java
class HelloWorld {
    public static void main(String[] args) {
        String message = "Hello, World!";
        System.out.println(message); 
    }
}
~~~

In python you can define a variable just as in Java but you
don't need to declare a type neither do you need to use a var-keyword

~~~python
message = "Hello World"
print(message)
~~~

### Dynamic typing

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

Where in Python a handle is actually containing some type-information 
(interface or class that the actual heap-object is implementing) in 
Python this is just a simple label (name) and a pointer to the object

~~~python
message = "Hello World"
print(message)
message = 1 + 3
print(message)
~~~

### Comments

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


~~~python
# One line comment
message = "Hello World"
print("hello world")
'''
Multiline comments
over here
'''
~~~

### Format string

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

### Input and output

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

### Function

Let's start with a simple static functions 

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

## Datatypes

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

~~~
<class 'str'>
<class 'int'>
<class 'bool'>
<class 'float'>
<class 'complex'>  
~~~


### Integer division

~~~python
print(5 // 2) # 2
print(5 / 2) # 2.5
~~~


### Only integer

No short, long, double

Arbitrary precision

~~~python
b = 1000000000000000000000000000000000000000000000000000000
~~~


~~~java
int b = 1000000000000000000000000000000000000000000000000000000
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


### Operations


Het **overzicht** van deze **rekenkundige operatoren** vindt je hier onder:

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

## Control

### if - else

~~~python
x = 5
if x < 0:
    print("negative")
else:
    print("positive")
~~~


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


~~~python
x = 0
if x < 0:
    print("negative")
elif x == 0:
    print("zero")
else:
    print("positive")
~~~

### match - case

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




### Ternary expression vs if expression


~~~python
a = 5 if 5 < 10 else 20
~~~

### Exceptions

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