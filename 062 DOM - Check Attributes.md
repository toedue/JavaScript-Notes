## DOM - Check Attributes

### 1. Element.attributes
- **What it does**: Returns a live `NamedNodeMap` of an element’s attributes, where each attribute is a node you can access by name or index.
- **Use it**: To list all attributes of an element.
- **Note**: Includes all attributes, even custom ones (e.g., `data-*`).

### 2. Element.hasAttribute
- **What it does**: Checks if an element has a specific attribute, returning `true` or `false`.
- **Use it**: To conditionally act based on an attribute’s presence.

### 3. Element.hasAttributes
- **What it does**: Checks if an element has any attributes, returning `true` if there are any, `false` otherwise.
- **Use it**: To determine if an element has attributes at all.

### 4. Element.removeAttribute
- **What it does**: Removes a specified attribute from an element.
- **Use it**: To clean up or reset attributes.

#### Example:
- We’ll check attributes on a `<p>` element and a `<div>` based on an assumed HTML structure.

#### Code:
```javascript
/*
  DOM Check Attributes Example
  - Using attributes, hasAttribute, hasAttributes, and removeAttribute.
*/

// Assuming HTML like:
// <p id="my-para" data-src="">Paragraph</p>
// <div>Empty Div</div>

console.log(document.getElementsByTagName("p")[0].attributes);

let myP = document.getElementsByTagName("p")[0];

if (myP.hasAttribute("data-src")) {
  if (myP.getAttribute("data-src") === "") {
    myP.removeAttribute("data-src");
  } else {
    myP.setAttribute("data-src", "New Value");
  }
} else {
  console.log(`Not Found`);
}

if (myP.hasAttributes()) {
  console.log(`Has Attributes`);
}

if (document.getElementsByTagName("div")[0].hasAttributes()) {
  console.log(`Has Attributes`);
} else {
  console.log(`Div Has No Attributes`);
}
```

#### What Happens:
- **attributes**:
  - `console.log(document.getElementsByTagName("p")[0].attributes)` logs a `NamedNodeMap` with `id="my-para"` and `data-src=""`.
  - Example output: `[id="my-para", data-src=""]` (access like `myP.attributes[0].name` or `myP.attributes["data-src"].value`).

- **hasAttribute Check**:
  - `myP.hasAttribute("data-src")` returns `true` because `data-src` exists.
  - `myP.getAttribute("data-src") === ""` is `true`, so `removeAttribute("data-src")` removes it.
  - If `data-src` had a value (e.g., `"old"`), it would set `data-src="New Value"`.

- **hasAttributes**:
  - `myP.hasAttributes()` returns `true` (due to `id` after `data-src` removal).
  - `document.getElementsByTagName("div")[0].hasAttributes()` returns `false` (assuming no attributes on the `<div>`).

#### Assumed HTML:
```html
<!DOCTYPE html>
<html>
<head><title>My Page</title></head>
<body>
  <p id="my-para" data-src="">Paragraph</p>
  <div>Empty Div</div>
  <script src="dom-check-attributes.js"></script>
</body>
</html>
```

#### Output (Approximate):
```
[NamedNodeMap] {0: id="my-para", 1: data-src="", ...}
Has Attributes
Div Has No Attributes
```

---

### Key Points
- **Live Collection**: `getElementsByTagName` returns a live `HTMLCollection`, so changes affect the DOM immediately.
- **Attribute Order**: `attributes` reflects the order attributes appear in the HTML.
- **Custom Attributes**: `data-src` is a custom data attribute, accessible via `getAttribute` or `dataset.src` (e.g., `myP.dataset.src`).
- **Edge Case**: If `<div>` had attributes (e.g., `class="test"`), it would log `Has Attributes`.

---


- **Inspect**: Use `console.dir(myP.attributes)` to see all attribute details.
- **dataset**: For `data-*` attributes, `element.dataset` is a modern alternative (e.g., `myP.dataset.src`).
- **Safety**: Check `hasAttribute` before `getAttribute` to avoid `null` errors on missing attributes.
- **Debug**: Log `myP.attributes.length` to count attributes dynamically.
