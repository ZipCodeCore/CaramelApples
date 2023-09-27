+++
categories = ['Development', 'Java']
date = '2023-08-25'
description = 'Questions for easy Java technical interview.'
slug = 'java4-tech'
tags = ['Java', 'Technical']
title = 'More Easy Java Questions'
+++

### Simples

* Sum Integers from 7 to 23, print sum
* Find and print the smallest integer in an array a = [9, 5, 6, 3, 8, 2, 4];
* Given an array of objects (of class Xaction) w/nulls, sum all the values of the objects in the array, using Xaction::getValue(). Print the sum.
* reverse an array of objects of type Xaction


### **What is meant by the Local variable and the Instance variable?**

**Answer:** 

**Local variables** are defined in the method and scope of the variables that exist inside the method itself.

**Instance variable** is defined inside the class and outside the method and the scope of the variables exists throughout the class.


### **What is a Class?**

**Answer:** All Java codes are defined in a Class. It has variables and methods.

**Variables** are attributes which define the state of a class.

**Methods** are the place where the exact business logic has to be done. It contains a set of statements (or) instructions to satisfy the particular requirement.

 \n What is the shortest class you can write in Java? \n class Foo{}

### **What is an Object?**

**Answer:** An instance of a class is called an object. The object has state and behavior.

Whenever the JVM reads the “new()” keyword then it will create an instance of that class.


create me a new object of type Foo. \n 

### What are the four access modifiers?

public, private, default, protected.

And what do they mean?

Public:

Public members are visible in the same package as well as the outside package that is for other packages.

Public members of Class A are visible to Class B (same package) as well as Class C (different packages).

**Private:** 

Private members are visible in the same class only and not for the other classes in the same package as well as classes in the outside packages.

Private members in class A are visible only in that class. It is invisible for class  B as well as class C.

### **What is Polymorphism?**

**Answer:** Polymorphism means many forms.

A single object can refer to the super-class or sub-class depending on the reference type which is called polymorphism.

**__Example:__**

```javascript
Public class Manipulation(){ //Super class

public void add(){}

}

public class Addition extends Manipulation(){ // Sub class

public void add(){}

public static void main(String args[]){

Manipulation addition = new Addition();//Manipulation is reference type and Addition is reference type

addition.add();

}

}
```

Using the Manipulation reference type we can call the Addition class “add()” method. This ability is known as Polymorphism. Polymorphism is applicable for **overriding** and not for **overloading**. \n 

### **What is meant by a JAVA Interface?**

**Answer:** Multiple inheritances cannot be achieved in java. To overcome this problem the Interface concept is introduced.

An interface is a template which has only method declarations and not the method implementation.

### **What is meant by Abstract class?**

**Answer:** We can create the Abstract class by using the “Abstract” keyword before the class name. An abstract class can have both “Abstract” methods and “Non-abstract” methods that are a concrete class.

**and a Abstract method?**

The method which has only the declaration and not the implementation is called the abstract method and it has the keyword called “abstract”. Declarations ends with a semicolon.


### How would you build me a HashMap from scratch?


### **Difference between Abstract class and Interface.**

**Answer: The differences between Abstract Class and Interface are as follows: \n **

**Abstract Class:**

* Abstract classes have a default constructor and it is called whenever the concrete subclass is instantiated.
* It contains Abstract methods as well as Non-Abstract methods.
* The class which extends the Abstract class shouldn’t require the implementation of all the methods, only Abstract methods need to be implemented in the concrete sub-class.
* Abstract class contains instance variables.

**Interface:**

* It doesn’t have any constructor and couldn’t be instantiated.
* The abstract method alone should be declared.
* Classes that implement the interface should provide the implementation for all the methods.
* The interface contains only constants.

### **What is the meaning of Collections in Java?**

**Answer:** Collection is a framework that is designed to store many objects in various ways.


**Collections are used to perform the following operations:**

* Searching
* Sorting
* Manipulation
* Insertion
* Deletion

A group of objects is known as collections. All the classes and interfaces for collecting are available in Java util package.


What’s your favorite Collection Class and Why? \n 

### **What’s MAP in Java? .**

**Answer: A collection interface.**

**Map** allows us to keep key/value pairs. It has a unique key to a specific value. We can search for a value, based on the key. Like the set, the map also uses the “equals ( )” method to determine whether two keys are the same or different.


**What is Hash Map?**

* Unordered and unsorted map.
* Hashmap is a good choice when we don’t care about the order.
* It allows one null key and multiple null values.

Create a hash map that uses an object as a key and a URL as it’s value.


### **What is meant by Exception?**

**Answer:** An Exception is a problem that can occur during the normal flow of execution. A method can throw an exception when something fails at runtime. If that exception couldn’t be handled, then the execution gets terminated before it completes the task.

If we handled the exception, then the normal flow gets continued. Exceptions are a subclass of java.lang.Exception.

### **What are the types of Exceptions?**

**Answer:** There are two types of Exceptions. They are explained below in detail.

**a) Checked Exception:**

These exceptions are checked by the compiler at the time of compilation. Classes that extend Throwable class except Runtime exception and Error are called checked Exception.

Checked Exceptions must either declare the exception using throws keyword (or) surrounded by appropriate try/catch.

**__For Example,__** ClassNotFound Exception

**b) Unchecked Exception:**

These exceptions are not checked during the compile time by the compiler.  The compiler doesn’t force to handle these exceptions. **It includes:**

* Arithmetic Exception
* ArrayIndexOutOfBounds Exception

### **What are the different ways to handle exceptions?**

**Answer:** **Two different ways to handle exceptions are explained below:**

**a) Using try/catch:**

The risky code is surrounded by try block. If an exception occurs, then it is caught by the catch block which is followed by the try block.

**__Example:__**
| `class` `Manipulation{``public` `static` `void` `main(String[] args){``add();``}``Public void` `add(){``try{``addition();``}catch(Exception e){``e.printStacktrace();``}``}``}` |

**b) By declaring throws keyword:**

At the end of the method, we can declare the exception using throws keyword.

**__Example:__**
| `class` `Manipulation{``public` `static` `void` `main(String[] args){``add();``}``public` `void` `add() throws` `Exception{``addition();``}``}` |


