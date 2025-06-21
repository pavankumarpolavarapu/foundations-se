# 🏠 Pillar 1: HTML (The Structure / Skeleton)

## 🎯 What it is
- A markup language to describe the content and structure of a webpage.
- Defines what things *are* (a heading, an image, a list).

## 🧱 Core Concepts

- ### Tags & Elements
  - **Concept**: The building blocks of HTML.
  - **Syntax**: `<tag>Content</tag>`
  - **Examples**:
    - `<h1>`: A top-level heading.
    - `<p>`: A paragraph.
    - `<a>`: An anchor (link).
    - `<img>`: An image (self-closing).
    - `<div>`: A generic division or container.
    - `<ul>`, `<li>`: Unordered list and list item.

- ### Attributes
  - **Concept**: Extra information inside the opening tag.
  - **Syntax**: `<tag attribute="value">`
  - **Examples**:
    - `<a href="...">`: The destination URL for a link.
    - `<img src="...">`: The source file for an image.
    - `<p class="intro">`: A hook for CSS (can be used on many elements).
    - `<div id="main-content">`: A hook for JS/CSS (must be unique on the page).

- ### Document Structure
  - **`<!DOCTYPE html>`**: Declares it's an HTML5 document.
  - **`<html>`**: The root element that wraps everything.
  - **`<head>`**: Contains metadata (title, CSS links). Not visible.
  - **`<body>`**: Contains all the visible content.


# 🎨 Pillar 2: CSS (The Presentation / Style)

## 🎯 What it is
- A stylesheet language to control the visual appearance of HTML.
- Defines how things *look* (color, font, layout, spacing).

## 🖌️ Core Concepts

- ### Selectors
  - **Concept**: The "query language" to target HTML elements.
  - **Types**:
    - **Element**: `p { ... }` (targets all `<p>` tags).
    - **Class**: `.intro { ... }` (targets all elements with `class="intro"`).
    - **ID**: `#main-content { ... }` (targets the single element with `id="main-content"`).

- ### Properties & Values
  - **Concept**: The actual style rules you apply.
  - **Syntax**: `selector { property: value; }`
  - **Examples**:
    - `color: blue;`
    - `font-size: 14px;`
    - `background-color: #eee;`
    - `border: 1px solid black;`

- ### The Box Model
  - **Concept**: Every element is a rectangular box.
  - **Layers (from inside out)**:
    - **Content**: The text or image.
    - **Padding**: Transparent space inside the border.
    - **Border**: A line around the padding and content.
    - **Margin**: Transparent space outside the border.

- ### How to Link
  - **Method**: Use the `<link>` tag in the HTML `<head>`.
  - **Example**: `<link rel="stylesheet" href="style.css">`


# ⚡ Pillar 3: JavaScript (The Functionality / Interactivity)

## 🎯 What it is
- A programming language to make web pages dynamic and interactive.
- Defines how things *work* and *respond* (clicking a button, submitting a form).

## ⚙️ Core Concepts

- ### Variables & Data Types
  - **Concept**: Storing and managing data.
  - **Keywords**: `let` (can be changed), `const` (cannot be changed).
  - **Types**: String (`"hello"`), Number (`123`), Boolean (`true`/`false`).

- ### Functions
  - **Concept**: Reusable blocks of code.
  - **Syntax**: `function myFunction() { ... }`
  - **Use**: To organize code and perform actions.

- ### Events
  - **Concept**: Responding to user actions.
  - **Method**: Use `element.addEventListener('eventName', functionToRun);`
  - **Examples**:
    - `'click'`: When an element is clicked.
    - `'mouseover'`: When the mouse moves over an element.
    - `'submit'`: When a form is submitted.

- ### DOM Manipulation
  - **Concept**: Using JS to find, change, create, or delete HTML elements.
  - **Finding Elements**: `document.querySelector('.my-class');`
  - **Changing Elements**:
    - `.textContent = "New text";`
    - `.style.color = "blue";`

- ### How to Link
  - **Method**: Use the `<script>` tag.
  - **Best Practice**: Place it at the end of the `<body>`.
  - **Example**: `<script src="script.js"></script>`