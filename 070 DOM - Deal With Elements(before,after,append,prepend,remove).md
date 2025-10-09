
## DOM - Deal With Elements

### 1. before [Element || String]
- **What it does**: Inserts content (elements or strings) immediately before the target element in the DOM.
- **Use it**: To add siblings before an element.

### 2. after [Element || String]
- **What it does**: Inserts content immediately after the target element.
- **Use it**: To add siblings after an element.

### 3. append [Element || String]
- **What it does**: Adds content as the last child of the target element.
- **Use it**: To insert elements or text inside the target.

### 4. prepend [Element || String]
- **What it does**: Adds content as the first child of the target element.
- **Use it**: To insert elements or text at the start of the target.

### 5. remove
- **What it does**: Removes the target element (and its children) from the DOM.
- **Use it**: To delete an element entirely.

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
  <div id="my-div">Hello Div</div>
  <script src="main.js"></script>
</body>
</html>
```

#### JavaScript (main.js):
```javascript
/*
  DOM Deal With Elements Example
  - Using before, after, append, prepend, and remove.
*/

let element = document.getElementById("my-div");
let createdP = document.createElement("p");

// element.remove(); // Commented out to demonstrate other methods
```

#### Enhanced Example:
Let’s add functionality to demonstrate all methods:
```javascript
let element = document.getElementById("my-div");
let createdP = document.createElement("p");
createdP.textContent = "New Paragraph";

// Add before the div
element.before("Before Text");
element.before(createdP);

// Add after the div
element.after("After Text");
element.after(document.createElement("span").appendChild(document.createTextNode("New Span")));

// Append inside the div
element.append(" Appended Text");
element.append(document.createElement("b").appendChild(document.createTextNode("Bold Text")));

// Prepend inside the div
element.prepend("Prepended Text ");
element.prepend(document.createElement("i").appendChild(document.createTextNode("Italic Text")));

// Remove (uncomment to test)
// element.remove();
```

#### What Happens:
- **Setup**:
  - `element`: Selects `<div id="my-div">Hello Div</div>`.
  - `createdP`: Creates a `<p>` element with `textContent = "New Paragraph"`.

- **before**:
  - `element.before("Before Text")`: Adds a text node before `<div>`.
  - `element.before(createdP)`: Places `<p>New Paragraph</p>` before `<div>`.

- **after**:
  - `element.after("After Text")`: Adds a text node after `<div>`.
  - `element.after(...)`: Creates and adds `<span>New Span</span>` after `<div>`.

- **append**:
  - `element.append(" Appended Text")`: Adds text as the last child of `<div>`.
  - `element.append(...)`: Adds `<b>Bold Text</b>` as the last child.

- **prepend**:
  - `element.prepend("Prepended Text ")`: Adds text as the first child of `<div>`.
  - `element.prepend(...)`: Adds `<i>Italic Text</i>` as the first child.

- **remove** (Commented):
  - If uncommented, `element.remove()` deletes `<div id="my-div">` and its children.

#### Resulting DOM Structure:
```html
<body>
  <p>New Paragraph</p>
  Before Text
  <div id="my-div">
    <i>Italic Text</i>
    Prepended Text 
    Hello Div
     Appended Text
    <b>Bold Text</b>
  </div>
  After Text
  <span>New Span</span>
  <script src="main.js"></script>
</body>
```

#### Visual Output:
- The page shows:
  - "New Paragraph"
  - "Before Text"
  - The `<div>` with "Italic Text Prepended Text Hello Div Appended Text Bold Text"
  - "After Text"
  - "New Span"

---

### Key Points
- **String vs Element**: Strings create text nodes; elements must be created with `createElement` or similar.
- **Positioning**: `before`/`after` affect siblings; `append`/`prepend` affect children.
- **Live DOM**: Changes update the DOM instantly.
- **Remove**: Deletes the element entirely, including its children.

---


- **Text Nodes**: Use `document.createTextNode` for explicit text control instead of strings.
- **Multiple Nodes**: `append`/`prepend`/`before`/`after` accept multiple arguments (e.g., `element.append(node1, node2)`).
- **Debug**: Inspect the DOM in DevTools to verify structure.
- **Safety**: Check if `element` exists before calling methods (e.g., `if (element) element.remove()`).

