---
title: Beginner’s Guide to Java ♨️ Part 4 of 4
slug: guide-to-java-4
date: 2021-6-21
author: Atharva Joshi
read_time: 5
tags: [Java]
order: 1
hero: https://raw.githubusercontent.com/atharva20-coder/devatharva.com/master/src/images/posts/java-img/javaBanner.jpg
draft: false
emoji: "</>"
---

These blogs will help you learn Java Programming & Concepts in a simple and effective way. If you have no prior knowledge in Java, you won’t face any difficulty. If you are experienced java developer, this blog will help you brush up the concepts.

# Java 8 functional programming support

Functional programming is an alternative to object-oriented programming that is centered around pure functions. Functional applications avoid the shared state, and tend to be more concise and predictable than those using object-oriented code. In a pure mathematical sense a pure function is:

- Completely stateless, no variables storing state or values, no global variables
- No memory aka absence of memory or side effect
- Performs parallel evaluation, no need to synchronize and so are much simpler than multi-threading.

Using this functional programming style can produce cleaner, readable OO code with fewer problems. So, how can we harness functional programming from Java and what all is added?

1. Storing a function in an Object

In Java 8, the **java.util.Function<T, R>** Interface was introduced. It can store a function which takes one argument and returns an object. The Generic T is the type of the argument and R the type of the object you return. For example:

```java
public static Integer calculate(Function<Integer, Integer> function, Integer value) {
return function.apply(value);
}
```

2. Functional Interface

Functional interface are inteface with single abstract method. They can have only one functionality to exhibit. From Java 8 lambda expressions can be used to represent the instance of a functional interface. **Runnable, Comparator,Comparable** are some of the examples of functional interfaces.

```java
class Test
{
 public static void main(String args[])
 {
 new Thread(new Runnable()
  {
  @Override
  public void run()
  {
    System.out.println(“Hello”);
   }
 }).start();
 }
}
```

Using lambda expression to functional interface:

```java
class Test
{
 public static void main(String args[])
 {
 new Thread(()->
 {System.out.println(“Hello lambda”);}).start();
 }
}
```

3. Default methods in Interface

Interfaces always had public static final fields, from Java 8 they can have default methods. Before Java 8, we had to create anonymous inner class objects or implement these interfaces. The basic idea of a default method is: it is an interface method with a default implementation, and a derived class can provide a more specific implementation.

> So why not keep using Abstract class?
>
> Abstract classes are still a way to introduce state, or implement the core Object methods, its coupled with state. Default methods in interface are for **pure behavior**.

An example of default method is **nullLast** method in Comparator interface.

```java
Comparator<Obj> newComparator = Comparator.nullLast(oldComparator);

```

**As Lambda expressions are introduced. It was quite difficult to add support of lambda expressions in existing collection interfaces. To add a support of Lambda expressions, they need to rewrite all interfaces of collection framework which introduced concept of Default Methods in interfaces.**

So, supporting functional programming, the Interfaces are stateless and it can have multiple static default methods.

4. No more `synchronized` on interface methods

Synchronization is the capability to control the access of multiple threads to shared resources. Synchronized static methods have a lock on the class ”Class” so when a thread enters a synchronized static method, the class itself gets locked by the thread monitor and no other thread can enter any static synchronized methods on that class. This is unlike instance methods, as multiple threads can access “same synchronized instance methods” as same time for different instances.

For example, Run method of runnable class can be synchronized, If u make run method synchronized then the lock on runnable object will be occupied before executing the run method.

Synchronization is about locking. Locking is about coordinating shared access to mutable state. Each object should have a synchronization policy that determines which locks guard which state variables. Many objects use as their synchronization policy the Java Monitor Pattern, in which an object’s state is guarded by its intrinsic lock.

But interfaces do not own the state of the objects into which they are mixed in. Subclasses may override methods that are declared synchronized in super classes, effectively removing synchronization. This would give you the false sense of confidence that you have done something about thread safety, and no error message tells you that you’re assuming the wrong synchronization policy.

5. Optionals

We all hate nulls and null checks. It sucks that for every arugument we have to check whether it is null or not.

In Java 8, **java.util.Optional<T>** was introduced to handle objects which might not exist better. It is a container object that can hold another object. The Generic T is the type of the object you want to contain.

```java
Integer i = 5;
Optional<Integer> optionalInteger = Optional.of(i);
```

The Optional class doesn’t have any public constructor. To create an optional, we use **Optional.of(object)** if the object is never, ever null OR **Optional.ofNullable(object)** for nullable objects.

6. Lambda Expressions

Lambda expressions are readable and expressive way to code the processing of lists or collections. It’s a method without a declaration, i.e., access modifier, return value declaration, and name. It saves you the effort of declaring and writing a separate method to the containing class.

Lambdas are often:

- Passed as arguments to higher-order functions
- Used to construct the result of a higher- order function that needs to return a function
- Passed as an argument (common usage)

They enable you to treat functionality as a method argument, or code as data.

```java
MathOperation addition = (int a, int b) -> a + b;

addition(a,b);
```

7. Streams

Streams are a wonderful new way to work with data collections. Almost every Stream method returns the Stream again, so developers can continue to work with it. Streams have the ability to filter, map, and reduce while being traversed.

Streams are also immutable and a one-time-use Object. Once it has been traversed, it cannot be traversed again. Every time developers manipulate it, they create a new Stream. The way it it supports functional programming is if developers convert a Data Structure into a Stream and work on it, the original data structure won’t be changed. So absence of memory aka no side effects!

Check the examples for various utilization of Streams:

Simple Stream

```java
public void convertObjects() {
Stream<String> objectStream = Stream.of(“Hello”, “World”);
}
```

Arrays to Stream

```java
public void convertStuff() {
String[] array = {“hello”, “world”};
Stream<String> arrayStream = Arrays.stream(array);
}
```

Concat multiple Lists into Stream

```java
public void concatList() {
List<Integer> list1 = Arrays.asList(1, 2, 3);
List<Integer> list2 = Arrays.asList(4, 5, 6);
Stream.of(list1, list2) //Stream<List<Integer>>
.flatMap(List::stream) //Stream<Integer>
.forEach(System.out::println); // 1 2 3 4 5 6
}
```

Usage of Filter for conditions in Stream

```java
public void filterNull() {
Stream.of(2, 1, null, 3).filter(Objects::nonNull).map(num -> num)
// without filter, you would’ve got a NullPointerExeception
.forEach(System.out::println);
}
```

Usage of Collectors to convert Stream to List

```java
public void showCollect() {
List<Integer> filtered = Stream.of(0, 1, 2, 3).filter(num -> num).collect(Collectors.toList());
}
```

Performing reducing tasks

```java
public void showReduceSum() {
 int[] array = {23,43,56,97,32};
 Arrays.stream(array).reduce((x,y) -> x+y).ifPresent(s -> System.out.println(s));
}
```

Sorting data in Stream

```java
public void showSort() {
Stream.of(3, 2, 4, 0).sorted((c1, c2) -> c1 — c2).forEach(System.out::println); // 0 2 3 4
}
```

8. Other points

Apart from proper utilization of all the above supports to write cleaner and readable functional programming code, there are few small things like avoiding usage of global variables in functions, keeping final variables, using functions as parameters and writing functions that only depends on its parameters.

# Java 9 reactive programming support

Reactive programming is all about data flows. The data flows emitted by one component will propagate to another component. **Event buses, click events, twitter feeds** are similar asynchronous event stream or data stream. **Observable Class and Observer Interface** is a good example of reactive paradigm. To summarize reactive programming is all about creating architecture that supports: Event driven or message driven (asynchronous), Scalable, Reslient and Responsive.

**Java 9 introduced a Flow API and common interfaces for the Reactive Programming, providing a step by step way to implement the reactive programming.**The Flow APIs has covered the communication aspect (request, slow down, drop, block, etc.) enabling us to adopt Reactive Programming, not needing additional libraries such as RxJava or Project Reactor, amongst others. The Flow has four nested interfaces:

- Flow.Processor<T,R> → If we want to transform incoming message and pass it further to the next Subscriber, we need to implement the Processor interface. For operations like chaining transformations of items from publishers to subscribers.

```java
public static interface Processor<T,R> extends Subscriber<T>, Publisher<R> {
}
```

- Flow.Publisher<T> → to produce/publish items and control signals.

```java
@FunctionalInterface
public static interface Publisher<T> {
public void subscribe(Subscriber<? super T> subscriber);
}
```

- **Flow.Subscriber<T> →** The receiver of messages needs to implement the Subscriber interface, to receive those messages and signals.

```java
public static interface Subscriber<T> {
public void onSubscribe(Subscription subscription);
public void onNext(T item);
public void onError(Throwable throwable);
public void onComplete();
}
```

- Flow.Subscription → to link both the Publisher and the Subscriber.

```java
public static interface Subscription {
public void request(long n);
public void cancel();
}
```

- **java.util.concurrent.SubmissionPublisher<T> →** So Flow API has only one implementing class of the Publisher that implements **Flow.Publisher<T>** and it is a producer of items, compliant with the Reactive Streams initiative.

The below example will clearly example the flow and various interfaces methods and its usage.

## Publishing and Consuming Messages

In a simple reactive flow, we have a Publisher publishing messages, and a simple Subscriber consuming messages as they arrive — one at the time.The Publisher publishes a stream of data that the Subscriber is asynchronously subscribed to.

Check the example, **SubmissionPublisher** class implements **Publisher,** the Publisher has one method subscribe(), for subscribers to receive events published by it, and SubmissionPublisher’s submit method produces the items.

```java
public class FlowMain {
public static void main(String[] args) {
SubmissionPublisher<String> publisher = new SubmissionPublisher<>();
MySubscriber<String> subscriber1 = new MySubscriber<>(“One”);
MySubscriber<String> subscriber2 = new MySubscriber<>(“Two”);
publisher.subscribe(subscriber1);
publisher.subscribe(subscriber2);
publisher.submit(“Hello”);
publisher.submit(“Universe”);
try {
Thread.sleep(1000);
} catch (InterruptedException e) {
e.printStackTrace();
}
publisher.close();
}
}
```

Lets discuss the interface methods of subscriber:

- **onSubscribe(subcription) →** The Publisher will invoke this method when getting a new Subscriber. Normally We either save the subscription since it will be used later to send signals to the Publisher: request more items, or cancel the subscription. It’s also common to use it right away to request the first item, as we do here.
- **onNext(item) →** This method will be invoked whenever a new item is received. Usually, in this method we handle processing that item, logging and requesting a new one.
- **onError(throwable) →** This is called by the Publisher to tell the Subscriber that something went wrong. Moreover, to log the message when the Publisher drops an item.
- **onComplete() →** this one is invoked when the Publisher does not have more items to send, so the Subscription is completed.

So lets see the Implementation of Subscriber:

```java
public class MySubscriber<T> implements Subscriber<T> {
private Subscription subscription;
private String name;
public MySubscriber(String name) {
this.name = name;
}
@Override
public void onComplete() {
System.out.println(name + “: Completed”);
}
@Override
public void onError(Throwable t) {
System.out.println(name + “: Weird... its an error”);
t.printStackTrace();
}
@Override
public void onNext(T msg) {
System.out.println(name + “: “ + msg.toString() + “ received a message”);
subscription.request(1);
}
@Override
public void onSubscribe(Subscription subscription) {
System.out.println(name + “: onSubscribe”);
this.subscription = subscription;
subscription.request(1);
}
}
```

## How is it different from Observer pattern?

The question might araise, we already had Observable Class and Observer Interace in Java. So, why this is introduced and how is it different?

One of the main difference is in Publisher-Subscriber pattern, the publisher and subscriber don’t know each other, the communication is through queues or brokers. So, the are loosely coupled. In Observer pattern, the observer knows all subjects. The Publisher/Subscriber pattern is mostly implemented in an asynchronous way and can be used across multiple applications or microservices whereas observer pattern is very synchronous.

## You just completed part 4 👏👏

## Thank you for reading!😀 I hope you enjoyed it and please share if you enjoyed it.

<br><br><br>
