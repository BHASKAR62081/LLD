# SOLID Principles (Object-Oriented Design)

SOLID is a set of five object-oriented design principles introduced by **Robert C. Martin (Uncle Bob)**.  
These principles help developers build software that is maintainable, scalable, flexible, and easy to understand.

SOLID is widely used in enterprise applications and is frequently asked in technical interviews.

---

## 1️⃣ Single Responsibility Principle (SRP)

### Definition

A class should have only **one reason to change**, meaning it should have only one responsibility.

### Explanation

If a class handles multiple responsibilities, changes in one functionality may affect others. This increases coupling and makes the code harder to maintain.

### Benefits

- Easier testing
- Better readability
- Reduced side effects
- Improved maintainability

### Example (Conceptual)

Instead of:

- `UserService` handling user logic, database operations, and email sending

Use separate classes:

- `UserService` → Business logic
- `UserRepository` → Database operations
- `UserEmailService` → Email notifications

Each class focuses on a single responsibility.

---

## 2️⃣ Open/Closed Principle (OCP)

### Definition

Software entities should be **open for extension but closed for modification**.

### Explanation

You should be able to add new functionality without modifying existing code.  
This prevents breaking already tested and stable components.

### How to Achieve

- Interfaces
- Abstraction
- Inheritance
- Polymorphism

### Example (Conceptual)

Instead of modifying a `PaymentProcessor` every time a new payment method is added:

Create a `Payment` interface and implement:

- `CreditCardPayment`
- `UPIPayment`
- `NetBankingPayment`

New payment methods can be added without changing existing code.

---

## 3️⃣ Liskov Substitution Principle (LSP)

### Definition

Objects of a subclass should be replaceable with objects of the superclass without affecting program correctness.

### Explanation

If class B extends class A, then B should behave in a way that does not break expectations set by A.

### Violation Example

If `Bird` has a `fly()` method and `Penguin` extends `Bird`, forcing penguin to fly violates LSP.

### Correct Approach

- Create a base `Bird` class
- Create a separate `Flyable` interface
- Only birds that can fly implement `Flyable`

### Benefits

- Maintains correct polymorphism
- Prevents unexpected behavior
- Improves system reliability

---

## 4️⃣ Interface Segregation Principle (ISP)

### Definition

Many Client specific interfaces are better than one general purpose interfaces means,
Clients should not be forced to depend on interfaces(or implement methods) they do not use/need.

### Explanation

Instead of creating one large interface, create multiple smaller and specific interfaces.

### Problem with Large Interfaces

- Classes implement unused methods
- Leads to empty or dummy implementations
- Increases unnecessary coupling

### Correct Design

Instead of:

- `Worker` → work(), eat(), sleep()

Create:

- `Workable` → work()
- `Eatable` → eat()
- `Sleepable` → sleep()

Now:

- Human implements all
- Robot implements only `Workable`

### Benefits

- Cleaner design
- Better flexibility
- Reduced unnecessary code

---

## 5️⃣ Dependency Inversion Principle (DIP)

### Definition

High-level modules should not depend on low-level modules but rather both should depend on abstractions.

Abstractions should not depend on details.  
Details should depend on abstractions.

### Explanation

Instead of directly creating objects inside a class, depend on interfaces and inject dependencies.

### Why It Matters

- Reduces tight coupling
- Improves testability (mocking)
- Makes system flexible

### Example (Conceptual)

Instead of:

- `OrderService` directly creating `MySQLDatabase`

Use:

- `Database` interface
- `MySQLDatabase` implements `Database` AND `MongoDatabase` implements `Database`

Inject the required implementation into `OrderService`.
This makes switching databases easy without modifying OrderService.

---

# 📌 Summary Table

| Principle | Core Idea                         | Main Benefit           |
| --------- | --------------------------------- | ---------------------- |
| SRP       | One class → one responsibility    | Easier maintenance     |
| OCP       | Extend without modifying          | Safer feature addition |
| LSP       | Subclass must behave like parent  | Reliable polymorphism  |
| ISP       | Many small interfaces > one large | Clean architecture     |
| DIP       | Depend on abstractions            | Loose coupling         |

---

| ghj | hjkl        | jgu        |
| --- | ----------- | ---------- |
| jk  | gvhjvjhvjjb | jnhvhvhjvv |
| kuk | mmhbjmbj    | hjvjhvhjv  |

# 🎯 Why SOLID is Important

- Encourages clean architecture
- Makes systems scalable
- Improves maintainability
- Reduces bugs
- Essential for enterprise applications
- Frequently asked in interviews

---

## Quick Revision (1-Line Each)

- **SRP** → One class, one job
- **OCP** → Extend behavior without modifying code
- **LSP** → Subclasses must not break parent behavior
- **ISP** → Do not force unused methods
- **DIP** → Depend on interfaces, not concrete classes

---

✅ These principles form the foundation of good object-oriented design.
