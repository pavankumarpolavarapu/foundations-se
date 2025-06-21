### The Ultimate Java Developer's Handbook

Welcome to your definitive guide to practical Java. This document is designed to be your primary reference from foundational concepts to the modern features used in professional development every day. We will cover the *how* (syntax) and the *why* (concepts) side-by-side.

**The Java Philosophy:** Java is a statically-typed, compiled, object-oriented language built for creating robust, high-performance, and portable applications. Its motto, **"Write Once, Run Anywhere,"** is made possible by the Java Virtual Machine (JVM).

---

### **Table of Contents**

1.  **The Absolute Basics:** Your First Program
2.  **Core Building Blocks:** Variables, Data Types, and Operators
3.  **Controlling the Flow:** Logic, Conditionals, and Loops
4.  **The Heart of Java:** Object-Oriented Programming (OOP)
5.  **Working with Data:** Arrays and the Collections Framework
6.  **Real-World Essentials:** Error Handling and File I/O
7.  **Modern Java (Java 8+):** Lambdas and Streams

---

### 1. The Absolute Basics: Your First Program

All Java code must live inside a **`class`**. The execution of any Java application begins at the **`main`** method.

**Syntax & Breakdown:**

```java
// File must be named "MyFirstApplication.java"
public class MyFirstApplication { // 'public class' is a container for our program

    // This is the main method - the entry point for the JVM
    public static void main(String[] args) {
        // public: Can be called from anywhere
        // static: Belongs to the class, not an object. The JVM calls it without creating an object.
        // void: This method doesn't return any value.
        // main: The name of the method.
        // (String[] args): A parameter to receive command-line arguments.

        // Use System.out.println() to print a line to the console.
        System.out.println("Hello, Java Developer!");
    }
}
```

**How to Run It:**
1.  **Compile:** `javac MyFirstApplication.java` (This creates `MyFirstApplication.class` bytecode)
2.  **Run:** `java MyFirstApplication` (The JVM executes the bytecode)

---

### 2. Core Building Blocks: Variables, Data Types, and Operators

Java is **statically-typed**: you must declare a variable's type before using it.

#### Primitive Types (The Raw Data)
```java
// Integer Types
byte aByte = 100;       // -128 to 127
short aShort = 30000;   // -32,768 to 32,767
int anInt = 1000000;    // The standard choice for whole numbers
long aLong = 1000000000L; // Use 'L' for large numbers

// Floating-Point Types (for decimals)
float aFloat = 3.14f;   // Use 'f' for floats
double aDouble = 3.14159; // The standard choice for decimals

// Other Primitives
boolean aBoolean = true;  // or false
char aChar = 'A';         // A single character, in single quotes
```

#### The `String` Object (For Text)
`String` is a class, not a primitive, but it's a fundamental part of Java.

```java
String greeting = "Hello, ";
String name = "Alice";
String message = greeting + name; // Concatenation: "Hello, Alice"

// Useful String methods
int length = message.length(); // 13
boolean isEqual = message.equals("Hello, Alice"); // true (use .equals() for objects, not ==)
String sub = message.substring(7, 12); // "Alice"
```

#### Operators
```java
int a = 10;
int b = 3;

// Arithmetic
int sum = a + b;      // 13
int difference = a - b; // 7
int product = a * b;    // 30
int quotient = a / b;   // 3 (integer division drops remainder)
int remainder = a % b;  // 1 (modulo operator)

// Relational
boolean isGreater = a > b; // true
boolean isLessOrEqual = a <= b; // false
boolean areEqual = (a == b); // false (use == for primitives)
boolean areNotEqual = (a != b); // true

// Logical
boolean t = true;
boolean f = false;
boolean andResult = t && f; // false (AND)
boolean orResult = t || f;  // true (OR)
boolean notResult = !t;     // false (NOT)
```
---

### 3. Controlling the Flow: Logic, Conditionals, and Loops

#### `if / else if / else`
```java
int score = 75;
if (score >= 90) {
    System.out.println("Excellent!");
} else if (score >= 60) {
    System.out.println("Good job.");
} else {
    System.out.println("Please try again.");
}
```

#### `switch` Statement (for checking a single variable against multiple values)
```java
int dayOfWeek = 4;
String dayName;
switch (dayOfWeek) {
    case 1: dayName = "Monday"; break;
    case 2: dayName = "Tuesday"; break;
    // ...
    case 4: dayName = "Thursday"; break;
    // ...
    default: dayName = "Invalid day"; break;
}
```

#### Loops
```java
// The standard 'for' loop
for (int i = 0; i < 5; i++) {
    System.out.println("Count: " + i); // Prints 0 through 4
}

// The 'while' loop (runs as long as the condition is true)
int countdown = 3;
while (countdown > 0) {
    System.out.println(countdown);
    countdown--; // Decrement the counter
}
System.out.println("Blast off!");

// The enhanced 'for-each' loop (for iterating over arrays or collections)
String[] names = {"Alice", "Bob", "Charlie"};
for (String currentName : names) {
    System.out.println("Hello, " + currentName);
}
```
---

### 4. The Heart of Java: Object-Oriented Programming (OOP)

This is the most critical section for understanding professional Java.

#### Class & Object (Blueprint & Instance)
A `class` is the blueprint. An `object` is a specific instance created from that blueprint.

```java
// The Blueprint: Car.java
public class Car {
    // 1. Fields (private for Encapsulation)
    private String color;
    private int year;
    private int speed;

    // 2. Constructor (to create a new Car object)
    public Car(String color, int year) {
        this.color = color;
        this.year = year;
        this.speed = 0; // Default value
    }

    // 3. Methods (public interface)
    public void accelerate(int amount) {
        this.speed += amount;
    }

    public void brake(int amount) {
        this.speed -= amount;
    }

    // Getter methods to access private fields
    public int getSpeed() {
        return this.speed;
    }
    public String getColor() {
        return this.color;
    }
}
```

#### Inheritance (`extends`), Polymorphism (`@Override`), and Abstraction (`abstract`/`interface`)

```java
// Abstraction: An interface defines a contract
interface Playable {
    void play(); // Any class that implements Playable MUST provide a play() method
}

// Abstraction: An abstract class provides a template
abstract class MediaFile {
    protected String title; // 'protected' is visible to child classes

    public MediaFile(String title) {
        this.title = title;
    }

    public String getTitle() {
        return title;
    }
    
    // An abstract method MUST be implemented by non-abstract children
    public abstract String getMediaType();
}

// Inheritance & Polymorphism
class Music extends MediaFile implements Playable {
    private String artist;

    public Music(String title, String artist) {
        super(title); // Call the parent constructor
        this.artist = artist;
    }

    @Override // Implementing the abstract method from MediaFile
    public String getMediaType() {
        return "Music";
    }

    @Override // Implementing the method from the Playable interface
    public void play() {
        System.out.println("Playing song: " + title + " by " + artist);
    }
}
```

---

### 5. Working with Data: Arrays and the Collections Framework

#### Arrays (Fixed-Size)
```java
int[] numbers = new int[5]; // An empty array of 5 integers
numbers[0] = 10;
numbers[4] = 50;
// numbers[5] = 60; // Throws an ArrayIndexOutOfBoundsException!

String[] fruits = {"Apple", "Banana", "Orange"};
System.out.println("First fruit: " + fruits[0]);
```

#### The Collections Framework (Dynamic-Size)

`import java.util.*;` is often needed at the top of your file.

##### `List` and `ArrayList` (The Workhorse)
An ordered collection that allows duplicates.

```java
List<String> names = new ArrayList<>();
names.add("Alice");
names.add("Bob");
names.add(1, "Charlie"); // Add "Charlie" at index 1

String secondName = names.get(1); // "Charlie"
names.remove("Bob");
int listSize = names.size(); // 2

for (String name : names) {
    System.out.println(name);
}
```

##### `Map` and `HashMap` (Key-Value Pairs)
Stores data in key-value pairs. Keys must be unique.

```java
Map<String, Integer> studentScores = new HashMap<>();
studentScores.put("Alice", 95);
studentScores.put("Bob", 82);
studentScores.put("Alice", 98); // This updates the existing value for "Alice"

int alicesScore = studentScores.get("Alice"); // 98
boolean hasBob = studentScores.containsKey("Bob"); // true
studentScores.remove("Bob");

// Iterate over a map
for (Map.Entry<String, Integer> entry : studentScores.entrySet()) {
    System.out.println(entry.getKey() + ": " + entry.getValue());
}
```

---

### 6. Real-World Essentials: Error Handling and File I/O

#### Exception Handling (`try-catch-finally`)
To handle code that might fail without crashing the application.

```java
try {
    // Code that might throw an exception
    int[] myNumbers = {1, 2, 3};
    System.out.println(myNumbers[10]); // This will fail!
} catch (ArrayIndexOutOfBoundsException e) {
    // Code to run if that specific exception happens
    System.out.println("Error: That index does not exist.");
    System.out.println("Exception message: " + e.getMessage());
} finally {
    // Code that ALWAYS runs, whether there was an error or not
    System.out.println("The 'try-catch' block is finished.");
}
```

#### File I/O (Reading a File)
The modern way using `try-with-resources` which automatically closes the file.

```java
import java.nio.file.Files;
import java.nio.file.Paths;
import java.util.List;
import java.io.IOException;

public class FileReaderExample {
    public static void main(String[] args) {
        String filePath = "data.txt";
        
        try {
            List<String> allLines = Files.readAllLines(Paths.get(filePath));
            for (String line : allLines) {
                System.out.println(line);
            }
        } catch (IOException e) {
            System.out.println("Error reading file: " + e.getMessage());
        }
    }
}
```

---

### 7. Modern Java (Java 8+): Lambdas and Streams

These features revolutionized Java, making code more concise and expressive.

#### Lambda Expressions
A short block of code which takes in parameters and returns a value. They are essentially anonymous functions.

```java
// Old way: Anonymous inner class
new Thread(new Runnable() {
    @Override
    public void run() {
        System.out.println("Running in a thread!");
    }
}).start();

// New way: Lambda Expression
new Thread(() -> System.out.println("Running in a thread with a lambda!")).start();
```

#### The Stream API
A powerful way to process collections of data in a declarative way.

**The Goal:** From a list of `Car` objects, get the colors of all cars made after the year 2010, in uppercase, and put them in a new list.

```java
List<Car> cars = new ArrayList<>();
cars.add(new Car("Blue", 2012));
cars.add(new Car("Red", 2008));
cars.add(new Car("Black", 2018));
cars.add(new Car("White", 2010));

// The Stream Pipeline
List<String> modernCarColors = cars.stream() // 1. Get a stream from the list
    .filter(car -> car.getYear() > 2010)       // 2. Intermediate Op: only keep modern cars
    .map(car -> car.getColor().toUpperCase())  // 3. Intermediate Op: transform car object to uppercase color string
    .collect(Collectors.toList());             // 4. Terminal Op: collect the results into a new list

// modernCarColors will be ["BLUE", "BLACK"]
```
---