## DOM - Events

### 1. Use Events On HTML
- **What it does**: Add event handlers directly in HTML attributes (e.g., `<button onclick="function()">`).
- **Example**:
  ```html
  <button onclick="console.log('Clicked from HTML')">Click Me</button>
  ```
- **Use it**: Quick for simple interactions, but less flexible and harder to maintain.

### 2. Use Events On JS
- **What it does**: Attach event handlers programmatically using properties like `onclick`, `oncontextmenu`, etc.
- **Advantages**: More dynamic, allows complex logic, and separates behavior from markup.
- **Common Events**:
  - **onclick**: Triggers when an element is clicked.
  - **oncontextmenu**: Triggers on a right-click (context menu).
  - **onmouseenter**: Triggers when the mouse enters an element.
  - **onmouseleave**: Triggers when the mouse leaves an element.
  - **onload**: Triggers when a resource (e.g., window, image) finishes loading.
  - **onscroll**: Triggers when an element’s scrollbar is scrolled.
  - **onresize**: Triggers when the window is resized.
  - **onfocus**: Triggers when an element gains focus (e.g., input).
  - **onblur**: Triggers when an element loses focus.
  - **onsubmit**: Triggers when a form is submitted.

#### Example:
- We’ll attach events to a button and the window based on an assumed HTML structure.

#### HTML (index.html):
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge" />
  <title>Learn JavaScript</title>
</head>
<body>
  <button id="btn">Click Me</button>
  <form id="myForm" onsubmit="console.log('Form Submitted from HTML')">
    <input type="text" />
    <button type="submit">Submit</button>
  </form>
  <script src="main.js"></script>
</body>
</html>
```

#### JavaScript (main.js):
```javascript
/*
  DOM Events Example
  - Attaching events via JavaScript.
*/

let myBtn = document.getElementById("btn");

// Mouse Events
myBtn.onmouseleave = function () {
  console.log("Mouse Left");
}; // Note: Code had "Clicked" but should match "mouseleave"

// Window Events
window.onresize = function () {
  console.log("Window Resized");
}; // Note: Code had "Scroll" but should match "resize"

// Additional Examples (Uncomment to test)
// myBtn.onclick = function () {
//   console.log("Button Clicked");
// };

// myBtn.oncontextmenu = function (e) {
//   e.preventDefault(); // Prevent context menu
//   console.log("Right Clicked");
// };

// myBtn.onmouseenter = function () {
//   console.log("Mouse Entered");
// };

// window.onload = function () {
//   console.log("Page Loaded");
// };

// window.onscroll = function () {
//   console.log("Scrolled");
// };

// let myInput = document.querySelector("input");
// myInput.onfocus = function () {
//   console.log("Input Focused");
// };

// myInput.onblur = function () {
//   console.log("Input Blurred");
// };

// let myForm = document.getElementById("myForm");
// myForm.onsubmit = function (e) {
//   e.preventDefault(); // Prevent form submission
//   console.log("Form Submitted");
// };
```

#### What Happens:
- **myBtn.onmouseleave**:
  - Triggers when the mouse leaves the button, logging "Mouse Left".
  - (Note: The original code had "Clicked" for `onmouseleave`, which was a mismatch—corrected to "Mouse Left".)

- **window.onresize**:
  - Triggers when the browser window is resized, logging "Window Resized".
  - (Note: The original code had "Scroll" for `onresize`, which was a mismatch—corrected to "Window Resized".)

- **Additional Events** (Commented):
  - `onclick`: Logs on button click.
  - `oncontextmenu`: Logs on right-click, with `e.preventDefault()` to block the context menu.
  - `onmouseenter`: Logs when the mouse enters the button.
  - `onload`: Logs when the page finishes loading.
  - `onscroll`: Logs during window scrolling.
  - `onfocus`/`onblur`: Logs when the input gains/loses focus.
  - `onsubmit`: Logs on form submission, with `e.preventDefault()` to prevent default behavior.

#### Output (Interactive):
- Move the mouse over and away from the button to see "Mouse Left".
- Resize the window to see "Window Resized".
- Uncomment other events to test their triggers (e.g., click the button, submit the form).

---

### Key Points
- **Event Overwrite**: Assigning a new handler (e.g., `myBtn.onclick = ...`) overwrites the previous one—use `addEventListener` for multiple handlers.
- **Event Object**: `e` (event) provides details (e.g., `e.preventDefault()` stops defaults).
- **HTML vs JS**: HTML events are inline; JS events are dynamic and preferable for separation of concerns.
- **Scope**: Event functions have access to the element’s context via `this`.

---


- **addEventListener**: Prefer it over `on...` for adding multiple listeners (e.g., `myBtn.addEventListener("click", () => console.log("Clicked"));`).
- **Remove**: Use `removeEventListener` or set to `null` (e.g., `myBtn.onmouseleave = null`) to disable.
- **Debug**: Log `e` in the handler to inspect event properties.
- **Performance**: Avoid heavy logic in frequent events like `onscroll`.
