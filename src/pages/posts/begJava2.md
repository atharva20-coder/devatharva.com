---
title: Beginner’s Guide to Java ♨️ Part 2 of 4
slug: guide-to-java-2
date: 2021-6-03
author: Atharva Joshi
read_time: 5
tags: [Java]
order: 1
hero: /src/images/posts/java-img/javaBanner.jpg
draft: false
---

These blogs will help you learn Java Programming & Concepts in a simple and effective way. If you have no prior knowledge in Java, you won’t face any difficulty. If you are experienced java developer, this blog will help you brush up the concepts.

# Immutable

Any class whose Object’s state cannot be changed once it is instantiated are called Immutable.

- String and all wrapper classes and enum class are example of immutable class.
- Immutable classes are inherently thread-safe.
- This is how we can make a class immutable:
  1.  Ensure class cannot be overridden — make class final.
  2.  All its fields are private.
  3.  Do not provide any method that can change the state of the object, no setter methods.
  4.  Use defensive copy or clone.
- BigDecimal is technically not immutable as its not final class.

# String, StringBuffer and StringBuilder

- String is immutable; we cannot modify a String object. Every time we assign a new value, a new String object is created in stack and pointer points to the new object.
- String pool (String intern pool) is a special storage area in Java heap. When a string is created and if the string already exists in the pool, the reference of the existing string will be returned, instead of creating a new object and returning its reference.

> Question: Why is String immutable in Java?

1. String Pool: When a string is created and if the string already exists in the pool, the reference of the existing string will be returned, instead of creating a new object. If string is not immutable, changing the string with one reference will lead to the wrong value for the other references.
2. To Cache its Hashcode: If string is not immutable, One can change its hashcode and hence not fit to be cached.
3. Security: String is widely used as parameter for many java classes, e.g. network connection, opening files, etc. Making it mutable might possess threats due to interception by the other code segment.

- String Comparison:

```java
String a = “abcd”;
String b = “abcd”;
System.out.println(a == b); // True
System.out.println(a.equals(b)); // True
String c = new String(“abcd”);
String d = new String(“abcd”);
System.out.println(c == d); // False
System.out.println(c.equals(d)); // True
```

`== Checks memory locations where as equals() checks value, using constructor will create an extra unnecessary object`. Therefore, double quotes should be used if you just need to create a String.

- String provides several methods concat(), trim(), substring() and replace().
- StringBuffer is mutable and StringBuilder is also mutable.
- StringBuilder is added in 1.5 this is not synchronized.
- intern() method is reference value of a String i.e. the address.

So S1.intern() == S2.intern(), only if S1.equals(S2) is true.

# Serialization

- The process of saving the state of an object by saving it to sequence of bytes and rebuilding it back from bytes is called serialization.
- Can be done by implementing serializable interface, it’s a marker interface.
- Fields marked as transient cannot be serialized.
- serialVersionUID is adding a version number to make sure the serialized object is not changed while getting back as deserialized.
- Serialization internally uses writeObject() and readObject() which although can be overridden and customized.
- In Externalization i.e. externalizable interface we have to use methods readExternal() and writeExternal().

# Comparator and Comparable

- Comparable interface allows itself to compare with another object uses CompareTo() method.
- Comparator interface is used to compare two different objects. Uses Compare() method.
- Method syntax:

```java
CompareTo(Object obj)
Compare(Object obj1, Object obj2)
```

- Comparator gives more control.
- **Collections.sort(list)** for Comparable and **Collections.sort(list, new comparatorObject())** for comparator.
- Comparable is implemented by a class in order to be able to comparing object of itself with some other objects.

```java
class HDTV implements Comparable<HDTV> {
private int size;
private String brand;
public HDTV(int size, String brand) {
this.size = size;
this.brand = brand;
}
// .. getters & setters
@Override
public int compareTo(HDTV tv) {
if (this.getSize() > tv.getSize())
return 1;
else if (this.getSize() < tv.getSize())
return -1;
else
return 0;
}}
public class Main {
public static void main(String[] args) {
HDTV tv1 = new HDTV(55, “Samsung”);
HDTV tv2 = new HDTV(60, “Sony”);
if (tv1.compareTo(tv2) > 0) {
System.out.println(tv1.getBrand() + “ is better.”);
} else {
System.out.println(tv2.getBrand() + “ is better.”);
}
}}
```

- In some situations, you may not want to change a class and make it comparable.

```java
class SizeComparator implements Comparator<HDTV> {
@Override
public int compare(HDTV tv1, HDTV tv2) {
int tv1Size = tv1.getSize();
int tv2Size = tv2.getSize();
if (tv1Size > tv2Size) {
return 1;
} else if (tv1Size < tv2Size) {
return -1;
} else {
return 0;
}
}}
public class Main {
public static void main(String[] args) {
HDTV tv1 = new HDTV(55, “Samsung”);
HDTV tv2 = new HDTV(60, “Sony”);
HDTV tv3 = new HDTV(42, “Panasonic”);
ArrayList<HDTV> al = new ArrayList<HDTV>();
al.add(tv1);
al.add(tv2);
al.add(tv3);
Collections.sort(al, new SizeComparator());
for (HDTV a : al) {
System.out.println(a.getBrand());
}
}}

```

# Collections

Collection is any data structure where objects are stored and iterated over. Data Structure in itself is a huge topic and I will try to cover it in a separate series. Here, we will try to cover some basic data structures in java collection libraries.

<img src="/src/images/posts/java-img/collection.jpeg" alt="java collection">

- Collection is an interface from which set, list and queue extends.
- Collections Class holds static utility methods to use with collections.
- Arrays are the fastest as compared to ArrayList or Vector and are preferable if we know the size upfront. As Arrays cannot grow as list do.
- ArrayList and Vector are specialized data structures that uses an Array internally and some convenient methods like add(), remove() etc so that they can grow and shrink whenever required.
- ArrayList supports index based Search with indexOf() and lastIndexOf() methods.
- Vector is synchronized and threadsafe, but it’s better to use ArrayList and below code for synchronization:

```
List mylist = Collections.synchronizedList(mylist);
// Single lock for the entire list
```

- Iterator interface is used to cycle through a collection in forward direction only.
- ListIterator extends Iterator and allow bidirectional traversing.
  <br><br>

  > Collection classes are fail first, i.e. if one thread changes the value while the other on is traversing it will give ConcurentModificationException. Even if we use SynchronizedList/SynchronizedMap still it will throw this exception coz these are conditionally threadsafe, which means individual operations are threadsafe but not the whole operation. So either Synchronize block can be used or ConcurentHashMap or CopyOnWriteArrayList. ConcurentHaspMap, CopyOnWriteArrayList and CopyOnWriteArraySet are thread safe or synchronized.

- HashMap works on principle of Hashing.
- Hashing in its simplest form, is a way to assigning a unique code for any variable/object after applying any formula/algorithm on its properties.
- HashMap has an inner class Entry to store key and value mapping.

<br><br>

> A hash value is calculated using key’s hash code by calling its hashCode() method. This hash value is used to calculate index in array for storing Entry object. JDK designers well assumed that there might be some poorly written hashCode() functions that can return very high or low hash code value. So there is another hash() function, and passed the object’s hash code to this hash() function to bring hash value in range of array index size.

- MapReduce has two key components. Map and Reduce. A map is a function which is used on a set of input values and calculates a set of key/value pairs. Reduce is a function which takes these results and applies another function to the result of the map function.
- It’s a good practice to use Collections.EMPTY_LIST/EMPTY_SET instead of null. E.g.

```java
List testList = Collections. EMPTY_LIST;
```

- Best practice to use immutable object as keys to Map.

<br><br>

> Arrays.asList(T… a) returns the java.util.Arrays.ArrayList and not java.util.ArrayList. Its just a view of original Array.

- Comparing ArrayList

```java
Collection<String> listOne = new ArrayList(Arrays.asList(“a”,”b”, “c”,”g”));
Collection<String> listTwo = new ArrayList(Arrays.asList(“a”,”b”,”d”, “e”));
List<String> sourceList = new ArrayList<String>(listOne);
List<String> destinationList = new ArrayList<String>(listTwo);
sourceList.removeAll( listTwo ); // Result: [c, g]
destinationList.removeAll( listOne ); // Result: [d, e]
```

- Difference between ITERATOR and ENUMERATION Interface: Iterator actually adds one method that Enumeration doesn’t have: remove(). Iterators allow the caller to remove elements from the underlying collection during the iteration with well-defined semantics.

> **Question:** How can we reverse the order in the TreeMap?
>
> > Using Collections.reverseOrder()
>
> > `Map tree = new TreeMap(Collections.reverseOrder());`
>
> **Question:** Can we add heterogeneous elements into TreeMap?
>
> > No, Sorted collections don’t allow addition of heterogeneous elements as they are not comparable. It’s okay if they class implements comparable.
>
> **Question:** Difference between int[] x; and int x[]
>
> > No Difference. Both are the acceptable ways to declare an array.

- Memory overhead hierarchy:

> ArrayList < LinkedList < HashTable < HashMap < HashSet

- Contains() uses Linear Search.
- HashMap allows one null key and multiple null values, HashTable doesn’t allow null keys or values.
- LinkedHashMap can be used to avoid collision, for LRU Cache too.
- Why ConcurentHashMap is better than HashTable.
- Sort HashMap by keys and by values.

# Guava

Guava is Google’s Core Libraries for Java with some more added classes and interfaces to Collection.

1. MultiSet and UniqueList are added. List is ordered and duplicates allowed, but UniqueList is where its ordered but duplicates are not allowed. Set is where duplicates are not allowed and its not ordered, whereas in MultiSet its not ordered and duplicates are allowed.
2. ImmutableList, ImmutableSet, ImmutableSortedSet, ImmutableMap are added.
3. ImmutableMultiSet, HashMultiSet, LinkedHashMultiSet, TreeMultiSet, EnumMultiSet and MultiMap are also added.
4. In MultiMap we have Key to Value, Many to Many relationship whereas in Java its One to Many relationship.

# Java Versions

Now that we are clear with some basic concepts, lets briefly look into some history and evolution of various versions of java.

- 1.4: I/O systems, enhanced performance, scalability were added.
- 1.5: Generics (collections, Iterator etc), enhanced for loop, autoboxing, unboxing, annotations, enums and static imports were added.
- 1.6: Windows vista full support, faster, complier side improvements, xml processing of web services were added.
- 1.7: String in switch statements, multiple exceptions in one catch block, etc. were added.
- 1.8:

**Lambda Expressions:** It’s a method without a declaration, i.e., access modifier, return value declaration, and name. It saves you the effort of declaring and writing a separate method to the containing class.
They enable you to treat functionality as a method argument, or code as data.

```java
MathOperation addition = (int a, int b) -> a + b;
addition(a,b);
```

**Date\Time APIs:** The current time is represented by the Clock class. The class is abstract, so you cannot create instances of it. The systemUTC() static method will return the current time.

```java
import javax.time.Clock;
Clock clock = Clock.systemUTC();
Clock clock = Clock.systemDefaultZone();
ZoneId zone = ZoneId.of(“Europe/Berlin”);
// ZoneId zone = ZoneId.systemDefault(); you can also use this
Clock clock = Clock.system(zone);
import javax.time.LocalDate;
LocalDate date = LocalDate.now();
```

**Stream:** A stream is a one-time-use Object. Once it has been traversed, it cannot be traversed again. Streams have the ability to filter, map, and reduce while being traversed. Using a sequential stream:

```java
List <Person> people = list.getStream.collect(Collectors.toList());
Using a parallel stream:
List <Person> people = list.getStream.parallel().collect(Collectors.toList());
```

## You just completed part 2 👏👏

## Thank you for reading!😀 I hope you enjoyed it and please share if you enjoyed it.

<br><br><br>
