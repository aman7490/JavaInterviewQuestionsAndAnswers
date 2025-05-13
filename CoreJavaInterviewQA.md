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

---
