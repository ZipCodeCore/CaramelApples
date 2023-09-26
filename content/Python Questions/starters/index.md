+++
categories = ['Development', 'Python']
date = '2023-08-25'
description = 'Questions for Starter Python & SQL technical interview.'
slug = 'python3-tech'
tags = ['Python', 'SQL', 'Technical']
title = 'Easy Python & SQL Questions'
+++
# Python & SQL Interview Qs

\
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

**Lists** and **Tuples** are both s**equence data types** that can store a collection of objects in Python. The objects stored in both sequences can have **different data types**. Lists are represented with **square brackets** `['sara', 6, 0.19]`, while tuples are represented with **parantheses** `('ansh', 5, 0.97)`. \n But what is the real difference between the two? The key difference between the two is that while**lists are mutable**, **tuples** on the other hand are **immutable** objects. This means that lists can be modified, appended or sliced on the go but tuples remain constant and cannot be modified in any manner. You can run the following example on Python IDLE to confirm the difference:

```python
my_tuple = ('sara', 6, 5, 0.97)
my_list = ['sara', 6, 5, 0.97]
print(my_tuple[0])     # output => 'sara'
print(my_list[0])     # output => 'sara'
my_tuple[0] = 'ansh'    # modifying tuple => throws an error
my_list[0] = 'ansh'    # modifying list => list modified
print(my_tuple[0])     # output => 'sara'
print(my_list[0])     # output => 'ansh'
```

 \n 

 \n 

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

* **None Type:** \n `None` keyword represents the null values in Python. Boolean equality operation can be performed using these NoneType objects.
  | Class Name | Description |
  |----|----|
  | NoneType | Represents the **NULL** values in Python. |
* **Numeric Types:** \n There are three distinct numeric types -**integers, floating-point numbers**, and **complex numbers**. Additionally, **booleans** are a sub-type of integers.
  | Class Name | Description |
  |----|----|
  | int | Stores integer literals including hex, octal and binary numbers as integers |
  | float | Stores literals containing decimal values and/or exponent signs as floating-point numbers |
  | complex | Stores complex numbers in the form (A + Bj) and has attributes: `real` and `imag` |
  | bool | Stores boolean value (True or False). |

***Note:*** *The standard library also includes **fractions** to store rational numbers and **decimal** to store floating-point numbers with user-defined precision.*

* **Sequence Types:** \n According to Python Docs, there are three basic Sequence Types -**lists, tuples,** and **range** objects. Sequence types have the `in` and `not in` operators defined for their traversing their elements. These operators share the same priority as the comparison operations.
  | Class Name | Description |
  |----|----|
  | list | Mutable sequence used to store collection of items. |
  | tuple | Immutable sequence used to store collection of items. |
  | range | Represents an immutable sequence of numbers generated during execution. |
  | str | Immutable sequence of Unicode code points to store textual data. |

**Note:**The standard library also includes additional types for processing: \n 1.**Binary data** such as `bytearray bytes` `memoryview`, and \n 2.**Text strings** such as `str`.

* **Mapping Types:**

A mapping object can map hashable values to random objects in Python. Mappings objects are mutable and there is currently only one standard mapping type, the ***dictionary***.
| Class Name | Description |
|----|----|
| dict | Stores comma-separated list of **key: value** pairs |

* **Set Types:** \n Currently, Python has two built-in set types -**set** and **frozenset**. **set** type is mutable and supports methods like `add()` and `remove()`. **frozenset** type is immutable and can't be modified after creation.
  | Class Name | Description |
  |----|----|
  | set | Mutable unordered collection of distinct hashable objects. |
  | frozenset | Immutable collection of distinct hashable objects. |

***Note: ***`set` *is mutable and thus cannot be used as key for a dictionary. On the other hand,* `frozenset` *is immutable and thus, hashable, and can be used as a dictionary key or as an element of another set.*

* **Modules:** \n Module is an additional built-in type supported by the Python Interpreter. It supports one special operation, i.e.,**attribute access**: `mymod.myobj`, where `mymod` is a module and **myobj** references a name defined in m's symbol table. The module's symbol table resides in a very special attribute of the module **__dict__**, but direct assignment to this module is neither possible nor recommended.
* **Callable Types:** \n Callable types are the types to which function call can be applied. They can be**user-defined functions, instance methods, generator functions**, and some other **built-in functions, methods** and **classes**. \n Refer to the documentation at[docs.python.org](https://docs.python.org/3/reference/datamodel.html) for a detailed view of the **callable types**.


# SQL

### What is the SELECT statement?

SELECT operator in SQL is used to select data from a database. The data returned is stored in a result table, called the result-set.


```javascript
SELECT * FROM myDB.students;
```

### What are some common clauses used with SELECT query in SQL?

Some common SQL clauses used in conjuction with a SELECT query are as follows:

* **WHERE** clause in SQL is used to filter records that are necessary, based on specific conditions.
* **ORDER BY** clause in SQL is used to sort the records based on some field(s) in ascending (**ASC**) or descending order (**DESC)**.


```javascript
SELECT *
FROM myDB.students
WHERE graduation_year = 2019
ORDER BY studentID DESC;
```

* **GROUP BY** clause in SQL is used to group records with identical data and can be used in conjunction with some aggregation functions to produce summarized results from the database.
* **HAVING** clause in SQL is used to filter records in combination with the GROUP BY clause. It is different from WHERE, since the WHERE clause cannot filter aggregated records.


```javascript
SELECT COUNT(studentId), country
FROM myDB.students
WHERE country != "INDIA"
GROUP BY country
HAVING COUNT(studentID) > 5;
```

### What are Entities and Relationships?

**Entity**: An entity can be a real-world object, either tangible or intangible, that can be easily identifiable. For example, in a college database, students, professors, workers, departments, and projects can be referred to as entities. Each entity has some associated properties that provide it an identity.

**Relationships**: Relations or links between entities that have something to do with each other. For example - The employee's table in a company's database can be associated with the salary table in the same database.


### What is a relationship and what are they?

Database Relationship is defined as the connection between the tables in a database. There are various data basing relationships, and they are as follows:.

* One to One Relationship.
* One to Many Relationship.
* Many to One Relationship.
* Self-Referencing Relationship.


### What is a Primary Key?

The PRIMARY KEY constraint uniquely identifies each row in a table. It must contain UNIQUE values and has an implicit NOT NULL constraint. \n A table in SQL is strictly restricted to have one and only one primary key, which is comprised of single or multiple fields (columns).

```javascript
CREATE TABLE Students (   /* Create table with a single field as primary key */
   ID INT NOT NULL
   Name VARCHAR(255)
   PRIMARY KEY (ID)
);

CREATE TABLE Students (   /* Create table with multiple fields as primary key */
   ID INT NOT NULL
   LastName VARCHAR(255)
   FirstName VARCHAR(255) NOT NULL,
   CONSTRAINT PK_Student
   PRIMARY KEY (ID, FirstName)
);

ALTER TABLE Students   /* Set a column as primary key */
ADD PRIMARY KEY (ID);
ALTER TABLE Students   /* Set multiple columns as primary key */
ADD CONSTRAINT PK_Student   /*Naming a Primary Key*/
PRIMARY KEY (ID, FirstName);
```


### What is a Foreign Key?

A FOREIGN KEY comprises of single or collection of fields in a table that essentially refers to the PRIMARY KEY in another table. Foreign key constraint ensures referential integrity in the relation between two tables. \n The table with the foreign key constraint is labeled as the child table, and the table containing the candidate key is labeled as the referenced or parent table.

```javascript
CREATE TABLE Students (   /* Create table with foreign key - Way 1 */
   ID INT NOT NULL
   Name VARCHAR(255)
   LibraryID INT
   PRIMARY KEY (ID)
   FOREIGN KEY (Library_ID) REFERENCES Library(LibraryID)
);

CREATE TABLE Students (   /* Create table with foreign key - Way 2 */
   ID INT NOT NULL PRIMARY KEY
   Name VARCHAR(255)
   LibraryID INT FOREIGN KEY (Library_ID) REFERENCES Library(LibraryID)
);

ALTER TABLE Students   /* Add a new foreign key */
ADD FOREIGN KEY (LibraryID)
REFERENCES Library (LibraryID);
```


### What is a Query?

A query is a request for data or information from a database table or combination of tables. A database query can be either a select query or an action query.

```javascript
SELECT fname, lname    /* select query */
FROM myDb.students
WHERE student_id = 1;
```

```javascript
UPDATE myDB.students    /* action query */
SET fname = 'Captain', lname = 'America'
WHERE student_id = 1;
```

### What is a Subquery? What are its types?

A subquery is a query within another query, also known as a **nested query** or **inner query**. It is used to restrict or enhance the data to be queried by the main query, thus restricting or enhancing the output of the main query respectively. For example, here we fetch the contact information for students who have enrolled for the maths subject:

```javascript
SELECT name, email, mob, address
FROM myDb.contacts
WHERE roll_no IN (
 SELECT roll_no
 FROM myDb.students
 WHERE subject = 'Maths');
```

There are two types of subquery - **Correlated** and **Non-Correlated**.

* A **correlated** subquery cannot be considered as an independent query, but it can refer to the column in a table listed in the FROM of the main query.
* A **non-correlated** subquery can be considered as an independent query and the output of the subquery is substituted in the main query.
