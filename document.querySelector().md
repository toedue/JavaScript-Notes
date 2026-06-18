# `document.querySelector()` in JavaScript

## Definition

`document.querySelector()` is a DOM method used to select the **first HTML element** that matches a specified CSS selector.

It returns the matching element as an object that JavaScript can manipulate.

---

## Syntax

```javascript
document.querySelector(selector);
```

### Parameters

| Parameter  | Description                 |
| ---------- | --------------------------- |
| `selector` | A valid CSS selector string |

### Return Value

* Returns the **first matching element**
* Returns `null` if no matching element is found

---

## Basic Syntax Examples

### Select by tag name

```html
<h1>Hello World</h1>
```

```javascript
const heading = document.querySelector("h1");
```

---

### Select by class

```html
<div class="card"></div>
```

```javascript
const card = document.querySelector(".card");
```

> Use a dot (`.`) before the class name.

---

### Select by ID

```html
<div id="profile"></div>
```

```javascript
const profile = document.querySelector("#profile");
```

> Use a hash (`#`) before the ID name.

---

## Using CSS Selectors

Since `querySelector()` accepts CSS selectors, you can use powerful selection patterns.

### Descendant selector

```html
<div class="card">
  <h2>Title</h2>
</div>
```

```javascript
const title = document.querySelector(".card h2");
```

---

### Attribute selector

```html
<input type="text">
```

```javascript
const input = document.querySelector('input[type="text"]');
```

---

### Multiple classes

```html
<button class="btn primary"></button>
```

```javascript
const button = document.querySelector(".btn.primary");
```

---

## Examples of DOM Manipulation

### Change text

```javascript
document.querySelector("h1").textContent = "Welcome!";
```

---

### Change style

```javascript
document.querySelector(".card").style.backgroundColor = "lightblue";
```

---

### Add an event listener

```javascript
document.querySelector(".card").addEventListener("click", () => {
  console.log("Clicked");
});
```

---

## Important Note: First Match Only

Given this HTML:

```html
<p>First paragraph</p>
<p>Second paragraph</p>
<p>Third paragraph</p>
```

```javascript
const paragraph = document.querySelector("p");
console.log(paragraph.textContent);
```

### Output

```text
First paragraph
```

Only the first matching element is selected.

To select all matching elements, use:

```javascript
document.querySelectorAll("p");
```

---

## Handling `null`

If no element matches the selector:

```javascript
const card = document.querySelector(".card");
```

and `.card` does not exist, `card` becomes:

```javascript
null
```

Trying to use methods on `null` causes an error:

```javascript
card.addEventListener("click", () => {});
```

### Error

```text
Cannot read properties of null
```

### Safe approach

```javascript
const card = document.querySelector(".card");

if (card) {
  card.addEventListener("click", () => {
    console.log("Clicked");
  });
}
```

---

## Common Mistakes

| Incorrect                            | Correct                              |
| ------------------------------------ | ------------------------------------ |
| `document.querySelector("card")`     | `document.querySelector(".card")`    |
| `document.querySelector("profile")`  | `document.querySelector("#profile")` |
| Using an invalid CSS selector        | Use valid CSS syntax                 |
| Accessing elements before they exist | Use `defer` or `DOMContentLoaded`    |

---

## `querySelector()` vs `getElementById()`

| Feature                  | `querySelector()` | `getElementById()` |
| ------------------------ | ----------------- | ------------------ |
| Uses CSS selectors       | ✅                 | ❌                  |
| Select by class          | ✅                 | ❌                  |
| Select by ID             | ✅                 | ✅                  |
| Select nested elements   | ✅                 | ❌                  |
| Returns first match only | ✅                 | N/A                |
| Slightly faster for IDs  | ❌                 | ✅                  |

Example:

```javascript
document.querySelector("#header");
document.getElementById("header");
```

Both select the same element.

---

## Best Practices

* Use `querySelector()` when you need flexible CSS selectors.
* Store selected elements in variables if you use them multiple times.
* Check for `null` when elements may not exist.
* Use `defer` in your script tag to ensure the DOM is loaded.

---

## Summary

```javascript
const element = document.querySelector(selector);
```

* Accepts any valid CSS selector
* Returns the first matching element
* Returns `null` if no match exists
* Useful for selecting and manipulating HTML elements dynamically
