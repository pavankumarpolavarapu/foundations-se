### The 5 SOLID Principles of Object-Oriented Design

SOLID is an acronym for five principles that build on each other. They are a bit more specific than DRY and are your guide to designing good classes and modules.

Let's go through them one by one.

---

#### S - Single Responsibility Principle (SRP)

*   **What it is:** A class should have only one reason to change.
*   **In Plain English:** **A class should do one thing, and do it well.**
*   **Analogy:** Think of a Swiss Army Knife. The knife blade has one job: cutting. The screwdriver has one job: turning screws. They are bundled together, but each tool has a single responsibility. You don't want a "sporknife" that does a poor job of all three things.

**Example:** Imagine a `Report` class.

```javascript
// --- BAD: Violates SRP ---
class Report {
  constructor(title, data) {
    this.title = title;
    this.data = data;
  }

  // Responsibility 1: Formatting
  formatAsHtml() {
    return `<h1>${this.title}</h1><p>${this.data}</p>`;
  }

  // Responsibility 2: Saving to a file
  saveToFile(filename) {
    // ... logic to write this.formatAsHtml() to a file ...
  }
}
```
This `Report` class has two reasons to change: 1) if the report's format changes (e.g., you want JSON instead of HTML), or 2) if the way you save files changes.

```javascript
// --- GOOD: Follows SRP ---
class Report {
  constructor(title, data) {
    this.title = title;
    this.data = data;
  }

  // It's only job is to hold the report data
}

class ReportFormatter {
  // Its only job is to format
  static toHtml(report) {
    return `<h1>${report.title}</h1><p>${report.data}</p>`;
  }
}

class FileSaver {
  // Its only job is to save
  static save(filename, content) {
    // ... logic to write content to a file ...
  }
}
```
Now, each class has only one job. This is much cleaner and easier to manage.

---

#### O - Open/Closed Principle (OCP)

*   **What it is:** Software entities (classes, modules, functions) should be open for extension, but closed for modification.
*   **In Plain English:** **You should be able to add new features without changing existing, working code.**
*   **Analogy:** Think of a power strip. It is "closed" for modification—you can't (and shouldn't) open it up to add more outlets. But it's "open" for extension—you can plug in as many new devices as you have outlets.

**Example:** A payment processor.

```javascript
// --- BAD: Violates OCP ---
// If we want to add Bitcoin, we have to MODIFY this function.
function processPayment(paymentDetails) {
  if (paymentDetails.type === 'creditCard') {
    // process credit card
  } else if (paymentDetails.type === 'paypal') {
    // process paypal
  }
}
```

```javascript
// --- GOOD: Follows OCP ---
// We define a "contract" or an interface
class PaymentProcessor {
  process(paymentMethod) {
    paymentMethod.pay();
  }
}

// We create classes that fulfill that contract
class CreditCardPayment {
  pay() { /* ... credit card logic ... */ }
}

class PayPalPayment {
  pay() { /* ... PayPal logic ... */ }
}

// NOW, to add a new payment type, we don't touch ANY old code.
// We just add a NEW class.
class BitcoinPayment {
  pay() { /* ... Bitcoin logic ... */ }
}
```
The `PaymentProcessor` is closed to changes but open to being extended with new payment types. This is incredibly powerful for creating stable systems.

---

#### L - Liskov Substitution Principle (LSP)

*   **What it is:** Subtypes must be substitutable for their base types.
*   **In Plain English:** **If you have a `Bird` class, any subclass (like `Sparrow` or `Penguin`) should be able to do anything a `Bird` can do, without causing your program to crash.**
*   **Analogy:** The classic "If it looks like a duck, quacks like a duck, but needs batteries, you probably have a wrong abstraction." A toy duck is not a real duck, so it shouldn't be a subclass of `Duck` if your program expects all ducks to be able to fly.

**Example:** The famous Rectangle/Square problem.

```javascript
// --- BAD: Violates LSP ---
class Rectangle {
  setWidth(width) { this.width = width; }
  setHeight(height) { this.height = height; }
  getArea() { return this.width * this.height; }
}

// A square IS-A rectangle, right? Let's try to inherit.
class Square extends Rectangle {
  setWidth(width) {
    this.width = width;
    this.height = width; // A square's sides must be equal
  }
  setHeight(height) {
    this.width = height;
    this.height = height; // A square's sides must be equal
  }
}

// Some function that works with Rectangles
function useRectangle(rect) {
  rect.setWidth(5);
  rect.setHeight(4);
  // We EXPECT the area to be 20.
  console.assert(rect.getArea() === 20, "Area should be 20!");
}

const rect = new Rectangle();
const sq = new Square();

useRectangle(rect); // This works fine.
useRectangle(sq);   // This fails! The assertion breaks because area is 16.
```
The `Square` class breaks the behavior of its parent `Rectangle` class. It's not a valid substitute. The solution is often to rethink the inheritance and favor composition or different abstractions.

```javascript
// GOOD EXAMPLE - FOLLOWS LSP

// 1. Create a generic, abstract concept.
// It only promises that a shape has an area.
abstract class Shape {
  abstract getArea(): number;
}

// 2. Rectangle implements the Shape contract.
class Rectangle extends Shape {
  constructor(width, height) {
    super();
    this.width = width;
    this.height = height;
  }
  
  setWidth(width) { this.width = width; }
  setHeight(height) { this.height = height; }

  getArea() {
    return this.width * this.height;
  }
}

// 3. Square also implements the Shape contract.
// It has a different API because it has different behavior.
class Square extends Shape {
  constructor(side) {
    super();
    this.side = side;
  }
  
  setSide(side) { this.side = side; }

  getArea() {
    return this.side * this.side;
  }
}
```

---

#### I - Interface Segregation Principle (ISP)

*   **What it is:** Clients should not be forced to depend upon interfaces that they do not use.
*   **In Plain English:** **Make your interfaces small and specific. Don't create "fat" interfaces that force classes to implement methods they don't need.**
*   **Analogy:** Think of a restaurant. You don't have one giant menu with "Breakfast-Lunch-Dinner-Drinks-Dessert" on it. You have separate menus. If you're just there for a drink, you get the drink menu. You aren't forced to care about the dinner options.

**Example:** An interface for workers.

```javascript
// --- BAD: "Fat" Interface Violates ISP ---
// Not all workers can code or manage people.
interface IWorker {
  work();
  eat();
  code();
  manage();
}

class Programmer implements IWorker {
  work() { /* ... */ }
  eat() { /* ... */ }
  code() { /* ... */ }
  manage() { /* I don't manage people... do nothing? throw error? */ }
}

class Manager implements IWorker {
  work() { /* ... */ }
  eat() { /* ... */ }
  code() { /* I don't code... do nothing? */ }
  manage() { /* ... */ }
}
```

```javascript
// --- GOOD: Segregated Interfaces ---
interface IWorkable { work(); }
interface IEatable { eat(); }
interface ICodable { code(); }
interface IManageable { manage(); }

// Now you compose the interfaces you need.
class Programmer implements IWorkable, IEatable, ICodable {
  // ... implement the 3 methods ...
}

class Manager implements IWorkable, IEatable, IManageable {
  // ... implement the 3 methods ...
}
```
This is much more flexible and clean. No more empty or error-throwing methods.

---

#### D - Dependency Inversion Principle (DIP)

*   **What it is:** High-level modules should not depend on low-level modules. Both should depend on abstractions. Abstractions should not depend on details. Details should depend on abstractions.
*   **In Plain English:** **Your code should depend on interfaces or abstract classes, not on concrete implementations.**
*   **Analogy:** The wall socket. Your high-level module (a laptop) doesn't depend directly on the low-level module (the coal power plant). It depends on an abstraction: the wall socket interface. The power plant also connects to that same interface. This decouples them. You can plug your laptop into a wall powered by solar or nuclear energy without changing your laptop at all.

**Example:** A notification system.

```javascript
// --- BAD: Violates DIP ---
// The high-level Notification class depends DIRECTLY on the low-level EmailNotifier.
class EmailNotifier {
  send(message) { /* ... sends an email ... */ }
}

class Notification {
  constructor() {
    this.notifier = new EmailNotifier(); // Hard-coded dependency!
  }

  sendNotification(message) {
    this.notifier.send(message);
  }
}
```
What if you want to switch to SMS? You have to change the `Notification` class. They are tightly coupled.

```javascript
// --- GOOD: Follows DIP ---
// 1. Define the abstraction (the "wall socket")
interface INotifier {
  send(message);
}

// 2. Low-level modules depend on the abstraction
class EmailNotifier implements INotifier {
  send(message) { /* ... sends an email ... */ }
}
class SmsNotifier implements INotifier {
  send(message) { /* ... sends an SMS ... */ }
}

// 3. High-level module also depends on the abstraction
class Notification {
  // We "inject" the dependency. It can be ANY INotifier.
  constructor(notifier: INotifier) {
    this.notifier = notifier;
  }

  sendNotification(message) {
    this.notifier.send(message);
  }
}

// --- Usage ---
const emailNotifier = new EmailNotifier();
const smsNotifier = new SmsNotifier();

// We can create a Notification service that uses email...
const emailNotificationService = new Notification(emailNotifier);
emailNotificationService.sendNotification("Hello via Email!");

// ... or one that uses SMS, without changing the Notification class at all!
const smsNotificationService = new Notification(smsNotifier);
smsNotificationService.sendNotification("Hello via SMS!");
```
This makes your system incredibly flexible and much easier to test.

---