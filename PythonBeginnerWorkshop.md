# Intro to Python 11/12/2018

This is a short introduction to the Python programing language for beginners.

# Installation

Download and install the latest version of Python 3.x:
* MacOS: https://www.python.org/downloads/mac-osx/
  * If using brew, simply run `brew install python`
* Linux (generic source, you'll have to build it manually): https://www.python.org/downloads/source/
  * Alternatively, install from your distro's package manager
* Windows: https://www.python.org/downloads/windows/

## Sidebar: Python 2 vs Python 3
Python 3 broke backward compatibility with Python 2 programs when it was released. It introduced native unicode character support, and a slew of other changes to the core language. Due to the work involved in switching, many libraries used to only work on Python 2, but that has become far less of an issue over the last few years. You will still run into Python 2 being used in the industry or for certain libraries, but support for Python 2 is being discontinued in 2020. Unless you have a really strong reason to use Python 2, you should start all your new projects using Python 3.

# Playing with the Read-eval-print loop (REPL)

Start the REPL interpreter with the command `python` or `python3` if you have both 2 and 3 installed.

## Basic Math and Logic Operators

```Python
>>> 4 + 4
8
>>> 55 - 10
45
>>> 2 * 4
8
>>> 4 / 2 # Division float
2.0 # Note the automatic conversion to a floating point number
>>> 5 / 2
2.5
>>> 5 // 2 # Division floor
2 # Note that an integer type is returned
>>> 7 % 4 # Modulo
3
>>> 3 == 3 # Check for equality
True # All boolean constants are capitalized.
>>> 3 != 3 # Check for inequality
False
>>> 2 < 3 # Less than
True
>>> 2 > 3 # Greater than
False
>>> 3 != 3 or 3 == 3 # OR operator
True
>>> 'abc' == 'abc' and 'cdb' == 'abc' # AND operator (note that string literals can be wrapped in either single or double quotes)
False
>>> not 'abc' == 'abc'
False
```

### Math

| Operator | Description |
| -------- | ----------- |
| + | Addition|
| - | Subtraction |
| * | Multiplication |
| / | Float Division |
| // | Floor Division |
| % | Modulus |

### Comparison

| Operator | Description |
| -------- | ----------- |
| > | Greater than |
| < | Less than |
| == | Equal to |
| != | Not equal to |
| >= | Greater than or equal |
| <= | Less than or equal | 

### Logical

| Operator | Description |
| -------- | ----------- |
| and | AND operator |
| or | OR operator |
| not | Negation |


[Full List (Including Bitwise and Assignment Operators)](https://www.geeksforgeeks.org/basic-operators-python/)

## Basic Data Structures

### Lists

Lists are mutable ordered data structures of all the same type.

```Python
>>> l = ['a', 'b', 'c'] # Variable l is now bound to the list object
>>> l[0] # Lists are zero-indexed
'a'
>>> l[2]
'c'
>>> l.append('e') # Adds to end of list
>>> l
['a', 'b', 'c', 'e']
>>> l[3] = 'd' # Lists are mutable.
>>> l
['a', 'b', 'c', 'd']
>>> l.append('e')
>>> l
['a', 'b', 'c', 'd', 'e']
>>> l[1:3] # Slicing lists
['b', 'c']
>>> l[:4]
['a', 'b', 'c', 'd']
>>> l[2:]
['c', 'd', 'e']
>>> l.pop(2)
'c'
>>> l
['a', 'b', 'd']
>>> l.remove('b')
>>> l
['a', 'd']
>>> l.insert(1, 'b')
>>> l
['a', 'b', 'd']
>>> l + ['e', 'f', 'g']
['a', 'b', 'd', 'e', 'f', 'g']
```

[Full List Documentation](https://docs.python.org/3/tutorial/datastructures.html#more-on-lists)

### Tuples

Tuples are non-mutable ordered data structures of either the same or mixed types.

```Python
>>> t = (1, 2, 'a')
>>> t
(1, 2, 'a')
>>> t[1]
2
>>> x, y, z = t # Tuple unpacking
>>> x
1
>>> y
2
>>> z
'a'
```

[Full Tuple Documentation](https://docs.python.org/3/tutorial/datastructures.html#tuples-and-sequences)

### Dictionaries

Dictionaries are maps of keys to values. The types of the keys and the types of the values can be different. Note that dictionaries are unordered.

```Python
>>> d = {'a': 1, 'b': 2, 'c': 3} # You can also create an empty dictionary with dict()
>>> d
{'a': 1, 'b': 2, 'c': 3}
>>> d['b']
2
>>> d['c'] = 5
>>> d
{'a': 1, 'b': 2, 'c': 5}
>>> d['d'] = 4
>>> d
{'a': 1, 'b': 2, 'c': 5, 'd': 4}
>>> del d['c']
>>> d
{'a': 1, 'b': 2, 'd': 4}
>>> d.keys()
dict_keys(['a', 'b', 'd'])
>>> d.values()
dict_values([1, 2, 4])
>>> d.items()
dict_items([('a', 1), ('b', 2), ('d', 4)]) # Note this is iterable, see below how to use it
>>> d.pop('d')
4
>>> d
{'a': 1, 'b': 2}
>>> 'a' in d
True
>>> 'd' in d
False
>>> 'a' not in d
False
```
[Full Dictionary Documentation](https://docs.python.org/3/library/stdtypes.html#mapping-types-dict)

## Flow Control

### If Statement

```Python
>>> if 'a' in d:
...   print(d['a']) # Each line in the if statement needs to start with a tab. Python uses white space instead of braces
... # Note that the dots indicate the interpreter is waiting for further input before executing your code.
1
>>> if 'd' in d:
...   print(d['d'])
... else:
...   print('Not here!')
...
Not here!
>>> if 'd' in d:
...   print(d['d'])
... elif 'b' in d: # elif is else if in other languages
...   print(d['c'])
... else:
...   print('Not here!')
...
2
```

### For-loop

```Python
>>> l = ['a', 'b', 'c', 'd']
>>> for item in l:
...   print(item)
a
b
c
d
```

#### Looping through a dictionary

```Python
>>> d = {'a': 1, 'b': 2, 'c': 3}
>>> for k, v in d.items():
...   print(k + ': ' + str(v)) # Note the conversion from an int to a string using the str function
a: 1
b: 2
c: 3
```

#### Side Bar: Traditional for-loops

Python has no support for the traditional index based for-loops (think `for (i = 0; i < x; i++)` style for-loop). It is very rare that you will need this method, but it is still useful if you are manipulating the index as you run through the loop. To simulate this, you can use the range function:

```Python
>>> for i in range(len(l) - 1):
...   print(l[i]) # Print every element except the last one (normally in this case you'd just slice the list, but just take this as an example)
a
b
c
```

But what if you just want the index of the item? You can use the enumerate function:

```Python
>>> for i, v in enumerate(l):
...   print(str(i) + ' ' + v)
0 a
1 b
2 c
```

### List Comprehensions

List comprehensions are a special type of for loop that can transform one list into another. They are useful replacements for the `map` and `filter` functions you'd find in a language like Racket (note that python does include these functions, as well as lambdas, but list comprehensions are the preferred method)

```Python
>>> l = [2, 1, 3, 1, 5, 6]
>>> [x*2 for x in l] # Multiply each value by two
[4, 2, 6, 2, 10, 12]
>>> [x for x in l if x == 1] # Filter the list down to just the values equal to 1
[1, 1]
```

### While-loops

Python has while loops as well.

```Python
>>> x = 0
>>> while x < 4:
...   print(x) # Again, there is a built in function for this (range), but this is an easy example
...   x += 1 # Note the assignment operator (there is no x++)
...
0
1
2
3
```

### Final Notes

Python does have `break`, `continue`, and `pass` keywords for controlling the flow of loops. You can read more about these, as well as read the full documentation about flow control here:

[Flow Control Docs](https://docs.python.org/3/tutorial/controlflow.html)

## Functions

Functions in python are straight forward and defined by the `def` keyword. Functions have their own scope.

```Python
>>> def addThreeVars(x, y, z):
...   return x + y + z
...
>>> addThreeVars(1, 2, 3)
>>> 6
```

# RIP REPL

The REPL is great for testing out small pieces of code, but we need to put our code in actual files if we want to use the language for real!

## A simple code file

1. Create a new file called `hello.py` in your favorite text editor
2. Type the following in the file:
```Python
def say_hello(name): # Note that python functions should be all lower case, separated by underscores
  print('Hello ' + name)

say_hello('John')
```
3. Save the file
4. To run the file, simply call `python3 hello.py` from the command line (Don't forget to `cd` to the correct directory!)

You should see the output: `Hello John`

Note that everything written in the file will be executed from top to bottom in this case.

## Modules

Now, let's say we want to import our function into another file or the REPL environment so we can use it over and over again.

1. Remove the `say_hello('John')` line from your file
2. Open the python REPL by running `python3`
3. Type `import hello`
4. Now call your function using `hello.say_hello('Jack')`
5. You should see `Hello Jack`

In this case, the name of the file you just imported (`hello`) is the root module. The function `say_hello` is attached to this module, thus why you have to call `hello.say_hello()`.

Note that there is also now a folder called `__pycache__` in the same directory as your `hello.py` file. If you list this directory, you should see a `.pyc` file. Python is an interpreted language, but the interpreter will compile modules into bytecode files to be reused later. This happens automatically when you first load the module, and when you change the source, the `.pyc` file will be recompiled. You should not commit the `.pyc` files to source control (e.g your git repo).

If you just want to import a specific item or items from a module, you can use the `from . import .` syntax:

1. Open the python REPL by running `python3`
2. Type `from hello import say_hello`
3. Now call `say_hello('George')`
4. You should see `Hello George`

## Classes

In python, everything is actually an object. Strings for example have their own methods (such as split). You can easily make your own classes!

1. Create a new file called `person.py`
2. Enter the following:
```Python
class Person():
  def __init__(this, first, middle, last): # Note that "this" is always passed in as the first argument to every one of the class's functions. This is how you access the class's member functions and variables
    self.first = first
    self.middle = middle
    self.last = last

  def get_full_name(self):
    return self.first + ' ' + self.middle + ' ' + self.last
```
3. Open the REPL
4. Run `from person import Person`
5. To create a Person object and assign it to the variable `p`, run `p = Person('John', 'H', 'Doe')`
6. Now you can call `p.get_full_name()`
7. You should see `John H Doe`

We can combine this with our `say_hello()` function. Just run `say_hello(p.get_full_name())`.

### Inheritance

Python supports full inheritance.

1. Below your `Person` class, type following in your `person.py` file:
```Python
class Doctor(Person):
  def get_full_name(self):
    return "Dr. " + super().get_full_name()
```
2. Now in the REPL, run `from person import Doctor`
3. Run `doc = Doctor('Colin', 'H', 'Kelly')`
4. Try `doc.get_full_name()`
5. You should see `Dr. Colin H Kelly`

## Final Notes

### pip and virtualenvs

There are many useful libraries out there for python. Most, if not all, of these are accessible by using python's built in package manager: `pip`. To install a library globally on your python 3 installation, simply run `pip3 install library_name` for example, if we wanted to install matplotlib (a useful library for creating visual graphs and charts), you'd run `pip3 install matplotlib`. You can uninstall packages by running `pip3 uninstall matplotlib`.

Another useful feature of pip is requirements.txt files. If your project includes a bunch of dependencies you want to distribute, you can list them in a requirements.txt file. This allows the people who download your project to quickly install all the dependencies they need to run it. Find out more [here](https://pip.pypa.io/en/stable/user_guide/#requirements-files).

Aside from pip, another important tool is virtualenv. This tool lets you create separate, isolated, python installations. This allows you to manage the dependencies for each of your projects individually, instead of having to install everything at the global level. It is best practice to use a new virtualenv for each of your projects. See [here](https://docs.python.org/3/library/venv.html) for more info.
