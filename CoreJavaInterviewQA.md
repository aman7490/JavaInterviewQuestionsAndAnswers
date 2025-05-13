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
