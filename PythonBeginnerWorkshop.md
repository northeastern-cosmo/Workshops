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

