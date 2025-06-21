# Clean Architecture (by Robert Martin)

## 🎯 The Goal
- To create systems that are:
  - **Independent** of Frameworks, UI, and Database.
  - **Testable** (business rules can be tested in isolation).
  - **Maintainable** and built to last.

## 🏛️ The Core Idea
- Separate software into layers (concentric circles).
- Protect the valuable business logic from the messy details.

## 📜 The Golden Rule: The Dependency Rule
- **Dependencies can ONLY point inwards.**
- `(Inner Layer) <--- (Outer Layer)`
- An inner circle must not know anything about an outer circle.

## 🧅 The Layers (from Inside-Out)

- ### 1. Entities (The Core)
  - **What**: Enterprise-wide business objects & rules (`Student`, `Order`).
  - **Key**: Highest level, most general, least likely to change.

- ### 2. Use Cases (The Actions)
  - **What**: Application-specific business rules that define what the app *does* (`EnrollStudent`, `PlaceOrder`).
  - **Key**: Orchestrates Entities to achieve a goal. Knows nothing of the DB or UI.

- ### 3. Interface Adapters (The Translators)
  - **What**: Converts data between layers.
  - **Contains**:
    - **Controllers**: Web request -> Use Case call.
    - **Presenters**: Use Case result -> UI model.
    - **Gateways/Repositories**: Implements data interfaces.

- ### 4. Frameworks & Drivers (The Details)
  - **What**: The tools and delivery mechanisms.
  - **Contains**: The UI (React, HTML), Database (PostgreSQL), Web Framework (ASP.NET), etc.
  - **Key**: The most volatile layer. Should be swappable.

## ✨ The Magic Trick: Crossing Boundaries
- **How**: The Dependency Inversion Principle (SOLID 'D').
- **Flow**:
  1. **Use Case (Inner Layer)** defines an `IRepository` interface (a contract).
  2. **Gateway (Outer Layer)** creates a concrete `PostgresRepository` class that *implements* that interface.
  3. The `PostgresRepository` is "injected" into the Use Case.
- **Result**: The Use Case talks to the interface it owns, not the concrete database class.