---
title: Beginner’s Guide to Java ♨️ Part 3 of 4
slug: guide-to-java-3
date: 2021-6-11
author: Atharva Joshi
read_time: 5
tags: [Java]
order: 1
hero: /src/images/posts/java-img/javaBanner.jpg
draft: false
---

These blogs will help you learn Java Programming & Concepts in a simple and effective way. If you have no prior knowledge in Java, you won’t face any difficulty. If you are experienced java developer, this blog will help you brush up the concepts.

# Threads

- A thread is a small executable program, a process can contain multiple threads(lightweight process).
- Threads can be used either by:

1. Extending Thread class
2. Implementing Runnable interface.

```java
public class Test extends Thread {
public void run(){
// logic
}
Thread t1 = new Test();
// Thread t1 = new Thread(new Test()); FOR RUNNABLE
t1.Start();
}
```

- Runnable is preferred as there is scope of multiple inheritance.
- Start() method calls run() method but we cannot call run() directly as it will not create new thread, run will cause current thread to execute run(). It’s like calling direct method without any thread.

<br><br>
<img src="/src/images/posts/java-img/thread.jfif" alt="thread">
<br><br>
Object.wait() → Thread will be blocked till notify is called.
<br><br>
Object.notify() → Wakes up a single thread that is waiting on this object’s monitor and put it in runnable mode.
<br><br>
Object.notifyAll() → Wakes up all threads that is waiting on this object’s monitor.
<br><br>
Thread.yield() → Puts current thread to runnable and takes next thread.
<br><br>
Thread.sleep() → Puts the thread on sleep/suspended state for few milliseconds, we can pass time to the sleep method as parameter.
<br><br>

- Demon thread is low priority thread that always run in the background e.g. garbage collection thread.
  <br><br>
- To avoid deadlocks make sure you won’t synchronize code which makes blocking call.

# Mutex and Semaphore

Tool used for thread synchronization. A semaphore is a very relaxed type of lockable object. A given semaphore has a predefined maximum count, and a current count. Lock provides mutual exclusion, but does not serve queues or ordering problem like printing jobs or producer consumer problems. For this we have Semaphore.

```java
public class Semaphore {
int value;
// No of users that can use Resource
public Semaphore(int init) {
if (init < 0) {
init = 0;
}
value = init;
}
// Acquiring Resource
public synchronized void down() {
while (value == 0) {
try {
wait();
} catch (InterruptedException e) {
}
value — ;
}
}
// Releasing Resource
public synchronized void up() {
value++;
notify();
}
}
```

We will initialize Semaphore class before Start() method, in the run we will first call semaphoreObject.down() to lock and task completion we call semaphoreObject.up().

A mutex is a “Mutual Exclusion Semaphore”. It refers to a type of lockable object that can be owned by exactly **one thread at a time**. Only the thread that acquired the lock can release the lock on a mutex. When the mutex is locked, any attempt to acquire the lock will fail or block, even if that attempt is done by the same thread.

# Error Handling

<img src="/src/images/posts/java-img/error handling.jfif" alt="java error handling">
<br><br>

1. Error is dynamic linkage failure or hand machine failure that is unlikely to happen.
2. Unchecked exceptions are runtime exceptions happens with JVM executing program e.g. nullPointerException.

```java
public class MyException extends Exception {
private String errorCode = “Unkown_Exception”;
public MyException(String message, String errorCode){
super(message);
this.errorCode = errorCode;
}
Public String getErrorCode(){
Return this.errorCode;
}
}
```

- throw keyword is used to throw exception to the runtime to handle it.
- When we are throwing any exception in a method and not handling it, then we need to use throws keyword in method signature to let caller program know the exceptions that might be thrown by the method.

# Observable Class and Observer Interface

1. There is a design pattern called Observer. It is useful to notify serveral objects(Observer) when something has happened to one instance(Observable).

2. It is commonly used in Ajax to notify several objects when an event(link onclick) occurs.
3. What you basically do it:
4. Have an Observable class.
   - Have a few Observer classes.
   - Register the Observers to the Observable object (addObserver).
   - Call notifyObserver when you want to notify all the observers that something has happened.

# JDBC

- JDBC is a Java API(set of classes and interfaces) that is used to connect and execute query to the database. It uses jdbc drivers to connect to the database.
- JDBC Driver is a software component that enables java application to interact with the database.
- There are 3 JDBC statements:

  1. Statement: query is compiled each time.
  2. PreparedStatement: query is compiled only once. So performance is better.
  3. CallableStatement: To execute procedures and functions.

- The DriverManager class manages the registered drivers.
- The ResultSet object represents a row of a table.
- The ResultSetMetaData interface returns the information of table such as total number of columns, column name, column type etc.
  Sample Code:

```java
@Resource(mappedName = “jdbc/DarmAircom”)
private javax.sql.DataSource dataSource;
Connection connection = dataSource.getConnection();
CallableStatement statement = connection.prepareCall(“call ABC.ABC_PKG.PROCEDURE_NAME(?,?,?,?,?,?,?,?,?,?,?,?,?)”);
statement.execute();
statement.close();
connection.close();
```

# Reading & Writing File

ByteStream: For reading and writing binary data, byte stream is incorporated.
<br><br>
CharacterStreams: It work with the characters rather than the byte.
<br><br>
FileInputStream: It contains the input byte from a file and implements an input stream.
<br><br>
FileOutputStream: It uses for writing data to a file and also implements an output stream.
<br><br>
Reading from File: A FileReader class is a general tool to read in characters from a File. The BufferedReader class can wrap around Readers, like FileReader, to buffer the input and improve efficiency.

```java
public static void readFromFile(String fileName) throws IOException {
int total = 0;
BufferedReader in = new BufferedReader( new FileReader(fileName));
for ( String s = in.readLine(); s != null; s = in.readLine() ) {
// GOT EACH LINE
}
in.close();
}
```

_File name would be something like “C:/Users/Atharva/Desktop/task.txt”_
<br><br>
Writing to File: Check out the example for writing to file using FileOutputStream.
<br><br>

```java
File fout = new File(file_location_string);
FileOutputStream fos = new FileOutputStream(fout);
BufferedWriter out = new BufferedWriter(new OutputStreamWriter(fos));
out.write(“something”);
Using FileWriter:
FileWriter fstream = new FileWriter(file_location_string);
BufferedWriter out = new BufferedWriter(fstream);
out.write(“something”);
```

FileOutputStream is meant for writing streams of raw bytes such as image data. For writing streams of characters, consider using FileWriter.

# Design Patterns

##Singleton Pattern

- Instantiated only once in JVM per class loader.
- Constructor should have private access modifier, so that it cannot be instantiated outside the class.
- Only way to instantiate an instance is by getInstance() method with public access modifier. It should be static method.
- SessionFactory class and logger class are examples of singleton classes.

```java
public class Singleton {
private static Singleton instance = new Singleton();
private singleton() {}
public static Singleton getInstance(){
return instance;
}
}
```

## Factory Pattern

**Factory pattern** is one of the most used **design patterns in Java.** In **Factory pattern**, we create object without exposing the creation logic to the client and refer to newly created object using a common interface. For example:

```java
interface Dog {
public void speak ();
}
class Poodle implements Dog {
public void speak() {
System.out.println(“The poodle says \”arf\””);
}
}
class Rottweiler implements Dog {
public void speak() {
System.out.println(“The Rottweiler says (in a very deep voice) \”WOOF!\””);
}
}
class DogFactory {
public static Dog getDog(String criteria) {
if ( criteria.equals(“small”) )
return new Poodle();
else if ( criteria.equals(“big”) )
return new Rottweiler();
return null;
}
}
public class JavaFactoryPatternExample {
public static void main(String[] args) {
Dog dog = DogFactory.getDog(“small”);
dog.speak();
dog = DogFactory.getDog(“big”);
dog.speak();
}
}
```

# Adaptor Pattern

It’s used so that two unrelated interfaces can work together. Example:

```java
public interface SocketAdapter {
public Volt get120Volt();
public Volt get12Volt();
public Volt get3Volt();
}
```

## Builder Pattern

Builder pattern is the extension of Factory pattern wherein the Builder class builds a complex object in multiple steps.

# Few Important points

- A java.util.Date represents data and time of the day, a java.sql.Date only represents a date (the complement of java.sql.Date is java.sql.Time, which only represents a time of day, but also extends java.util.Date)
- Synchronization is the capability to control the access of multiple threads to shared resources.
- Synchronized static methods have a lock on the class”Class” so when a thread enters a synchronized static method, the class itself gets locked by the thread monitor and no other thread can enter any static synchronized methods on that class. This is unlike instance methods, as multiple threads can access “same synchronized instance methods” as same time for different instances. public synchronized void synchronizedMethod() {}
- A Thread Dump is a complete list of active threads.
- Thread leak is when an application does not release reference to a thread object properly. Due to this some Threads do not get garbage collected and the number of unused threads grow with time.
- A Thread Pool is a collection of threads on which task can be scheduled. Instead of creating new thread for each task.
- Constructors cannot be synchronized coz other threads cannot see the object being created before the thread creating it has finished it.
- Run method of runnable class can be synchronized, If u make run method synchronized then the lock on runnable object will be occupied before executing the run method.
- A cluster is group of computers that can individually run a software. Clustering is needed for achieving high availability for a server software. The main purpose of clustering is to achieve 100% availability or a zero down time in service.
- Load balancing is simple technique for distributing work load across multiple machines or clusters.
- <mark>Fail over means switching to another machine when one of the machine fails.</mark>
- JEE applications use the concept of distributing web application to provide session-failover and enable load balancing. By adding distributable tag in web.xml file (distributable/).
- Java is always pass-by-value. The difficult thing to understand is that Java passes objects as references and those references are passed by value.
- In Java, the Arrays.sort() methods use merge sort or a tuned quicksort depending on the datatypes and for implementation efficiency switch to insertion sort when fewer than seven array elements are being sorted. Arrays.sort is used indirectly by the Collections classes.
- 0xDEADBEEF (“dead beef”) is frequently used to indicate a software crash or deadlock in embedded systems. DEADBEEF was originally used to mark newly allocated areas of memory that had not yet been initialized — when scanning a memory dump, it is easy to see the DEADBEEF. It is used by IBM RS/6000 systems, Mac OS on 32-bit PowerPC processors and the Commodore Amiga as a magic debug value. On Sun Microsystems’ Solaris, it marks freed kernel memory. On OpenVMS running on Alpha processors, DEAD_BEEF can be seen by pressing CTRL-T. The DEC Alpha SRM console has a background process that traps memory errors, identified by PS as “BeefEater waiting on 0xdeadbeef”.

<br><br><br>

## You just completed part 3 👏👏

## Thank you for reading!😀 I hope you enjoyed it and please share if you enjoyed it.

<hr>
