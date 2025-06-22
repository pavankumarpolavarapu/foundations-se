
# 🏗️ Creational Design Patterns (How Objects Are Born)

## 1. Singleton
- **Motto**: "Ensure only one instance exists globally."
- **Analogy**: A country's central government.
- **Key Use Case**: For logging, configuration managers, or database connection pools.

## 2. Factory Method
- **Motto**: "Let subclasses decide which concrete class to create."
- **Analogy**: A pizza franchise (NY vs. Chicago stores make different pizzas).
- **Key Use Case**: When a class can't anticipate the object types it needs to create.

## 3. Abstract Factory
- **Motto**: "Create families of related objects without specifying their concrete classes."
- **Analogy**: An IKEA furniture series (Modern vs. Victorian).
- **Key Use Case**: To ensure created objects are from a compatible family (e.g., a consistent UI theme).

## 4. Builder
- **Motto**: "Construct complex objects step-by-step."
- **Analogy**: Ordering a custom Subway sandwich.
- **Key Use Case**: To avoid a "telescoping constructor" with too many parameters.

## 5. Prototype
- **Motto**: "Create new objects by cloning an existing one."
- **Analogy**: Making a copy of a key.
- **Key Use Case**: When object creation is expensive, but cloning is cheap.


# 🌉 Structural Design Patterns (How Objects Are Composed)

## 1. Adapter
- **Motto**: "Make two incompatible interfaces work together."
- **Analogy**: A travel power adapter.
- **Key Use Case**: To use a legacy or third-party class with your system.

## 2. Bridge
- **Motto**: "Decouple an abstraction from its implementation so they can vary independently."
- **Analogy**: A TV remote control and the TV device.
- **Key Use Case**: To avoid a "class explosion" when you have multiple dimensions of variation.

## 3. Composite
- **Motto**: "Treat a group of objects the same way as a single object."
- **Analogy**: A file system (files and folders).
- **Key Use Case**: To represent part-whole hierarchies (tree structures).

## 4. Decorator
- **Motto**: "Add new features to an object dynamically at runtime."
- **Analogy**: Adding toppings (milk, sugar) to a coffee.
- **Key Use Case**: A flexible alternative to subclassing for adding functionality.

## 5. Facade
- **Motto**: "Provide a simple, unified interface to a complex system."
- **Analogy**: The ignition key of a car.
- **Key Use Case**: To simplify interaction with a complex library or subsystem.

## 6. Flyweight
- **Motto**: "Share common object parts to save memory."
- **Analogy**: The characters in a word processor.
- **Key Use Case**: For applications with a massive number of objects that share state.

## 7. Proxy
- **Motto**: "Provide a placeholder to control access to an object."
- **Analogy**: A credit card (a proxy for your bank account).
- **Key Use Case**: For lazy initialization (Virtual Proxy), security (Protection Proxy), or logging.

# 🏃 Behavioral Design Patterns (How Objects Communicate & Collaborate)

## Part 1: Core Communication & Algorithms
- ### Strategy
  - **Motto**: "Swap out algorithms at runtime."
  - **Analogy**: A map app's route strategy (driving vs. walking).
- ### Observer
  - **Motto**: "Notify multiple objects automatically when state changes."
  - **Analogy**: A YouTube channel notifying subscribers.
- ### Command
  - **Motto**: "Encapsulate a request as an object."
  - **Analogy**: A restaurant order ticket.
- ### Template Method
  - **Motto**: "Define an algorithm's skeleton, letting subclasses fill in the steps."
  - **Analogy**: A standardized plan for building a house.

## Part 2: State, Traversal & Interaction
- ### Iterator
  - **Motto**: "Traverse a collection without exposing its internal structure."
  - **Analogy**: A TV remote's "next channel" button.
- ### State
  - **Motto**: "Alter an object's behavior when its state changes."
  - **Analogy**: A vending machine's different states (no coin, has coin, sold).
- ### Mediator
  - **Motto**: "Centralize complex communication between objects."
  - **Analogy**: An air traffic control tower.

## Part 3: State, Responsibility & Language
- ### Memento
  - **Motto**: "Capture and restore an object's internal state without breaking encapsulation."
  - **Analogy**: A "Save Game" or "Undo" functionality.
- ### Chain of Responsibility
  - **Motto**: "Pass a request along a chain of handlers until one handles it."
  - **Analogy**: A customer support system with different tiers.
- ### Visitor
  - **Motto**: "Add a new operation to a set of classes without changing them."
  - **Analogy**: A tax inspector visiting different types of businesses.
- ### Interpreter
  - **Motto**: "Define a grammar for a language and interpret sentences."
  - **Analogy**: A musician reading sheet music.