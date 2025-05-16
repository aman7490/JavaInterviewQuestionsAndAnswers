📚 Java Interview Questions – Index
✅ Basic Java Concepts
What is Java?

Difference between JDK, JRE, and JVM

Difference between == and .equals()

What is Inheritance?

What is Polymorphism?

Difference between Method Overloading and Overriding

Abstract Class vs Interface

Exception Handling in Java

Difference between final, finally, and finalize()

Access Modifiers in Java

🚀 Advanced Java Concepts
ArrayList vs Vector

Garbage Collection in Java

How HashMap Works Internally

Java Memory Model (JMM)

Common Pitfalls in Multithreading

Callable and Future Interfaces

The volatile Keyword

🔍 Java Sorting Interfaces
Comparable Interface

Comparator Interface

Comparator with Lambda Expressions

Comparator with Java 8 Default Methods


## ✅ 1. What is Java?

### 📘 Detailed Answer:

Java is a **high-level**, **object-oriented**, **class-based** programming language developed by **James Gosling** at Sun Microsystems in 1995. It is designed to have as few implementation dependencies as possible.

### 🌟 Key Features:

* **Object-Oriented**: Everything is treated as an object.
* **Platform Independent**: “Write Once, Run Anywhere” using the JVM.
* **Secure and Robust**: Has strong memory management and exception handling.
* **Multithreaded**: Allows concurrent execution of two or more threads.
* **Portable**: Can run on any machine with a JVM.

---

## ✅ 2. Difference between JDK, JRE, and JVM

### 📘 Detailed Answer:

| Component                          | Description                                                                            |
| ---------------------------------- | -------------------------------------------------------------------------------------- |
| **JVM** (Java Virtual Machine)     | Runs Java bytecode and provides an environment to execute Java programs.               |
| **JRE** (Java Runtime Environment) | JVM + libraries + other files required to run Java programs.                           |
| **JDK** (Java Development Kit)     | JRE + tools like compiler (`javac`), debugger, etc., for developing Java applications. |

### 💡 Example:

If you want to **run** a Java application → you need **JRE**.
If you want to **develop** a Java application → you need **JDK**.

---

## ✅ 3. What is the difference between `==` and `.equals()` in Java?

### 📘 Detailed Answer:

* `==` checks **reference equality** (whether two references point to the same object).
* `.equals()` checks **value/content equality** (whether two objects have the same value).

### 💻 Example:

```java
String s1 = new String("hello");
String s2 = new String("hello");

System.out.println(s1 == s2);      // false (different references)
System.out.println(s1.equals(s2)); // true (same content)
```

---

## ✅ 4. What is Inheritance?

### 📘 Detailed Answer:

Inheritance allows one class (child/subclass) to acquire the properties and methods of another class (parent/superclass).

### 💻 Example:

```java
class Animal {
    void eat() {
        System.out.println("Eating...");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Barking...");
    }
}

public class TestInheritance {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.eat();  // Inherited method
        d.bark(); // Dog's method
    }
}
```

---

## ✅ 5. What is Polymorphism?

### 📘 Detailed Answer:

Polymorphism means "many forms". It allows one method to behave differently based on the object that invokes it.

### 🔸 Types:

* **Compile-time polymorphism** (Method Overloading)
* **Runtime polymorphism** (Method Overriding)

### 💻 Example: Method Overriding

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Cat extends Animal {
    void sound() {
        System.out.println("Cat meows");
    }
}
```

---

## ✅ 6. Difference between Method Overloading and Overriding

| Feature     | Overloading                            | Overriding                                |
| ----------- | -------------------------------------- | ----------------------------------------- |
| Definition  | Same method name, different parameters | Subclass provides specific implementation |
| Occurs In   | Same class                             | Subclass                                  |
| Return Type | Can be different                       | Must be same or covariant                 |

### 💻 Overloading Example:

```java
class MathUtils {
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }
}
```

### 💻 Overriding Example:

```java
class Parent {
    void show() {
        System.out.println("Parent show()");
    }
}

class Child extends Parent {
    @Override
    void show() {
        System.out.println("Child show()");
    }
}
```

---

## ✅ 7. Abstract Class vs Interface

| Feature     | Abstract Class                                  | Interface                                                        |
| ----------- | ----------------------------------------------- | ---------------------------------------------------------------- |
| Methods     | Can have both abstract and non-abstract methods | Only abstract methods (Java 7), default/static allowed (Java 8+) |
| Constructor | Can have                                        | Cannot have                                                      |
| Inheritance | Single                                          | Multiple (via interfaces)                                        |

### 💻 Example:

```java
abstract class Shape {
    abstract void draw();
    void print() {
        System.out.println("Shape");
    }
}

interface Drawable {
    void draw();
}
```

---

## ✅ 8. Exception Handling in Java

### 📘 Detailed Answer:

Java provides a powerful mechanism for handling runtime errors using:

* `try`: Code that may throw an exception
* `catch`: Code to handle the exception
* `finally`: Code that always executes
* `throw`: Used to explicitly throw an exception
* `throws`: Declares the exception

### 💻 Example:

```java
public class ExceptionExample {
    public static void main(String[] args) {
        try {
            int x = 10 / 0;
        } catch (ArithmeticException e) {
            System.out.println("Cannot divide by zero!");
        } finally {
            System.out.println("Finally block executed");
        }
    }
}
```

---

## ✅ 9. What is the difference between `final`, `finally`, and `finalize()`?

| Keyword      | Purpose                                                               |
| ------------ | --------------------------------------------------------------------- |
| `final`      | Used to declare constants, prevent method overriding, and inheritance |
| `finally`    | Block that always executes after try-catch                            |
| `finalize()` | Method called before object is garbage collected (deprecated)         |

---

## ✅ 10. What are the different access modifiers in Java?

| Modifier              | Class | Package | Subclass | World |
| --------------------- | ----- | ------- | -------- | ----- |
| `public`              | ✅     | ✅       | ✅        | ✅     |
| `protected`           | ✅     | ✅       | ✅        | ❌     |
| default (no modifier) | ✅     | ✅       | ❌        | ❌     |
| `private`             | ✅     | ❌       | ❌        | ❌     |

### 💻 Example:

```java
public class Test {
    private int a = 10;
    public int b = 20;
    protected int c = 30;
    int d = 40; // default
}
```
----------------------------------------------------------------------------


### **Advanced Java Interview Questions with In-depth Answers**

---

### **1. What are the differences between `ArrayList` and `Vector` in Java?**

Although both `ArrayList` and `Vector` implement the **List interface** and are similar in terms of functionality, they differ primarily in **thread-safety** and **synchronization**.

#### **Key Differences:**

1. **Thread-Safety**:

    * `Vector` is **synchronized**, making it thread-safe but slower when multiple threads are accessing it concurrently.
    * `ArrayList` is **not synchronized**, making it faster but not thread-safe.

2. **Growth Policy**:

    * `Vector` doubles its size when it exceeds its capacity.
    * `ArrayList` increases its size by 50% when it runs out of space.

#### **Example:**

```java
Vector<Integer> vector = new Vector<>();
vector.add(1); // Thread-safe, but slower

ArrayList<Integer> arrayList = new ArrayList<>();
arrayList.add(1); // Faster, but not thread-safe
```

---

### **2. Explain how garbage collection works in Java and how you can manage it.**

Garbage Collection (GC) in Java is the process of automatically identifying and deleting objects that are no longer in use to free up memory.

#### **Garbage Collection Process:**

1. **Mark-and-Sweep Algorithm**:

    * **Mark phase**: Identifies all live objects that are still being referenced.
    * **Sweep phase**: Removes objects that are unreachable (not referenced).

2. **Generational Garbage Collection**:

    * The JVM divides memory into **Young Generation**, **Old Generation**, and **Permanent Generation** (metaspace in later versions).
    * **Young Generation** holds newly created objects. When this space is full, minor GC occurs.
    * **Old Generation** contains objects that have survived several garbage collection cycles. Major GC (full GC) is more expensive and cleans up this area.

3. **Types of Garbage Collectors**:

    * **Serial GC**: Single-threaded garbage collection (older versions).
    * **Parallel GC**: Uses multiple threads for minor GC.
    * **CMS (Concurrent Mark-Sweep) GC**: Minimizes pause times by running concurrently with application threads.
    * **G1 (Garbage-First) GC**: Aims to provide low latency and high throughput.

#### **Managing Garbage Collection**:

* **Explicit GC**: You can suggest a garbage collection using `System.gc()` or `Runtime.getRuntime().gc()`, but it's not recommended since the JVM manages it automatically.
* **Tuning**: Garbage collectors can be tuned using JVM options to control memory sizes and behavior. For example:

  ```bash
  java -Xms512m -Xmx1024m -XX:+UseG1GC
  ```

---

### **3. How does `HashMap` work internally?**

`HashMap` in Java is backed by an array of **buckets**. Each bucket stores a **linked list** or **binary tree** (in case of high collision).

#### **How HashMap works**:

1. **Hashing**:

    * When a key-value pair is inserted, the `hashCode()` of the key is calculated. This hash code determines the index (bucket) in the internal array.
    * The key-value pair is then stored at that index.

2. **Collision Handling**:

    * **Linked List**: If two keys have the same hash code (collision), they are stored in a linked list at the same index.
    * **Red-Black Tree**: If the bucket exceeds a certain threshold, the linked list is replaced by a red-black tree for faster access.

3. **Resizing**:

    * If the number of entries exceeds the capacity (threshold), the `HashMap` resizes itself by doubling the array size and rehashing the entries.

#### **Example:**

```java
Map<String, Integer> map = new HashMap<>();
map.put("A", 1);
map.put("B", 2);
map.put("C", 3);

// Hashing and collision management
System.out.println(map.get("A"));
```

---

### **4. What is the Java Memory Model (JMM)?**

The **Java Memory Model (JMM)** defines how threads interact through memory and how the JVM handles **concurrent programming**.

#### **Key Concepts**:

1. **Visibility**:

    * When one thread modifies a variable, other threads may not immediately see the updated value unless proper synchronization is used.

2. **Atomicity**:

    * Operations on variables of size **1, 2, 4, or 8 bytes** (e.g., `int`, `long`, `boolean`) are atomic, while larger types might require synchronization to ensure atomicity.

3. **Ordering**:

    * The **happens-before** relationship ensures that the memory updates made by one thread are visible to others in a predictable order.

4. **Volatile Keyword**:

    * Ensures that changes to a variable are immediately visible to other threads.
    * It disables **caching** of variables and ensures **direct memory access**.

#### **Example:**

```java
private static volatile boolean flag = false;

public void toggleFlag() {
    flag = true;  // Other threads will see this immediately
}
```

---

### **5. What are some common pitfalls in Java multithreading?**

Multithreading can significantly improve performance, but it introduces complexity. Here are common pitfalls to watch for:

#### **Common Pitfalls**:

1. **Race Conditions**:

    * When multiple threads try to access shared resources concurrently, it can lead to inconsistent data if not properly synchronized.
    * **Solution**: Use synchronized blocks, locks, or higher-level concurrency utilities like `ReentrantLock`.

2. **Deadlocks**:

    * When two or more threads wait indefinitely for each other to release resources.
    * **Solution**: Avoid circular dependencies by acquiring resources in a fixed order.

3. **Thread Starvation**:

    * A low-priority thread may not get enough CPU time.
    * **Solution**: Use fair locks or prioritize threads accordingly.

4. **Livelocks**:

    * Threads continuously change their states in response to each other, but do not make progress.
    * **Solution**: Implement proper thread coordination and avoid unnecessary state changes.

#### **Example: Deadlock Avoidance**

```java
class A {
    synchronized void methodA(B b) {
        b.last();
    }
    synchronized void last() { }
}

class B {
    synchronized void methodB(A a) {
        a.last();
    }
    synchronized void last() { }
}
```

In the above code, if two threads execute `methodA` and `methodB` simultaneously, it could lead to a deadlock.

---

### **6. What are `Callable` and `Future` interfaces in Java?**

* **`Callable`** is similar to `Runnable`, but it can return a result and throw exceptions. It is used for concurrent tasks that may return a value.

  ```java
  Callable<Integer> task = () -> { return 123; };
  ```

* **`Future`** represents the result of an asynchronous computation. It provides methods to check if the task is completed, retrieve the result, or handle exceptions.

  ```java
  ExecutorService executor = Executors.newSingleThreadExecutor();
  Future<Integer> future = executor.submit(task);
  Integer result = future.get();  // Waits for completion and retrieves the result
  ```

---

### **7. What is the `volatile` keyword and how does it work?**

The `volatile` keyword ensures that a variable's **value** is directly read from and written to the **main memory** instead of being cached in a thread's local memory. This guarantees **visibility** in multi-threaded applications.

#### **Key Points**:

* **Visibility**: Updates to a volatile variable are visible across all threads immediately.
* **Atomicity**: `volatile` does not guarantee atomicity for operations other than simple reads and writes (e.g., `++` is not atomic).

#### **Example**:

```java
private volatile boolean flag = false;

public void toggleFlag() {
    flag = true;  // Other threads will see this immediately
}
```

------------------------------------------------------------------------

Absolutely! Let's revisit **Comparable** and **Comparator** interfaces in Java, with in-depth descriptions and detailed examples to make it easier for you to revise and remember.

---

### **1. Comparable Interface**

The **Comparable** interface is used to define the natural ordering of objects. A class that implements **Comparable** allows its objects to be sorted based on a specific criterion. The **compareTo()** method is used to compare the current object with the specified object.

#### **Key Points**

* The **Comparable** interface is part of the **java.lang** package.
* It has one method to implement: **int compareTo(T o)**.
* The method should return:

    * **Negative integer** if the current object is less than the other object.
    * **Zero** if the current object is equal to the other object.
    * **Positive integer** if the current object is greater than the other object.

#### **Example of Comparable**

Let's say we have a **Person** class, and we want to sort people based on their age.

```java
import java.util.*;

class Person implements Comparable<Person> {
    String name;
    int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Implementing the compareTo method to sort based on age
    @Override
    public int compareTo(Person other) {
        // Sorting by age in ascending order
        return this.age - other.age;
    }

    @Override
    public String toString() {
        return "Person{name='" + name + "', age=" + age + '}';
    }
}

public class ComparableExample {
    public static void main(String[] args) {
        List<Person> people = Arrays.asList(
            new Person("John", 25),
            new Person("Alice", 30),
            new Person("Bob", 20)
        );

        // Sorting using Comparable (based on age)
        Collections.sort(people);
        people.forEach(System.out::println);  // The list will be sorted by age
    }
}
```

#### **Output:**

```
Person{name='Bob', age=20}
Person{name='John', age=25}
Person{name='Alice', age=30}
```

In this example, the `compareTo()` method compares `Person` objects by their age. The `Collections.sort()` method sorts the list based on the natural ordering defined by `compareTo()`.

---

### **2. Comparator Interface**

The **Comparator** interface is used to define custom sorting logic. It can be used when we want to sort objects in multiple ways (for example, sorting a list of people first by name and then by age).

#### **Key Points**

* The **Comparator** interface is part of the **java.util** package.
* It has two key methods:

    * **int compare(T o1, T o2)**: Compares two objects.
    * **boolean equals(Object obj)**: (Optional) Determines whether two comparators are equal.
* **Comparator** can be used to sort objects in a way that is not necessarily the natural order (defined by **Comparable**).

#### **Example of Comparator**

Let's say we have a **Person** class, and we want to sort people by name or age. Here, we'll use a **Comparator** to sort by name.

```java
import java.util.*;

class Person {
    String name;
    int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public String toString() {
        return "Person{name='" + name + "', age=" + age + '}';
    }
}

class NameComparator implements Comparator<Person> {
    @Override
    public int compare(Person p1, Person p2) {
        return p1.name.compareTo(p2.name);  // Compare by name
    }
}

class AgeComparator implements Comparator<Person> {
    @Override
    public int compare(Person p1, Person p2) {
        return Integer.compare(p1.age, p2.age);  // Compare by age
    }
}

public class ComparatorExample {
    public static void main(String[] args) {
        List<Person> people = Arrays.asList(
            new Person("John", 25),
            new Person("Alice", 30),
            new Person("Bob", 20)
        );

        // Sorting by name
        Collections.sort(people, new NameComparator());
        System.out.println("Sorted by name:");
        people.forEach(System.out::println);

        // Sorting by age
        Collections.sort(people, new AgeComparator());
        System.out.println("\nSorted by age:");
        people.forEach(System.out::println);
    }
}
```

#### **Output:**

```
Sorted by name:
Person{name='Alice', age=30}
Person{name='Bob', age=20}
Person{name='John', age=25}

Sorted by age:
Person{name='Bob', age=20}
Person{name='John', age=25}
Person{name='Alice', age=30}
```

Here, **NameComparator** sorts by the person's name in lexicographical order, and **AgeComparator** sorts by the person's age in ascending order.

---

### **Using Comparator with Lambda Expression**

Java 8 introduced lambda expressions, which can be used to define comparators more concisely.

#### **Example with Lambda Expression:**

You can use **lambda expressions** to sort in a more compact way.

```java
import java.util.*;

class Person {
    String name;
    int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public String toString() {
        return "Person{name='" + name + "', age=" + age + '}';
    }
}

public class ComparatorWithLambda {
    public static void main(String[] args) {
        List<Person> people = Arrays.asList(
            new Person("John", 25),
            new Person("Alice", 30),
            new Person("Bob", 20)
        );

        // Sorting by name using lambda
        people.sort((p1, p2) -> p1.name.compareTo(p2.name));
        System.out.println("Sorted by name using lambda:");
        people.forEach(System.out::println);

        // Sorting by age using lambda
        people.sort((p1, p2) -> Integer.compare(p1.age, p2.age));
        System.out.println("\nSorted by age using lambda:");
        people.forEach(System.out::println);
    }
}
```

#### **Output:**

```
Sorted by name using lambda:
Person{name='Alice', age=30}
Person{name='Bob', age=20}
Person{name='John', age=25}

Sorted by age using lambda:
Person{name='Bob', age=20}
Person{name='John', age=25}
Person{name='Alice', age=30}
```

In this example, we use lambda expressions to define the sorting logic directly inside the `sort()` method.

---

### **Using Comparator in Java 8 with `Comparator` Default Methods**

Java 8 introduced several default methods in the **Comparator** interface:

1. **reversed()**: Reverses the order of the comparator.
2. **thenComparing()**: Allows for multi-level sorting (i.e., sorting first by one field, then by another if the first is equal).
3. **comparing()**: A static method to create comparators.

#### **Example with Default Methods:**

Let's say we want to sort by age first, and if two people have the same age, we want to sort them by name.

```java
import java.util.*;

class Person {
    String name;
    int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public String toString() {
        return "Person{name='" + name + "', age=" + age + '}';
    }
}

public class ComparatorWithDefaultMethods {
    public static void main(String[] args) {
        List<Person> people = Arrays.asList(
            new Person("John", 25),
            new Person("Alice", 30),
            new Person("Bob", 25),
            new Person("Charlie", 20)
        );

        // Sorting by age first, and if ages are equal, sorting by name
        people.sort(Comparator.comparingInt(Person::getAge).thenComparing(Person::getName));
        people.forEach(System.out::println);
    }
}
```

#### **Output:**

```
Person{name='Charlie', age=20}
Person{name='John', age=25}
Person{name='Bob', age=25}
Person{name='Alice', age=30}
```

Here, we used **`Comparator.comparingInt()`** to sort by age, and **`thenComparing()`** to apply secondary sorting by name.

---

### **Conclusion**

* **Comparable** is used for defining the natural order of objects, and it requires the implementation of the **compareTo()** method.
* **Comparator** allows for custom sorting logic, providing flexibility to define sorting mechanisms externally. It provides two important methods:

    * **compare()**: Used for comparing two objects.
    * **equals()**: Optional, for equality checks between comparators.
* Java 8 introduced default methods in **Comparator**, such as **reversed()**, **thenComparing()**, and **comparing()**, which make the sorting process much more streamlined and declarative.

By using **Comparable** and **Comparator**, you can sort your data in different ways, whether by natural order or using custom criteria, giving you full control over the sorting process.
