---
title: Beginner’s Guide to Java ♨️ Part 1 of 4
slug: guide-to-java-1
date: 2021-5-27
author: Atharva Joshi
read_time: 5
tags: [Java]
order: 1
hero: https://raw.githubusercontent.com/atharva20-coder/devatharva.com/master/src/images/posts/java-img/javaBanner.jpg
draft: false
emoji: "</>"
---

These blogs will help you learn Java Programming & Concepts in a simple and effective way.
If you have no prior knowledge in Java, you won’t face any difficulty. If you are experienced java developer, this blog will help you brush up the concepts.

# JVM, JRE, JDK

This is how the magic happens, you write your logic aka code in a java file, its converted into class file so that the machine can read your logic and run it.

<img src="https://miro.medium.com/max/875/1*dwYTp2UJxD0l_utvXEHy_A.png">

**Briefly these points covers it all:**

- JVM is the java virtual machine that runs the java byte code.
- JVM can be loaded on various hardware platforms, byte codes are the machine language of JVM. So Java is a better portable language. JVM is the entity that makes Java portable; there are different implementations of JVM for different OS (mac, windows, linux) etc.
- JRE is java runtime environment that is sufficient to run the program.
- JRE = JVM + library files/java package classes (Util, Lang, Math etc).
- JDK is java development kit, required to write, compile and run a program.
- JDK = JRE + Tools needed to develop java program.

# Memory allocation 🧠

So in the backgroud how the memory allcation works from your code. Brief pointers:

- Each time object is created in Java it is stored in heap memory.
- Primitive variables and local are stored in stack, member variables in heap.
- In multithreading each thread will have its own stack but will share same heap. We will discuss multithreading later in part 2.
- Methods and variables are pushed to the stack when a method is invoked and stack pointer is decremented when call is completed.
  32 bit OS can’t use more than 4GB RAM for java application. 64 bit use more memory for same object, almost twice.
- Primitive int uses 4 times less memory than Integer.

<br><br>
<img src="https://miro.medium.com/max/750/0*YnLwmAEJscRkHwx_." alt="memory-allocation">

  <p style="text-align: center;"> Memory Allocation Representation </p>
<br>

The below table gives an idea of various datatypes and range of values it can hold.

| Data-Type |              Size              |             Range |
| :-------- | :----------------------------: | ----------------: |
| Byte      |          8-bit signed          |       -128 to 127 |
| Short     |         16-bit signed          | -32,768 to 32,767 |
| int       |         32-bit signed          |  -2^31 to 2^31 -1 |
| long      |         64-bit signed          |   -2^63 to 2^63-1 |
| char      |         16-bit unicode         |       0 to 2^15-1 |
| double    | 64-bit IEEE 754 floating point | -2^1074 to 2^1.74 |
| float     | 32-bit IEEE 754 floating point |                   |

# OOPS — Encapsulation, Inheritance, Polymorphism, and Abstraction

Object Oriented Programming(OOP) is a programming concept that works on the 4 principles.

1. **Encapsulation**

   Encapsulation is wrapping data(variables) and functionality(methods) together as a single unit. Functionalities mean “methods” and data means “variables”. Its all wrapped in is “class.” It is a blueprint or a set of instruction.

**Class:** A class is a blueprint or prototype that defines the variables and the methods. For example:
<br><br>

> **Class:** Car
>
> **Data members or objects:** Color, Type, Model, etc.
>
> **Methods:** Stop, Accelerate, Cruise.

<br>

**Object:** Now, an object is a specimen of a class. Like in the above example my car is an object of the class Car.

**Variable:** can be local, instance and static. Local variables are declared inside the body of a method. Instance variables are declared outside method. They are object specific. Static variables are initialized only once and at the start of program execution. Static variables are initialized first, we will discuss static in detail later.

**Method:** methods are various functionalities, its nothing but set of code which is referred to by name and can be called (invoked) at any point in a program. You can pass multiple values to a method and it returns value(s).

**Package:** A Package is a collection of related classes. It helps organize classes into a folder structure and make it easy to locate and reuse them.

```java
package com.example;
class Car {
    String color = "black"; //instance variable
    void accelerate() {
        int speed = 90; //local variable
    }
}

```

2. **Abstraction**

   Abstraction is selecting data from a larger pool to show only the relevant details to the object. Here is a chart showing different access modifiers and how it restricts the data from a class.

<img src="https://miro.medium.com/max/875/1*F9fPgoOxgzEGDrd2bJpfkQ.png" alt="modifiers">

3.  **Inheritance**

    Inheritance is a mechanism in which one class acquires the property of another class. For example, a child inherits the traits of his/her parents.

```java
class Developer{
  public void writeCode(){
  // writeCode method

}
class BackendDeveloper extends Developer{
  public void writeCode(){
  // writeCode method
  }
}
Class run{
  public static void main (String args[]){
    Developer developerObject = new Developer()
	// writeCode method in class Developer will be executed
    developerObject.writeCode();

    BackendDeveloper backendDeveloperObj = new BackendDeveloper();
    // writeCodemethod in class BackendDeveloper will be executed
    backendDeveloperObj.writeCode();
  }
}
```

4. **Polymorphism**

   Polymorphism is a OOPs concept where one name can have many forms also knows as overloading. Dynamic Polymorphism is the mechanism by which multiple methods can be defined with same name and signature in the superclass and subclass also known as overriding.

   - Overloading is multiple methods in the same class with same name but different method signature.

   - Overriding deals with two methods, one in parent class and one in child class and both have same name and signature.

   - Subclass method overrides the method from super class.

   - In overriding sub classes access modifier must be greater than parent class E.g if we use public abc() in parent class and private abc() in sub class that will throw exception.

# Static Class Loading and Dynamic Class Loading

- Loading the class to JVM to run is called class loading.

- Classes are statically loaded using new operator.

- Very first class is loaded using static main() method and then subsequent class are loaded.

- Server based projects do not have main() at all, server provides infrastructure. Class to be loaded first is mentioned in config file. So the framework implements main() method and provides API in many cases. E.g: Container invokes init() method in servelets.

- Main is required when Java program is run on JVM from command prompt.

- NoClassDefinationFoundException is thrown if class reference is not found during static class loading.

- Dynamic class loading is programmatically invoking class at run time. E.g: Class.forName(String ClassName);

- ClassNotFoundException is thrown for dynamic class loading.

# Abstract Class and Interface

- Interface has no implementation code and all methods are abstract i.e. all methods are only declared and none are defined.

- Abstract class has executable methods and abstract methods.

- A class can implement any number of interfaces but can extend only one abstract class.

- In abstract class methods can be abstract and may not be.

- An abstract class cannot be instantiated in can only be subclassed.

- All abstract methods must be defined in subclass else the subclass should be abstract.

- Interface cannot be instantiated it can only be implemented by other classes or extended by other interfaces.

- Interface variables are final and static; interface methods are public and abstract by default.

- Interface cannot contain implementation and cannot be subclassed, so variables have to be constant.

# Java Packages

Here are some libraries available in java package to help code better. We will discuss them all eventually.
<br>
<img src="https://miro.medium.com/max/875/1*9-kl0KixCNNWIxo_6NmndA.png" alt="java packages">

# Constructor

- The sole purpose of having Constructors is to create an instance of a class. They are invoked while creating an object of a class.

- If a constructor with arguments has been defined in a class, you can no longer use a default no-argument constructor — you have to write one.

- Java Doesn’t support Copy Constructor.

- Constructor has same name as class.

- Once constructor can be called from other using ‘this’ syntax, this means this object.

- Java provides default constructor.

- Private constructor:

- Prevent class from being explicitly instantiated.

- Object can be constructed but internally.

- Used for singleton.

> **Question:** Can constructors be synchronized in Java?
>
> > No. Java doesn’t allow multi thread access to object constructors so synchronization is not even needed.
>
> **Question:** Are constructors inherited? Can a subclass call the parent’s class constructor?
>
> > You cannot inherit a constructor. By overriding a superclasses constructor you would erode the encapsulation abilities of the language. By Super keyword we can call the parents class contructor.

# Static

- Static is used to have only one copy i.e. when we want to create variable or method that is shared by all objects of the class.

- Static is used to share information across all the objects.

- Static is used for variables, methods and block.

- Static variables or method belong o the class and not to the object.

- Static variable or method is initialized once before instance variable.

- Static variable or method can be directly call from class name e.g. <className>.<variableName>

- Static method can access only static data.

- Static method cannot refer this or super.

- Static method can only call other static methods.

- Main method is static coz it must be accessible for an application to run before any instantiation takes place.

- Constructor cannot be made static coz compiler will treat it as a method, also constructor is used to initialize new object where static is opposite of it.

- Static variable is loaded first and then static block, although the sequence does matters. Static methods are loaded in the end.

- Hirarchy is:

> Static parent → Static child → Instance parent → Constructor parent → Instance child → Constructor child.

- While overriding static method, Complier doesn’t give any error and runs fine but it’s not overriding it is called hiding, coz we won’t get the benefits of run time polymorphism.

# Final, Finalize and Finally

- Final keyword is used if we don’t want to change its value.

- Final class cannot be extended.

- Final method cannot be overridden.

- Final variables are equivalent to constants.

- Finally block is called in all cases for a try catch block, used to release system resources like connections, statements etc. We will discuss try, catch and finally blocks in detail.

- Finalize() method helps garbage collection, this method is invoked before an object is discarded by garbage collector.

# Object Class

Every class has Object as super class. It has the following non-final methods:

- equal()
- hashCode()
- toString()
- clone()
- finalize()

It has the following final methods:

- wait()
- notify()
- notifyAll()
- getClass()

# Equals and HashCode

- equals() and hashCode() methods are overridden to compare two objects.

- equal() method makes equals comparison & hasCode method provide the hashCode.

```java
public class Tiger {
private String color;
private String stripePattern;
private int height;
public String getColor() {
 return color;
}
public String getStripePattern() {
 return stripePattern;
}

public Tiger(String color, String stripePattern, int height) {
 this.color = color;
 this.stripePattern = stripePattern;
 this.height = height;
}
@Override
public boolean equals(Object object) {
 boolean result = false;
 if (object == null || object.getClass() != getClass()) {
   result = false;
 } else {
   Tiger tiger = (Tiger) object;
   if (this.color == tiger.getColor() && this.stripePattern == tiger.getStripePattern()) {
       result = true;
       }
  }
return result;
}
@Override
public int hashCode() {
 int hash = 3;
 hash = 7 * hash + this.color.hashCode();
 hash = 7 * hash + this.stripePattern.hashCode();
 return hash;
}
}
```

# Clone

- Clone method is used to copy an object.

- Clone method has protected access modifier.

- To call the clone method the object must implement Clonable interface, else it will throw CloneNotSupportedException.

- Clonable interface is markers interface i.e. no methods defined interface. They just tell the class that it needs to be treated differently.

- The advantage of having clonable is we can clone only those objects that allow us to clone.

- If any field of an object is referred in other object, we will use shallow copy. In shallow copy only the memory address is copied i.e. same object is shared.

- In deep copy the object is created and dynamically new memory is allocated.

```java
Public Object Clone(){
Try{
Return super.clone();
}}
Public Object Clone(){
Try{
Object obj = (Object) super.clone();
Return obj;
}}
```

Don’t worry about the try statement, we will discuss in detail eventually.

# Aggregation and composition

- Aggregation expresses an ‘IS A’ relationship. E.g: House is a building.

- Composition expresses ‘HAS A’ relationship. E.g: House has a bathroom. This is a part of whole relationship where a part cannot exist without the whole.

- Aggregation is a weaker relationship and composition is stronger.

- Aggregations are generally achieved by extending a class and composition by implementing interface.

# Primitive and Wrapper Type

A variable of a primitive type directly contains the value of that type. Java has eight primitive types: `byte`, `short`, `int`, `long`, `char`, `boolean`, `float` and `double`.

A Wrapper class is a class whose object wraps or contains a primitive data types. When we create an object to a wrapper class, it contains a field and in this field, we can store a primitive data types and various other supporting, operational methods. It is slower to use the Object wrappers for primitives than just using the primitives. You’re adding the cost of object instantiation, method calls, etc. Each of Java’s eight primitive data types has a class dedicated to it like Byte, Short, Integer, Long, String, Boolean, Float and Double.

# Autoboxing and Unboxing

- Java 1.5 compiler provides automatic conversion of primitive datatype to wrapper type, this is known as Autoboxing and the reverse is Unboxing.

- Compiler internally uses valueOf() and intValue() for the same.

# Casting

- Assigning a value to other primitive value is casting.

> byte → short → int → long → float → double

- Upcasting is possible, e.g:

> int i = 5; long j = i;

- Downcasting is not possible, needs explicit casting:

> long j = 5;
>
> int i = j; (THIS IS WRONG, it will give classCastException)
>
> int i = (int) j;

- int to String casting is not possible.

## You just completed part 1 👏👏

## Thank you for reading!😀 I hope you enjoyed it and please share if you enjoyed it.

<br><br><br>
