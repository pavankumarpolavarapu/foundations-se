# ☕ The Ultimate Java Developer's Handbook

## 1. The Absolute Basics
- **Structure**: `public class FileName { public static void main(String[] args) { ... } }`
- **Execution**: `javac FileName.java` -> `java FileName`
- **Output**: `System.out.println("Message");`

## 2. Variables & Data Types
- **Static Typing**: Must declare type first (e.g., `int age = 25;`).
- **Primitives**: `int`, `double`, `boolean`, `char`.
- **String**: Special object for text. Use `.equals()` for comparison.
- **Operators**: `+`, `-`, `*`, `/`, `%` (math), `==`, `!=`, `>`, `<` (relational), `&&`, `||`, `!` (logical).

## 3. Controlling the Flow
- **Conditionals**: `if-else if-else` and `switch`.
- **Loops**:
  - `for (int i=0; i<5; i++) { ... }` (standard)
  - `while (condition) { ... }` (condition-based)
  - `for (String item : collection) { ... }` (enhanced for-each)

## 4. Object-Oriented Programming (OOP)
- **Class**: The blueprint (`class Car { ... }`).
- **Object**: The instance (`Car myCar = new Car();`).
- **Encapsulation**: `private` fields + `public` getters/setters.
- **Inheritance**: `class Manager extends Employee { ... }`.
- **Polymorphism**: `@Override` a parent's method for different child behavior.
- **Abstraction**: `abstract class` (template) or `interface` (pure contract).

## 5. Arrays & Collections
- **Arrays**: Fixed-size (`int[] nums = new int[10];`).
- **Collections Framework**: Dynamic-size data structures.
  - **`List` / `ArrayList`**: Ordered, allows duplicates. `.add()`, `.get()`, `.remove()`, `.size()`.
  - **`Map` / `HashMap`**: Key-value pairs. `.put(key, val)`, `.get(key)`, `.containsKey()`.

## 6. Real-World Essentials
- **Exception Handling**:
  - **`try`**: Code that might fail.
  - **`catch (ExceptionType e)`**: Code to run on failure.
  - **`finally`**: Code that always runs.
- **File I/O**: `List<String> lines = Files.readAllLines(Paths.get("file.txt"));`

## 7. Modern Java (Java 8+)
- **Lambda Expressions**: Concise anonymous functions.
  - **Syntax**: `(parameter) -> { body }` or `() -> expression`
- **Stream API**: Declarative processing of collections.
  - **Pipeline**: `source.stream().filter().map().collect()`