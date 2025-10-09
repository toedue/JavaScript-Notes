## DOM - Events (Validate Form Practice & Prevent Default)

### 1. Validate Form Practice
- **What it does**: Checks form inputs for validity before submission (e.g., non-empty, length constraints).
- **Use it**: To ensure user input meets requirements before processing (e.g., sending to a server).

### 2. Prevent Default
- **What it does**: The `event.preventDefault()` method stops the default action of an event (e.g., form submission, link navigation).
- **Use it**: To block browser defaults when validation fails or to handle events customly.

#### HTML (Assumed):
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge" />
  <title>Form Validation</title>
</head>
<body>
  <form>
    <input type="text" name="username" placeholder="Username" />
    <input type="number" name="age" placeholder="Age" />
    <button type="submit">Submit</button>
  </form>
  <a href="https://example.com">Link</a>
  <script src="main.js"></script>
</body>
</html>
```

#### JavaScript (main.js):
```javascript
/*
  DOM Events - Form Validation Example
  - Validate inputs and prevent default submission.
*/

let userInput = document.querySelector("[name='username']");
let ageInput = document.querySelector("[name='age']");

document.forms[0].onsubmit = function (e) {
  let userValid = false;
  let ageValid = false;

  if (userInput.value !== "" && userInput.value.length <= 10) {
    userValid = true;
  }

  if (ageInput.value !== "") {
    ageValid = true;
  }

  if (userValid === false || ageValid === false) {
    e.preventDefault();
  }
};

document.links[0].onclick = function (event) {
  console.log(event);
  event.preventDefault();
};
```

#### What Happens:
- **Form Selection**:
  - `userInput`: Selects the `<input name="username">` using `[name='username']`.
  - `ageInput`: Selects the `<input name="age">`.
  - `document.forms[0]`: Targets the first `<form>` in the document.

- **Form Validation (`onsubmit`)**:
  - The `onsubmit` event triggers when the form’s submit button is clicked.
  - **Username Check**: `userInput.value !== "" && userInput.value.length <= 10`
    - Ensures the username is not empty and ≤ 10 characters.
    - Sets `userValid = true` if valid.
  - **Age Check**: `ageInput.value !== ""`
    - Ensures the age input is not empty.
    - Sets `ageValid = true` if valid.
  - **Prevent Default**: `if (userValid === false || ageValid === false)`
    - If either input is invalid, `e.preventDefault()` stops the form from submitting (e.g., no page reload or server request).

- **Link Event (`onclick`)**:
  - `document.links[0]`: Targets the first `<a>` element.
  - Logs the `click` event object for debugging.
  - `event.preventDefault()` prevents navigation to `https://example.com`.

#### Example Scenarios:
- **Valid Input**: Username = "Osama" (≤ 10 chars), Age = "25"
  - `userValid = true`, `ageValid = true` → Form submits (default action proceeds).
- **Invalid Username**: Username = "OsamaMohamed" (> 10 chars), Age = "25"
  - `userValid = false`, `ageValid = true` → `e.preventDefault()` blocks submission.
- **Empty Age**: Username = "Ali", Age = ""
  - `userValid = true`, `ageValid = false` → `e.preventDefault()` blocks submission.
- **Link Click**: Clicking the `<a>` logs the event and stays on the page.

---

### Key Points
- **Event Object**: `e` (or `event`) contains details like `target`, `type`, etc., useful for debugging.
- **preventDefault**: Must be called explicitly to stop default behavior (e.g., form submission, link navigation).
- **Validation Logic**: Combine conditions to enforce rules—use `&&` or `||` for complex checks.
- **Dynamic**: Selectors like `[name='username']` make the code reusable.

---


- **Feedback**: Add UI feedback (e.g., `userInput.style.border = "2px solid red"`) for invalid inputs.
- **addEventListener**: Use `addEventListener("submit", ...)` for multiple handlers instead of `onsubmit`.
- **Error Handling**: Check `ageInput.value` for valid numbers (e.g., `isNaN(ageInput.value)`).
- **Debug**: Log `userInput.value` or `e.target` to inspect inputs.

