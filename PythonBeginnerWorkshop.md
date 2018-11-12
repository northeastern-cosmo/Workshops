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

