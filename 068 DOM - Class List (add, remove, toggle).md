## DOM - Class List

### What Is classList?
- **Definition**: The `classList` property is a read-only, live `DOMTokenList` that represents an element’s CSS classes, providing methods to add, remove, or toggle classes.
- **Use it**: To dynamically modify an element’s styling without directly editing the `className` string.

### Methods and Properties
1. **length**:
   - Returns the number of classes in the element’s `classList`.
2. **contains(className)**:
   - Checks if a specific class exists, returning `true` or `false`.
3. **item(index)**:
   - Returns the class at the specified index (0-based).
4. **add(className, ...)**:
   - Adds one or more classes to the element.
5. **remove(className, ...)**:
   - Removes one or more classes from the element.
6. **toggle(className)**:
   - Toggles a class: adds it if absent, removes it if present.

#### HTML (Assumed):
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge" />
  <title>Learn JavaScript</title>
  <style>
    .show { background: lightblue; }
    .osama { color: red; }
    .test { font-weight: bold; }
    .four { font-size: 20px; }
  </style>
</head>
<body>
  <div id="my-div" class="test osama four">Hello Div</div>
  <script src="main.js"></script>
</body>
</html>
```

#### JavaScript (main.js):
```javascript
/*
  DOM Class List Example
  - Exploring classList methods and properties.
*/

let element = document.getElementById("my-div");

console.log(element.classList);
console.log(typeof element.classList);
console.log(element.classList.contains("osama"));
console.log(element.classList.contains("show"));
console.log(element.classList.item(2));

element.onclick = function () {
  element.classList.toggle("show");
};
```

#### What Happens:
- **Setup**:
  - `element` selects `<div id="my-div" class="test osama four">`.
- **classList**:
  - `console.log(element.classList)`: Logs `DOMTokenList ["test", "osama", "four"]`.
- **typeof classList**:
  - `console.log(typeof element.classList)`: Logs `"object"` (it’s a `DOMTokenList`).
- **contains**:
  - `element.classList.contains("osama")`: Returns `true` (class exists).
  - `element.classList.contains("show")`: Returns `false` (class doesn’t exist).
- **item**:
  - `element.classList.item(2)`: Returns `"four"` (third class at index 2).
  - Note: If index is out of range (e.g., `item(3)`), it returns `null`.
- **toggle**:
  - `element.onclick` toggles the `show` class:
    - Click 1: Adds `show` → `<div class="test osama four show">` (applies lightblue background).
    - Click 2: Removes `show` → `<div class="test osama four">`.

#### Output (Console):
```
DOMTokenList ["test", "osama", "four"]
"object"
true
false
"four"
```

#### Visual Effect:
- Clicking the `<div>` toggles the `show` class, changing the background to lightblue and back.

---

### Key Points
- **Live Collection**: `classList` reflects real-time changes to classes.
- **Multiple Classes**: Use `add("class1", "class2")` or `remove("class1", "class2")` for bulk operations.
- **No Duplicates**: `add` won’t add a class twice; `toggle` flips reliably.
- **Error Handling**: Invalid class names (e.g., spaces) throw errors—use valid CSS class names.

---


- **Debug**: Use `console.dir(element.classList)` to inspect properties or `element.classList.length` for class count.
- **Alternatives**: `className` replaces all classes as a string, but `classList` is safer and more precise.
- **Toggle with Force**: `toggle("class", true)` forces add; `toggle("class", false)` forces remove.
- **CSS**: Ensure classes have styles defined in CSS for visible effects.
