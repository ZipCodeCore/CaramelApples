+++
categories = ['Development', 'Java']
date = '2023-08-25'
description = 'More Questions for Java technical interview.'
slug = 'java5-tech'
tags = ['Java', 'Technical']
title = 'More Java Questions'
+++
# More Java Interview Questions

## Core Java Questions for Beginners

####  Is Data Passed by Reference or by Value in Java?

Although the answer to this question is pretty simple, this question may be confusing for beginners. First, let’s clarify what the question is about:

Passing by value – means that we pass a copy of an object as a parameter into a method.
Passing by reference – means that we pass a reference to an object as a parameter into a method.
To answer the question we have to analyze two cases. They represent two types of data that we can pass to a method: a primitive and an object.

When we pass primitives to a method, its value is copied into a new variable. When it comes to objects, the value of the reference is copied into a new variable. So we can say that Java is a strictly pass-by-value language.

We can learn more about that in one of our articles: Pass-By-Value as a Parameter Passing Mechanism in Java.

####  What Is the Difference Between Import and Static Imports?

We can use regular imports to import a specific class or all classes defined in a different package:

```java
import java.util.ArrayList; //specific class
import java.util.*; //all classes in util package
```

We can also use them to import public nested classes of an enclosing class:

```java
import rock.zipcode.Dicey.*
```

However, we should be aware that the import above doesn’t import class A itself.

There are also static imports that enable us to import static members or nested classes:

```java
import static java.util.Collections.EMPTY_LIST;
```

The effect is that we can use the static variable EMPTY_LIST without prepending the fully qualified class name, i.e. as if it was declared in the current class.

####  Which Access Modifiers Are Available in Java and What Is Their Purpose?

There are four access modifiers in Java:

- private
- default (package)
- protected
- public

The private modifier assures that class members won’t be accessible outside the class. It can be applied to methods, properties, constructors, nested classes, but not to top-level classes themselves.

Unlike the private modifier, we can apply the default modifier to all types of class members and to the class itself. We can apply default visibility by not adding any access modifier at all. If we use default visibility our class or its members will be accessible only inside the package of our class. We should keep in mind that the default access modifier has nothing in common with the default keyword.

Similar to the default modifier, all classes within one package can access protected members. What’s more, the protected modifier allows subclasses to access the protected members of a superclass, even if they are not within the same package. We can’t apply this access modifier to classes, only to class members.

The public modifier can be used together with the class keyword and all class members. It makes classes and class members accessible in all packages and by all classes.

####  Which Other Modifiers Are Available in Java and What Is Their Purpose?

There are five other modifiers available in Java:

static
final
abstract
synchronized
volatile
These do not control visibility.

First of all, we can apply the static keyword to fields and methods. Static fields or methods are class members, whereas non-static ones are object members. Class members don’t need an instance to be invoked. They are called with the class name instead of the object reference name. This article goes into more detail about the static keyword.

Then, we have the final keyword. We can use it with fields, methods, and classes. When final is used on a field, it means that the field reference cannot be changed. So it can’t be reassigned to another object. When final is applied to a class or a method, it assures us that that class or method cannot be extended or overridden. The final keyword is explained in more detail in this article.

The next keyword is abstract. This one can describe classes and methods. When classes are abstract, they can’t be instantiated. Instead, they are meant to be subclassed. When methods are abstract, they are left without implementation and can be overridden in subclasses.

The synchronized keyword may be the most advanced. We can use it with the instance as well as with static methods and code blocks. When we use this keyword, we make Java use a monitor lock to provide synchronization on a given code fragment. More information about synchronized can be found in this article.

The last keyword we’re going to discuss is volatile. We can only use it together with instance fields. It declares that the field value must be read from and written to the main memory – bypassing the CPU cache. All reads and writes for a volatile variable are atomic. The volatile keyword is explained in detail in this article.

####  What Is the Difference Between JDK, JRE, and JVM?

JDK stands for Java Development Kit, which is a set of tools necessary for developers to write applications in Java. 

JRE is a Java Runtime Environment. It’s a part of the JDK, but it contains the minimum functionality to run Java applications. It consists of a Java Virtual Machine, core classes, and supporting files. For example, it doesn’t have any compiler.

JVM is the acronym for Java Virtual Machine, which is a virtual machine able to run programs compiled to bytecode. It’s described by the JVM specification, as it’s important to ensure interoperability between different implementations. The most important function of a JVM is to enable users to deploy the same Java application into different operating systems and environments without worrying about what lies underneath.


####  What Is the Difference Between Stack and Heap?

There are two parts of memory where all variables and objects are stored by the JVM. The first is the stack and the second is the heap.

The stack is a place where the JVM reserves blocks for local variables and additional data. The stack is a LIFO (last in first out) structure. It means that whenever a method is called, a new block is reserved for local variables and object references. Each new method invocation reserves the next block. When methods finish their execution, blocks are released in the reversed manner they were started.

Every new thread has its own stack.

We should be aware that the stack has much less memory space than the heap. And when a stack is full, the JVM will throw a StackOverflowError. It’s likely to occur when there is a bad recursive call and the recursion goes too deep.

Every new object is created on the Java heap which is used for a dynamic allocation. There is a garbage collector which is responsible for erasing unused objects which are divided into young (nursery) and old spaces. Memory access to the heap is slower than access to the stack. The JVM throws an OutOfMemoryError when the heap is full.

####  What Is the Difference Between the Comparable and Comparator Interfaces?

Sometimes when we write a new class, we would like to be able to compare objects of that class. It’s especially helpful when we want to use sorted collections. There are two ways we can do this: with the Comparable interface or with the Comparator interface.

First, let’s look at the Comparable interface:

```java
public interface Comparable<T> {
    int compareTo(T var1);
}
```

We should implement that interface by the class whose objects we want to sort.

It has the compareTo() method and returns an integer. It can return three values: -1, 0, and 1 which means that this object is less than, equal to or greater than the compared object.

It’s worth mentioning that the overridden compareT0() method should be consistent with the equals() method.

On the other hand, we can use the Comparator interface. It can be passed to the sort() methods of the Collection interface or when instantiating sorted collections. That’s why it’s mostly used to create a one-time sorting strategy.

What’s more, it’s also useful when we use a third-party class that doesn’t implement the Comparable interface.

Like the compareTo() method, the overridden compare() methods should be consistent with the equals() method, but they may optionally allow comparison with nulls.

####  What Is the void Type and When Do We Use It?

Every time we write a method in Java, it must have a return type. If we want the method to return no value, we can use the void keyword.

We should also know that there is a Void class. It’s a placeholder class that may be used, for example, when working with generics. The Void class can neither be instantiated nor extended.

####  What Are the Methods of the Object Class and What Do They Do?

It’s important to know what methods the Object class contains and how they work. It’s also very helpful when we want to override those methods:

- clone() – returns a copy of this object
- equals() – returns true when this object is equal to the object passed as a parameter
- finalize() – the garbage collector calls this method while it’s cleaning the memory
- getClass() – returns the runtime class of this object
- hashCode() – returns a hash code of this object. We should be aware that it should be consistent with the equals() method
- notify() – sends a notification to a single thread waiting for the object’s monitor
- notifyAll() – sends a notification to all threads waiting for the object’s monitor
- toString() – returns a string representation of this object
- wait() – there are three overloaded versions of this method. It forces the current thread to wait the specified amount of time until another thread calls notify() or notifyAll() on this object.

####  What Is an Enum and How We Can Use It?

Enum is a type of class that allows developers to specify a set of predefined constant values. To create such a class we have to use the enum keyword. Let’s imagine an enum of days of the week:

```java
public enum Day {
    SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY 
}
```

To iterate over all constants we can use the static values() method. What’s more, enums enable us to define members such as properties and methods like regular classes.

Although it’s a special type of class, we can’t subclass it. An enum can, however, implement an interface.

Another interesting advantage of Enums is that they are thread-safe and so they are popularly used as singletons.

####  What Is a JAR?

JAR is a shortcut for Java archive. It’s an archive file packaged using the ZIP file format. We can use it to include the class files and auxiliary resources that are necessary for applications. It has many features:

- Security – we can digitally sign JAR files
- Compression – while using a JAR, we can compress files for efficient storage
- Portability – we can use the same JAR file across multiple platforms
- Versioning – JAR files can hold metadata about the files they contain
- Sealing – we can seal a package within a JAR file. This means that all classes from one package must be included in the same JAR file
- Extensions – we can use the JAR file format to package modules or extensions for existing software

####  What Is a NullPointerException?

The NullPointerException is probably the most common exception in the Java world.  It’s an unchecked exception and thus extends RuntimeException. We shouldn’t try to handle it.

This exception is thrown when we try to access a variable or call a method of a null reference, like when:

- invoking a method of a null reference
- setting or getting a field of a null reference
- checking the length of a null array reference
- setting or getting an item of a null array reference
- throwing null

####  What Are Two Types of Casting in Java? Which Exception May Be Thrown While Casting? How Can We Avoid It?

We can distinguish two types of casting in Java. We can do upcasting which is casting an object to a supertype or downcasting which is casting an object to a subtype.

Upcasting is very simple, as we always can do that. For example, we can upcast a String instance to the Object type:

```java
Object str = "string";
```

Alternatively, we can downcast a variable. It’s not as safe as upcasting as it involves a type check. If we incorrectly cast an object, the JVM will throw a ClassCastExcpetion at runtime. Fortunately, we can use the instanceof keyword to prevent invalid casting:

```java
Object o = "string";
String str = (String) o; // it's ok

Object o2 = new Object();
String str2 = (String) o2; // ClassCastException will be thrown

if (o2 instanceof String) { // returns false
    String str3 = (String) o2;
}
```

## Core Java Questions for Advanced Programmers

####  Why Is String an Immutable Class?

We should know that String objects are treated differently than other objects by the JVM. One difference is that String objects are immutable. It means that we can’t change them once we have created them. There are several reasons why they behave that way:

They are stored in the string pool which is a special part of the heap memory. It’s responsible for saving a lot of space.
The immutability of the String class guarantees that its hash code won’t change. Due to that fact, Strings can be effectively used as keys in hashing collections. We can be sure that we won’t overwrite any data because of a change in hash codes.
They can be used safely across several threads. No thread can change the value of a String object, so we get thread safety for free.
Strings are immutable to avoid serious security issues. Sensitive data such as passwords could be changed by an unreliable source or another thread.
We can learn more about the immutability of Strings in this article.

####  What Is the Difference Between Dynamic Binding and Static Binding?

Binding in Java is a process of associating a method call with the proper method body. We can distinguish two types of binding in Java: static and dynamic.

The main difference between static binding and dynamic binding is that static binding occurs at compile time and dynamic binding at runtime.

Static binding uses class information for binding. It’s responsible for resolving class members that are private or static and final methods and variables. Also, static binding binds overloaded methods.

Dynamic binding, on the other hand, uses object information to resolve bindings. That’s why it’s responsible for resolving virtual and overridden methods.

####  What Is JIT?

JIT stands for “just in time”. It’s a component of the JRE that runs in the runtime and increases the performance of the application. Specifically, it’s a compiler that runs just after the program’s start.

This is different from the regular Java compiler which compiles the code long before the application is started. JIT can speed up the application in different ways.

For example, the JIT compiler is responsible for compiling bytecode into native instructions on the fly to improve performance. Also, it can optimize the code to the targeted CPU and operating system.

Additionally, it has access to many runtime statistics which may be used for recompilation for optimal performance. With this, it can also do some global code optimizations or rearrange code for better cache utilization.

####  What Is Reflection in Java?

Reflection is a very powerful mechanism in Java. Reflection is a mechanism of Java language which enables programmers to examine or modify the internal state of the program (properties, methods, classes etc.) at runtime. The java.lang.reflect package provides all required components for using reflection.

When using this feature, we can access all possible fields, methods, constructors that are included within a class definition. We can access them irrespective of their access modifier. It means that for example, we are able to access private members. To do that, we don’t have to know their names. All we have to do is to use some static methods of Class.

It’s worth knowing that there is a possibility to restrict access via reflection. To do that we can use the Java security manager and the Java security policy file. They allow us to grant permissions to classes.

When working with modules since Java 9, we should know that by default, we aren’t able to use reflection on classes imported from another module. To allow other classes to use reflection to access the private members of a package we have to grant the “Reflection” Permission.

####  What Is a Classloader?

The classloader is one of the most important components in Java. It’s a part of the JRE.

Simply put, the classloader is responsible for loading classes into the JVM. We can distinguish three types of classloaders:

- Bootstrap classloader – it loads the core Java classes. They are located in the <JAVA_HOME>/jre/lib directory
- Extension classloader – it loads classes located in <JAVA_HOME>/jre/lib/ext or in the path defined by the java.ext.dirs property
- System classloader – it loads classes on the classpath of our application

A classloader loads classes “on demand”. It means that classes are loaded after they are called by the program. What’s more, a classloader can load a class with a given name only once. However, if the same class is loaded by two different class loaders, then those classes fail in an equality check.

There is more information about classloaders in the Class Loaders in Java article.

####  What Is the Difference Between Static and Dynamic Class Loading?

Static class loading takes place when we have source classes available at compile time. We can make use of it by creating object instances with the new keyword.

Dynamic class loading refers to a situation when we can’t provide a class definition at the compile time. Yet, we can do that at runtime. To create an instance of a class, we have to use the Class.forName() method:

```java
Class.forName("oracle.jdbc.driver.OracleDriver")
```

####  What Is the Purpose of the Serializable Interface?

We can use the Serializable interface to enable the serializability of a class, using Java’s Serialization API. Serialization is a mechanism for saving the state of an object as a sequence of bytes while deserialization is a mechanism for restoring the state of an object from a sequence of bytes. The serialized output holds the object’s state and some metadata about the object’s type and types of its fields.

We should know that subtypes of serializable classes are also serializable. However, if we want to make a class serializable, but its supertype is non-serializable we have to do two things:

implement the Serializable interface
assure that a no-argument constructor is present in the superclass
We can read more about Serialization in one of our articles.

####  Is There a Destructor in Java?

In Java, the garbage collector automatically deletes the unused objects to free up the memory. Developers have no need to mark the objects for deletion, which is error-prone. So it’s sensible Java has no destructors available.

In case the objects hold open sockets, open files, or database connections, the garbage collector is not able to reclaim those resources. We can release the resources in the close method and use try-finally syntax to call the method afterward before Java 7, such as the I/O classes FileInputStreamand FileOutputStream. As of Java 7, we can implement the interface AutoCloseable and use try-with-resources statement to write shorter and cleaner code.  But it’s possible the API users forget to call the close method, so the finalize method and Cleaner class come into existence to act as the safety net. But please be cautioned they are not equivalent to the destructor.

It’s not assured both the finalize method and the Cleaner class will run promptly. They even get no chance to run before the JVM exits. Although we could call System.runFinalization to suggest that JVM run the finalize methods of any objects pending for finalization, it’s still non-deterministic.

Moreover, the finalize method can cause performance issues, deadlocks, etc. We can find more information by looking at one of our articles: A Guide to the finalize Method in Java.

As of Java 9, the Cleaner class is added to replace the finalize method because of the downsides it has. As a result, we have better control over the thread which does the cleaning actions.

But the java spec points out the behavior of cleaners during System.exit is implementation-specific and Java provides no guarantees whether cleaning actions will be invoked or not.