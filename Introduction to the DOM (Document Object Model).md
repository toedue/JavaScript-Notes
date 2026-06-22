# Introduction to the DOM (Document Object Model)

## What Is the DOM?

The **DOM (Document Object Model)** is a programming interface that represents an HTML document as a tree of objects.

It allows JavaScript to:

* Access HTML elements
* Modify content
* Change styles
* Create or remove elements
* Respond to user actions

In simple terms:

> **The DOM connects JavaScript to HTML.**

Without the DOM, JavaScript could not interact with web pages.

---

## How the Browser Uses HTML

When a browser loads an HTML file, it:

1. Reads the HTML code
2. Creates a DOM tree
3. Makes the tree available to JavaScript

### Example HTML

```html
<body>
  <div class="card">
    <h1>Hello</h1>
    <button>Click Me</button>
  </div>
</body>
```

### DOM Tree Representation

```text
Document
│
└── html
    │
    ├── head
    │
    └── body
        │
        └── div
            │
            ├── h1
            │
            └── button
```

Each item in the tree is called a **node**.

---

## What Is the `document` Object?

The browser provides a global object called `document`.

It represents the entire web page.

```javascript
console.log(document);
```

You can use it to access and manipulate elements.

---

## Selecting Elements

Before changing an element, you must select it.

### `querySelector()`

Selects the first matching element.

```javascript
const card = document.querySelector(".card");
```

### `querySelectorAll()`

Selects all matching elements.

```javascript
const buttons = document.querySelectorAll("button");
```

### Other Selection Methods

```javascript
document.getElementById("title");

document.getElementsByClassName("card");

document.getElementsByTagName("button");
```

---

## Changing Content

### `textContent`

Changes text inside an element.

```javascript
const heading = document.querySelector("h1");

heading.textContent = "Welcome!";
```

---

### `innerHTML`

Changes HTML content.

```javascript
const card = document.querySelector(".card");

card.innerHTML = "<h2>New Content</h2>";
```

> Be careful when using `innerHTML` with user input because it can create security risks.

---

## Changing Styles

Use the `style` property.

```javascript
const card = document.querySelector(".card");

card.style.backgroundColor = "lightblue";
card.style.padding = "20px";
```

---

## Working with Classes

### Add a Class

```javascript
card.classList.add("active");
```

### Remove a Class

```javascript
card.classList.remove("active");
```

### Toggle a Class

```javascript
card.classList.toggle("active");
```

### Check for a Class

```javascript
card.classList.contains("active");
```

---

## Handling Events

JavaScript can respond to user interactions.

Examples of events:

* Click
* Mouse movement
* Keyboard input
* Form submission

### Example

```javascript
const button = document.querySelector("button");

button.addEventListener("click", () => {
  console.log("Button clicked");
});
```

---

## Creating Elements

### Create a New Element

```javascript
const paragraph = document.createElement("p");
```

### Add Content

```javascript
paragraph.textContent = "Hello!";
```

### Add It to the Page

```javascript
document.body.appendChild(paragraph);
```

---

## Removing Elements

```javascript
const card = document.querySelector(".card");

card.remove();
```

---

## DOM Loading Issue

JavaScript cannot access elements that have not been loaded yet.

This causes errors like:

```text
Cannot read properties of null
```

### Solution 1: Use `defer`

```html
<script src="index.js" defer></script>
```

### Solution 2: Place the Script Before `</body>`

```html
<body>
  <!-- HTML content -->

  <script src="index.js"></script>
</body>
```

---

## Common DOM Properties and Methods

| Method / Property             | Purpose                       |
| ----------------------------- | ----------------------------- |
| `document.querySelector()`    | Select first matching element |
| `document.querySelectorAll()` | Select all matching elements  |
| `textContent`                 | Get or set text               |
| `innerHTML`                   | Get or set HTML               |
| `style`                       | Change CSS styles             |
| `classList`                   | Manage CSS classes            |
| `addEventListener()`          | Handle events                 |
| `createElement()`             | Create elements               |
| `appendChild()`               | Add elements                  |
| `remove()`                    | Remove elements               |

---

## Example: Complete DOM Interaction

### HTML

```html
<div class="card">
  <h1>Hello</h1>
  <button>Change Text</button>
</div>
```

### JavaScript

```javascript
const button = document.querySelector("button");
const heading = document.querySelector("h1");

button.addEventListener("click", () => {
  heading.textContent = "Welcome to the DOM!";
});
```

When the button is clicked, the heading changes.

---

## Quick Summary

```text
DOM = Document Object Model

HTML → Browser → DOM Tree → JavaScript
```

```text
document → Represents the web page

querySelector() → Select elements

addEventListener() → Respond to events

style, textContent, classList → Modify elements
```

### Main Idea

> The DOM allows JavaScript to read, change, create, and remove HTML elements dynamically.
