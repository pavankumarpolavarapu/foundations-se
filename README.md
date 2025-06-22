
# Foundations of Software Engineering

This repository is a curated collection of notes, principles, and mind maps covering the foundational concepts of software engineering. It serves as a personal knowledge base and a study guide for both new and experienced developers looking to solidify their understanding of core principles, architectural patterns, and popular technologies.

The content is organized into Markdown files (`.md`) for detailed explanations and accompanying mind map files (`-MM.md`) for quick, visual overviews using markmap.

## 📚 Table of Contents

1.  [Core Software Design Principles](#-core-software-design-principles)
2.  [Database & Data Consistency Models](#-database--data-consistency-models)
3.  [Architectural Patterns](#-architectural-patterns)
4.  [Web Fundamentals](#-web-fundamentals)
5.  [Technology & Frameworks](#-technology--frameworks)
6.  [Algorithms & Patterns](#-algorithms--patterns)

---

## 🏛️ Core Software Design Principles

These are the timeless principles that guide the creation of maintainable, scalable, and robust software.

### 001: Don't Repeat Yourself (DRY)
The DRY principle is aimed at reducing the repetition of information of all kinds. Every piece of knowledge must have a single, unambiguous, authoritative representation within a system.

- **[📄 Detailed Notes](./001-DRY.md)**
- **[🧠 Mind Map](./001-DRY-MM.md)**

### 002: SOLID
SOLID is a mnemonic acronym for five design principles intended to make software designs more understandable, flexible, and maintainable.

- **[📄 Detailed Notes](./002-SOLID.md)**
- **[🧠 Mind Map](./002-SOLID-MM.md)**

---

## 🗄️ Database & Data Consistency Models

Understanding how data is stored, retrieved, and kept consistent is critical for building reliable applications. This section covers the trade-offs between different database models.

### 003: ACID
ACID (Atomicity, Consistency, Isolation, Durability) is a set of properties of database transactions intended to guarantee data validity despite errors, power failures, and other mishaps. Primarily associated with relational (SQL) databases.

- **[📄 Detailed Notes](./003-ACID.md)**
- **[🧠 Mind Map](./003-ACID-MM.md)**

### 004: NoSQL Databases
NoSQL databases provide a mechanism for storage and retrieval of data that is modeled in means other than the tabular relations used in relational databases. They are often used in big data and real-time web applications.

- **[📄 Detailed Notes](./004-NOSQL.md)**

### 005: CAP Theorem
The CAP theorem (also known as Brewer's theorem) states that it is impossible for a distributed data store to simultaneously provide more than two out of the following three guarantees: Consistency, Availability, and Partition Tolerance.

- **[📄 Detailed Notes](./005-CAP.md)**

### 006: BASE
An alternative to ACID, the BASE (Basically Available, Soft state, Eventually consistent) model is often used by NoSQL databases. It prioritizes availability over immediate consistency.

- **[📄 Detailed Notes](./006-BASE.md)**

### Tying It All Together: CAP, ACID, and BASE
This document provides a comparative overview, explaining how the CAP Theorem dictates the trade-offs that lead to choosing between an ACID-compliant system and a BASE-compliant system.

- **[📄 Comparison Notes](./006-CAP-ACID-BASE.md)**

---

## 🏗️ Architectural Patterns

High-level strategies for structuring software applications to promote separation of concerns and maintainability.

### 007: Clean Code
A collection of principles and practices for writing code that is readable, understandable, and easy to maintain. It's about craftsmanship and professionalism in development.

- **[📄 Detailed Notes](./007-CLEAN-CODE.md)**
- **[🧠 Mind Map](./007-CLEAN-CODE-MM.md)**

### 008: Clean Architecture
An architectural pattern that separates the elements of a design into concentric circles. Its primary rule is that source code dependencies can only point inwards, making the system independent of UI, databases, and frameworks.

- **[📄 Detailed Notes](./008-CLEAN-ARCHITECTURE.md)**
- **[🧠 Mind Map](./008-CLEAN-ARCHITECTURE-MM.md)**

---

## 🌐 Web Fundamentals

The building blocks of the modern web.

### 009: HTML, CSS, and JavaScript
The core trio of technologies for building user interfaces for the web.
- **HTML (HyperText Markup Language):** The standard markup language for documents designed to be displayed in a web browser.
- **CSS (Cascading Style Sheets):** A style sheet language used for describing the presentation of a document.
- **JavaScript (JS):** A programming language that enables interactive web pages.

- **[📄 Detailed Notes](./009-HTML-JS-CSS.md)**
- **[🧠 Mind Map](./009-HTML-JS-CSS-MM.md)**

---

## 💻 Technology & Frameworks

Notes on specific programming languages and frameworks that are widely used in the industry.

### 010: Java
A high-level, class-based, object-oriented programming language that is designed to have as few implementation dependencies as possible.

- **[📄 Detailed Notes](./010-JAVA.md)**
- **[🧠 Mind Map](./010-JAVA-MM.md)**

### 011: Spring Boot
An open-source, Java-based framework used to create microservices and stand-alone, production-grade Spring applications with minimal configuration.

- **[📄 Detailed Notes](./011-SPRING-BOOT.md)**
- **[🧠 Mind Map](./011-SPRING-BOOT-MM.md)**

### 012: React
A free and open-source front-end JavaScript library for building user interfaces based on UI components.

- **[📄 Detailed Notes](./012-REACT.md)**
- **[🧠 Mind Map](./012-REACT-MM.md)**

---

## 🧩 Algorithms & Patterns

Proven solutions to commonly occurring problems within a given context in software design.

### 013: Design Patterns (DP)
This section covers classic software design patterns (e.g., Singleton, Factory, Observer) that provide reusable solutions to common problems in software design.

- **[📄 Detailed Notes](./013-DP.md)**
- **[🧠 Mind Map](./013-DP-MM.md)**

---

## How to Use This Repository

1.  **Start with the Principles:** Begin with the [Core Principles](#-core-software-design-principles) and [Architectural Patterns](#-architectural-patterns) to build a strong theoretical foundation.
2.  **Understand Data:** Move to the [Database & Data Consistency Models](#-database--data-consistency-models) to learn about the trade-offs in data management.
3.  **Explore Technologies:** Dive into the specific [Technologies & Frameworks](#-technology--frameworks) to see how these principles are applied in practice.
4.  **Review with Mind Maps:** Use the mind map (`-MM.md`) files for a quick visual review or to refresh your memory on a topic.

## Contributing

Contributions are welcome! If you find a typo, have a suggestion, or want to add more content, please feel free to open an issue or submit a pull request.
