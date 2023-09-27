+++
categories = ['Development', 'Python']
date = '2023-08-25'
description = 'Questions for Starter Python technical interview.'
slug = 'python3-tech'
tags = ['Python', 'Technical']
title = 'Easy Python Questions'
+++

### Write simple function that sums the number from 1 to n

```python
def asum(n):
  return sum(range(n+1))
```

### Write a function that takes a list and turns a new list with the last two elements removed.

```python
def drop2(l):
    return l[:-2]
```

### write a function that drops the first item in a list

```python
def dropfirst(l):
  return l[1:]
```

### Take two lists and concatenate them.

```python
a = [1,2,3]
b = [7,8,9]
def ccat(l,r):
  return l + r
```

### Write a function that returns a dictionary of letter frequencies from a word

```python
word = 'brontosaurus'

def cw(word):
d = {}
for i in word:
	if i not in d:
		d[i] = 1
	else:
		d[i] +=1
return d

print(cw(word))
```


### What is slicing in Python?

```python

#As the name suggests, ‘slicing’ is taking parts of.
#Syntax for slicing is [start : stop : step]
#start is the starting index from where to slice a list or tuple
#stop is the ending index or where to stop.
#step is the number of steps to jump.
#Default value for start is 0, stop is number of items, step is 1.
#Slicing can be done on strings, arrays, lists, and tuples.

numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
print(numbers[1 : : 2])  #output : [2, 4, 6, 8, 10]
```

### What are lists and tuples? What is the key difference between the two?

**Lists** and **Tuples** are both **sequence data types** that can store a collection of objects in Python. The objects stored in both sequences can have **different data types**. Lists are represented with **square brackets** `['Desa', 6, 0.19]`, while tuples are represented with **parantheses** `('Dolio', 5, 0.97)`.  But what is the real difference between the two? The key difference between the two is that while**lists are mutable**, **tuples** on the other hand are **immutable** objects. This means that lists can be modified, appended or sliced on the go but tuples remain constant and cannot be modified in any manner. You can run the following example on Python IDLE to confirm the difference:

```python
my_tuple = ('Desa', 6, 5, 0.97)
my_list = ['Desa', 6, 5, 0.97]
print(my_tuple[0])     # output => 'Desa'
print(my_list[0])     # output => 'Desa'
my_tuple[0] = 'Dolio'    # modifying tuple => throws an error
my_list[0] = 'Dolio'    # modifying list => list modified
print(my_tuple[0])     # output => 'Desa'
print(my_list[0])     # output => 'Dolio'
```

### What are Dict and List comprehensions?

Python comprehensions, like decorators, are **syntactic sugar** constructs that help **build altered** and **filtered lists**, dictionaries, or sets from a given list, dictionary, or set. Using comprehensions saves a lot of time and code that might be considerably more verbose (containing more lines of code). Let's check out some examples, where comprehensions can be truly beneficial:


```python
my_list = [2, 3, 5, 7, 11]
squared_list = [x**2 for x in my_list]    # list comprehension
# output => [4 , 9 , 25 , 49 , 121]
squared_dict = {x:x**2 for x in my_list}    # dict comprehension
# output => {11: 121, 2: 4 , 3: 9 , 5: 25 , 7: 49}

my_list = [2, 3, 5, 7, 11]
squared_list = [x**2 for x in my_list if x%2 != 0]    # list comprehension
# output => [9 , 25 , 49 , 121]
squared_dict = {x:x**2 for x in my_list if x%2 != 0}    # dict comprehension
# output => {11: 121, 3: 9 , 5: 25 , 7: 49}

a = [1, 2, 3]
b = [7, 8, 9]
[(x + y) for (x,y) in zip(a,b)]  # parallel iterators
# output => [8, 10, 12]
[(x,y) for x in a for y in b]    # nested iterators
# output => [(1, 7), (1, 8), (1, 9), (2, 7), (2, 8), (2, 9), (3, 7), (3, 8), (3, 9)] 
```


### What are the common built-in data types in Python?

There are several built-in data types in Python. Although, Python doesn't require data types to be defined explicitly during variable declarations type errors are likely to occur if the knowledge of data types and their compatibility with each other are neglected. Python provides `type()` and `isinstance()` functions to check the type of these variables. These data types can be grouped into the following categories-

* **None Type:**  `None` keyword represents the null values in Python. Boolean equality operation can be performed using these NoneType objects.
  | Class Name | Description |
  |----|----|
  | NoneType | Represents the **NULL** values in Python. |

* **Numeric Types:**  There are three distinct numeric types -**integers, floating-point numbers**, and **complex numbers**. Additionally, **booleans** are a sub-type of integers.
  | Class Name | Description |
  |----|----|
  | int | Stores integer literals including hex, octal and binary numbers as integers |
  | float | Stores literals containing decimal values and/or exponent signs as floating-point numbers |
  | complex | Stores complex numbers in the form (A + Bj) and has attributes: `real` and `imag` |
  | bool | Stores boolean value (True or False). |

***Note:*** *The standard library also includes **fractions** to store rational numbers and **decimal** to store floating-point numbers with user-defined precision.*

* **Sequence Types:**  According to Python Docs, there are three basic Sequence Types -**lists, tuples,** and **range** objects. Sequence types have the `in` and `not in` operators defined for their traversing their elements. These operators share the same priority as the comparison operations.
  | Class Name | Description |
  |----|----|
  | list | Mutable sequence used to store collection of items. |
  | tuple | Immutable sequence used to store collection of items. |
  | range | Represents an immutable sequence of numbers generated during execution. |
  | str | Immutable sequence of Unicode code points to store textual data. |

**Note:**The standard library also includes additional types for processing:  1.**Binary data** such as `bytearray bytes` `memoryview`, and  2.**Text strings** such as `str`.

* **Mapping Types:**

A mapping object can map hashable values to random objects in Python. Mappings objects are mutable and there is currently only one standard mapping type, the ***dictionary***.
| Class Name | Description |
|----|----|
| dict | Stores comma-separated list of **key: value** pairs |

* **Set Types:**  Currently, Python has two built-in set types -**set** and **frozenset**. **set** type is mutable and supports methods like `add()` and `remove()`. **frozenset** type is immutable and can't be modified after creation.
  | Class Name | Description |
  |----|----|
  | set | Mutable unordered collection of distinct hashable objects. |
  | frozenset | Immutable collection of distinct hashable objects. |

***Note: ***`set` *is mutable and thus cannot be used as key for a dictionary. On the other hand,* `frozenset` *is immutable and thus, hashable, and can be used as a dictionary key or as an element of another set.*

* **Modules:**  Module is an additional built-in type supported by the Python Interpreter. It supports one special operation, i.e.,**attribute access**: `mymod.myobj`, where `mymod` is a module and **myobj** references a name defined in m's symbol table. The module's symbol table resides in a very special attribute of the module **__dict__**, but direct assignment to this module is neither possible nor recommended.

* **Classes:**  Classes are the most important data types in Python. Python is an object-oriented programming language and almost every entity in Python is an object, which means that they have attributes and methods. A class is like a blueprint for creating objects. An object has properties and methods(functions) associated with it. Almost everything in Python is an object, with its properties and methods. A Class is like an object constructor, or a "blueprint" for creating objects.  **Note:** *The **dir()** function returns all properties and methods of the specified object, without the values. This function will return all the properties and methods, even built-in properties which are default for all object.*

* **Callable Types:**  Callable types are the types to which function call can be applied. They can be**user-defined functions, instance methods, generator functions**, and some other **built-in functions, methods** and **classes**.  Refer to the documentation at[docs.python.org](https://docs.python.org/3/reference/datamodel.html) for a detailed view of the **callable types**.


