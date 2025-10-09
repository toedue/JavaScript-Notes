## DOM - Add Event Listener

### 1. addEventListener
- **What it does**: Attaches an event listener to an element, allowing you to define a callback function to run when the event occurs.
- **Syntax**: `element.addEventListener(event, callback, [options])`
  - `event`: String like `"click"`, `"mouseover"`, etc.
  - `callback`: Function to execute (or a named function reference).
  - `options`: Optional object (e.g., `{ capture: true }` for capture phase).
- **Use it**: To handle events dynamically without overwriting previous handlers.

### 2. Use Without On
- Unlike `onclick`, `onmouseover`, etc., `addEventListener` uses the event name without `"on"` (e.g., `"click"`).
- **Advantage**: Cleaner syntax and supports multiple listeners.

### 3. Attach Multiple Events
- **What it does**: Allows multiple listeners for the same event on an element, unlike `onclick` which overwrites.
- **Use it**: To run different functions for the same event.

### 4. Error Test
- **Issue**: Passing a string or invalid callback to `addEventListener` causes an error (e.g., `TypeError: not a function`).
- **Fix**: Ensure the second argument is a function.

### Search Topics
- **Capture & Bubbling**:
  - **Bubbling**: Events propagate up from the target element to ancestors (default behavior).
  - **Capture**: Events propagate down from ancestors to the target (enabled with `{ capture: true }`).
  - **Use**: Control event order or delegate events to parent elements.
- **removeEventListener**:
  - **What it does**: Removes a specific event listener.
  - **Syntax**: `element.removeEventListener(event, callback, [options])`
  - **Note**: The callback must be the same function reference used in `addEventListener`.

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
  <p>Original Paragraph</p>
  <script src="main.js"></script>
</body>
</html>
```

#### JavaScript (main.js):
```javascript
/*
  DOM Add Event Listener Example
  - Using addEventListener, event delegation, and exploring errors.
*/

let myP = document.querySelector("p");

// Commented Code (Error Cases and Overwrites)
// myP.onclick = one;
// myP.onclick = two;

// function one() {
//   console.log("Message From OnClick 1");
// }
// function two() {
//   console.log("Message From OnClick 2");
// }

// window.onload = "Osama"; // Error: String not a function

// myP.addEventListener("click", function () {
//   console.log("Message From OnClick 1 Event");
// });

// myP.addEventListener("click", one);
// myP.addEventListener("click", two);

// myP.addEventListener("click", "String"); // Error: Not a function

myP.onclick = function () {
  let newP = myP.cloneNode(true);
  newP.className = "clone";
  document.body.appendChild(newP);
};

// let cloned = document.querySelector(".clone"); // Error: null (no .clone exists yet)
// cloned.onclick = function () {
//   console.log("Iam Cloned");
// };

document.addEventListener("click", function (e) {
  if (e.target.className === "clone") {
    console.log("Iam Cloned");
  }
});
```

#### What Happens:
- **Setup**:
  - `myP`: Selects `<p>Original Paragraph</p>`.

- **Commented Code (Errors)**:
  - `myP.onclick = one; myP.onclick = two;`: Only `two` would run because `onclick` overwrites the previous handler.
  - `window.onload = "Osama";`: Throws an error (`TypeError: not a function`) because a string isn’t valid.
  - `myP.addEventListener("click", "String");`: Throws an error (`TypeError: not a function`) because the callback must be a function.
  - `let cloned = document.querySelector(".clone");`: Returns `null` because no element with `class="clone"` exists initially, causing an error on `cloned.onclick`.

- **Active Code**:
  - `myP.onclick`: When the `<p>` is clicked:
    - Clones `myP` with `cloneNode(true)` (includes text).
    - Sets `className = "clone"` on the clone.
    - Appends the clone to `<body>`.
    - Result: `<p class="clone">Original Paragraph</p>` added to `<body>`.
  - `document.addEventListener("click", ...)`:
    - Uses event delegation to listen for clicks on the `document`.
    - Checks if the clicked element (`e.target`) has `className === "clone"`.
    - Logs "Iam Cloned" when a cloned `<p>` is clicked.

#### Resulting DOM After Clicking `<p>` Once:
```html
<body>
  <p>Original Paragraph</p>
  <p class="clone">Original Paragraph</p>
  <script src="main.js"></script>
</body>
```

#### Behavior:
- Click the original `<p>` → A new `<p class="clone">` appears.
- Click the cloned `<p>` → Console logs "Iam Cloned".

---

### Capture & Bubbling
- **Bubbling (Default)**: The `click` event on `<p class="clone">` bubbles up to `document`, triggering the delegated listener.
- **Capture Example**:
  ```javascript:disable-run
  document.addEventListener("click", () => console.log("Captured"), { capture: true });
  ```
  - Runs during the capture phase (down the DOM) before bubbling.
- **Use Case**: Delegation (as shown) leverages bubbling to handle dynamically added elements.

### removeEventListener
- **Example**:
  ```javascript
  let handler = () => console.log("Clicked");
  myP.addEventListener("click", handler);
  myP.removeEventListener("click", handler); // Removes the exact handler
  ```
- **Key**: The callback must match exactly (same reference), and anonymous functions can’t be removed.

---


- **Delegation**: Use `document.addEventListener` for dynamic elements (like clones) to avoid binding to `null`.
- **Multiple Listeners**: `addEventListener` allows multiple handlers; `onclick` doesn’t.
- **Error Prevention**: Check if elements exist (`if (cloned) ...`) before binding.
- **Debug**: Log `e.target` to inspect clicked elements.

```
