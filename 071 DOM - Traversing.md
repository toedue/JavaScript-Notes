## DOM - Traversing

### 1. nextSibling
- **What it does**: Returns the next node (element, text, or comment) after the current element in the DOM.
- **Use it**: To access any type of node following the current one.

### 2. previousSibling
- **What it does**: Returns the previous node before the current element.
- **Use it**: To access any preceding node.

### 3. nextElementSibling
- **What it does**: Returns the next element (ignores text and comments) after the current element.
- **Use it**: To specifically target the next HTML element.

### 4. previousElementSibling
- **What it does**: Returns the previous element before the current element.
- **Use it**: To target the previous HTML element.

### 5. parentElement
- **What it does**: Returns the parent element of the current element.
- **Use it**: To move up the DOM tree to the containing element.

#### HTML (Assumed):
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge" />
  <title>Learn JavaScript</title>
</head>
<body>
  <div>
    <p class="one">Paragraph One</p>
    <span class="two">Span Two</span>
    <!-- Comment -->
    <p class="three">Paragraph Three</p>
  </div>
  <script src="main.js"></script>
</body>
</html>
```

#### JavaScript (main.js):
```javascript
/*
  DOM Traversing Example
  - Navigating siblings and parent elements.
*/

let span = document.querySelector(".two");

console.log(span.parentElement);

span.onclick = function () {
  span.parentElement.remove();
};
```

#### Enhanced Example (To Show All Methods):
```javascript
let span = document.querySelector(".two");

console.log(span.nextSibling); // Comment node
console.log(span.previousSibling); // Text node or <p class="one">
console.log(span.nextElementSibling); // <p class="three">
console.log(span.previousElementSibling); // <p class="one">
console.log(span.parentElement); // <div>

span.onclick = function () {
  span.parentElement.remove(); // Removes the <div> and its children
};
```

#### What Happens:
- **Setup**:
  - `span` selects `<span class="two">Span Two</span>`.

- **parentElement**:
  - `console.log(span.parentElement)` logs the `<div>` that contains the `<span>`.

- **onclick Event**:
  - Clicking the `<span>` triggers `span.parentElement.remove()`, which deletes the entire `<div>` (and its children: `<p>`, `<span>`, comment, `<p>`).

- **Traversal (Enhanced Example)**:
  - `span.nextSibling`: Gets the next node (a comment: `<!-- Comment -->`).
  - `span.previousSibling`: Gets the previous node (a text node with whitespace or `<p class="one">` depending on formatting).
  - `span.nextElementSibling`: Gets `<p class="three">` (ignores the comment).
  - `span.previousElementSibling`: Gets `<p class="one">`.
  - `span.parentElement`: Gets the `<div>`.

#### DOM Structure:
```html
<div>
  <p class="one">Paragraph One</p>
  <span class="two">Span Two</span>
  <!-- Comment -->
  <p class="three">Paragraph Three</p>
</div>
```

#### Output (Console):
```
<div>...</div>
#comment
#text or <p class="one">Paragraph One</p>
<p class="three">Paragraph Three</p>
<p class="one">Paragraph One</p>
<div>...</div>
```

#### Behavior:
- Clicking the `<span>` removes the entire `<div>`, making the page body empty (except for `<script>`).

---

### Key Points
- **Nodes vs Elements**: `nextSibling`/`previousSibling` include text/comments; `nextElementSibling`/`previousElementSibling` only include elements.
- **Live DOM**: Traversed nodes update with DOM changes.
- **Null Cases**: If no sibling or parent exists, these properties return `null` (e.g., `document.body.nextElementSibling` is `null`).
- **Use Case**: Combine with `remove`, `append`, etc., to reorganize the DOM.

---


- **Debug**: Log `node.nodeType` (1 for elements, 3 for text, 8 for comments) to identify node types.
- **Whitespace**: Text nodes from whitespace between tags can appear in `childNodes` or `siblings`.
- **Safety**: Check if elements exist (e.g., `if (span.nextElementSibling)`) to avoid errors.
- **Chaining**: Use `span.parentElement.nextElementSibling` to navigate further.
