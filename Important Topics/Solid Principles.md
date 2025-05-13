The **SOLID** principles are a set of five design principles that help developers create software that is easier to maintain, scale, and understand. These principles promote good object-oriented design and help prevent issues like tight coupling and poor code readability. The acronym **SOLID** stands for:

1. **S** - **Single Responsibility Principle (SRP)**
2. **O** - **Open/Closed Principle (OCP)**
3. **L** - **Liskov Substitution Principle (LSP)**
4. **I** - **Interface Segregation Principle (ISP)**
5. **D** - **Dependency Inversion Principle (DIP)**

---

### 1. **Single Responsibility Principle (SRP)**

* **Definition**: A class should have only one reason to change, meaning it should only have one responsibility or job.
* **Explanation**: If a class has multiple responsibilities, it becomes harder to understand, maintain, and modify. Each class should only focus on one task.

**Example**:

```java
// Violating SRP
class UserManager {
    public void addUser(User user) {
        // Add user logic
    }

    public void sendEmailNotification(User user) {
        // Send email logic
    }
}

// Correct way: Separate the responsibilities
class UserManager {
    private EmailService emailService;

    public UserManager(EmailService emailService) {
        this.emailService = emailService;
    }

    public void addUser(User user) {
        // Add user logic
        emailService.sendEmail(user);
    }
}

class EmailService {
    public void sendEmail(User user) {
        // Send email logic
    }
}
```

In the correct approach, `UserManager` is only responsible for user management, while `EmailService` handles email notifications.

---

### 2. **Open/Closed Principle (OCP)**

* **Definition**: Software entities (classes, modules, functions, etc.) should be open for extension but closed for modification.
* **Explanation**: This means that you should be able to extend the functionality of a class without changing its existing code. This can be achieved by using inheritance or interfaces.

**Example**:

```java
// Violating OCP
class DiscountCalculator {
    public double calculateDiscount(Order order) {
        if (order.getType() == "VIP") {
            return order.getAmount() * 0.2;
        } else if (order.getType() == "Regular") {
            return order.getAmount() * 0.1;
        }
        return 0;
    }
}

// Correct way: Use polymorphism
interface DiscountStrategy {
    double calculateDiscount(Order order);
}

class VIPDiscountStrategy implements DiscountStrategy {
    public double calculateDiscount(Order order) {
        return order.getAmount() * 0.2;
    }
}

class RegularDiscountStrategy implements DiscountStrategy {
    public double calculateDiscount(Order order) {
        return order.getAmount() * 0.1;
    }
}

class DiscountCalculator {
    private DiscountStrategy discountStrategy;

    public DiscountCalculator(DiscountStrategy discountStrategy) {
        this.discountStrategy = discountStrategy;
    }

    public double calculateDiscount(Order order) {
        return discountStrategy.calculateDiscount(order);
    }
}
```

In the correct approach, you can add new types of discount strategies without modifying the `DiscountCalculator` class.

---

### 3. **Liskov Substitution Principle (LSP)**

* **Definition**: Objects of a superclass should be replaceable with objects of a subclass without affecting the correctness of the program.
* **Explanation**: Subclasses should extend their parent classes without changing their behavior. If a subclass modifies the behavior of a method in the parent class, it can lead to unexpected bugs or issues.

**Example**:

```java
class Bird {
    public void fly() {
        // Flying logic
    }
}

class Sparrow extends Bird {
    @Override
    public void fly() {
        // Sparrow's flying logic
    }
}

class Ostrich extends Bird {
    @Override
    public void fly() {
        // Ostriches can't fly, so this is incorrect behavior
        throw new UnsupportedOperationException("Ostriches can't fly");
    }
}
```

**Correction**: In this case, it would be better to separate the flying behavior into a separate interface that only birds that can fly will implement.

---

### 4. **Interface Segregation Principle (ISP)**

* **Definition**: No client should be forced to depend on methods it does not use.
* **Explanation**: This principle encourages the design of smaller, more specific interfaces rather than large, general-purpose ones. This helps to avoid classes implementing methods that they don’t need.

**Example**:

```java
// Violating ISP
interface Worker {
    void work();
    void eat();
}

class HumanWorker implements Worker {
    public void work() { /* Work logic */ }
    public void eat() { /* Eat logic */ }
}

class RobotWorker implements Worker {
    public void work() { /* Work logic */ }
    public void eat() {
        throw new UnsupportedOperationException("Robots don't eat");
    }
}

// Correct way: Split into two interfaces
interface Workable {
    void work();
}

interface Eatable {
    void eat();
}

class HumanWorker implements Workable, Eatable {
    public void work() { /* Work logic */ }
    public void eat() { /* Eat logic */ }
}

class RobotWorker implements Workable {
    public void work() { /* Work logic */ }
}
```

By separating `Workable` and `Eatable`, we avoid forcing `RobotWorker` to implement the `eat()` method it doesn't need.

---

### 5. **Dependency Inversion Principle (DIP)**

* **Definition**: High-level modules should not depend on low-level modules. Both should depend on abstractions. Abstractions should not depend on details. Details should depend on abstractions.
* **Explanation**: The core logic of the program should depend on abstractions (interfaces or abstract classes) instead of concrete implementations, promoting loose coupling and flexibility.

**Example**:

```java
// Violating DIP
class LightBulb {
    public void turnOn() {
        System.out.println("Light Bulb turned on");
    }

    public void turnOff() {
        System.out.println("Light Bulb turned off");
    }
}

class Switch {
    private LightBulb bulb;

    public Switch(LightBulb bulb) {
        this.bulb = bulb;
    }

    public void operate() {
        bulb.turnOn();
    }
}

// Correct way: Use abstraction
interface Switchable {
    void turnOn();
    void turnOff();
}

class LightBulb implements Switchable {
    public void turnOn() { /* Light Bulb logic */ }
    public void turnOff() { /* Light Bulb logic */ }
}

class Fan implements Switchable {
    public void turnOn() { /* Fan logic */ }
    public void turnOff() { /* Fan logic */ }
}

class Switch {
    private Switchable device;

    public Switch(Switchable device) {
        this.device = device;
    }

    public void operate() {
        device.turnOn();
    }
}
```

By depending on the `Switchable` interface instead of the concrete `LightBulb` or `Fan`, we follow DIP and can easily add new devices without modifying the `Switch` class.

---

### ✅ **Summary of SOLID Principles**:

1. **Single Responsibility Principle (SRP)**: A class should have only one reason to change.
2. **Open/Closed Principle (OCP)**: Entities should be open for extension, but closed for modification.
3. **Liskov Substitution Principle (LSP)**: Subtypes should be replaceable by their base types without affecting correctness.
4. **Interface Segregation Principle (ISP)**: Clients should not be forced to depend on methods they don’t use.
5. **Dependency Inversion Principle (DIP)**: High-level modules should depend on abstractions, not concrete classes.

---

Let me know if you'd like more examples or if you'd like to dive deeper into any specific principle!
