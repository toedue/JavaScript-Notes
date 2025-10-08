## DOM - Create Elements

### 1. createElement
- **What it does**: Creates a new HTML element specified by its tag name (e.g., `"div"`, `"p"`).
- **Use it**: To dynamically add new elements to the DOM.

### 2. createComment
- **What it does**: Creates a comment node that can be inserted into the DOM.
- **Use it**: To add explanatory notes within the DOM structure (visible in DevTools but not on the page).

### 3. createTextNode
- **What it does**: Creates a text node with the specified string.
- **Use it**: To add plain text content to an element.

### 4. createAttribute
- **What it does**: Creates a new attribute node with a specified name.
- **Use it**: To define custom or standard attributes before attaching them.

### 5. appendChild
- **What it does**: Adds a node as the last child of the specified parent node.
- **Use it**: To insert created elements, text, or comments into the DOM.

#### Example:
- We’ll create a `<div>` with attributes, text, and a comment, then append it to the body.

#### Code:
```javascript
/*
  DOM Create Elements Example
  - Creating and appending a div with text, comment, and attributes.
*/

let myElement = document.createElement("div");
let myAttr = document.createAttribute("data-custom");
let myText = document.createTextNode("Product One");
let myComment = document.createComment("This Is Div");

myElement.className = "product";
myElement.setAttributeNode(myAttr);
myElement.setAttribute("data-test", "Testing");

// Append Comment To Element
myElement.appendChild(myComment);

// Append Text To Element
myElement.appendChild(myText);

// Append Element To Body
document.body.appendChild(myElement);
```

#### What Happens:
- **Element Creation**:
  - `myElement = document.createElement("div")` creates a new `<div>` element.
- **Attribute Creation**:
  - `myAttr = document.createAttribute("data-custom")` creates an attribute node.
  - `myElement.setAttributeNode(myAttr)` attaches it (value defaults to `""` unless set).
  - `myElement.setAttribute("data-test", "Testing")` adds another attribute.
  - `myElement.className = "product"` sets the `class` attribute directly.
- **Content Creation**:
  - `myComment = document.createComment("This Is Div")` creates a comment.
  - `myText = document.createTextNode("Product One")` creates a text node.
- **Appending**:
  - `myElement.appendChild(myComment)` adds the comment as the first child.
  - `myElement.appendChild(myText)` adds the text after the comment.
  - `document.body.appendChild(myElement)` inserts the `<div>` into the `<body>`.

#### Resulting DOM Structure:
```html
<body>
  <div class="product" data-custom="" data-test="Testing">
    <!--This Is Div-->
    Product One
  </div>
</body>
```

#### Notes:
- The `data-custom` attribute has no value (empty string) because `createAttribute` doesn’t set a default value unless modified (e.g., `myAttr.value = "custom"`).
- Order matters: `appendChild` places nodes in the order they’re added.

---


- **Node Order**: Use `insertBefore` if you need to control position (e.g., before another child).
- **Attribute Value**: Set `myAttr.value = "custom"` before `setAttributeNode` for a value.
- **Multiple Attributes**: Mix `setAttribute` and `className` for flexibility.
- **Debug**: Use `console.log(myElement)` or inspect the page in DevTools to see the result.
