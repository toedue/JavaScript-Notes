## BOM - Dialog Methods

### 1. alert(Message)
- **What it does**: Displays a simple dialog box with a message and an "OK" button.
- **Parameters**: `Message` (string to display).
- **Returns**: Nothing (no response captured).
- **Use it**: To notify the user of something important without needing input.

### 2. confirm(Message)
- **What it does**: Displays a dialog with a message, "OK" and "Cancel" buttons.
- **Parameters**: `Message` (string to display).
- **Returns**: `true` (OK clicked) or `false` (Cancel clicked).
- **Use it**: To get a yes/no response from the user.

### 3. prompt(Message, Default Message)
- **What it does**: Displays a dialog with a message, a text input, and "OK"/"Cancel" buttons.
- **Parameters**:
  - `Message`: The prompt text.
  - `Default Message`: Pre-filled text in the input (optional).
- **Returns**: The user’s input as a string (or `null` if Cancel is clicked).
- **Use it**: To collect user input.

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
  <h1>BOM Dialogs</h1>
  <script src="main.js"></script>
</body>
</html>
```

#### JavaScript (main.js):
```javascript
/*
  BOM Dialogs Example
  - Using alert, confirm, and prompt.
*/

// alert("Test");
// console.log("Test");

// let confirmMsg = confirm("Are You Sure?");

// console.log(confirmMsg);

// if (confirmMsg === true) {
//   console.log("Item Deleted");
// } else {
//   console.log("Item Not Deleted");
// }

let promptMsg = prompt("Good Day To You?", "Write Day With 3 Characters");

console.log(promptMsg);
```

#### What Happens:
- **Commented Code**:
  - `alert("Test")`: Would show a dialog with "Test" and an OK button; nothing is returned.
  - `console.log("Test")`: Logs "Test" to the console.
  - `confirm("Are You Sure?")`: Would show a dialog with "Are You Sure?" and OK/Cancel buttons.
    - Stores result in `confirmMsg` (`true` for OK, `false` for Cancel).
    - Logs "Item Deleted" if `true`, "Item Not Deleted" if `false`.

- **Active Code**:
  - `prompt("Good Day To You?", "Write Day With 3 Characters")`:
    - Shows a dialog with the message "Good Day To You?" and an input field pre-filled with "Write Day With 3 Characters".
    - User can:
      - Enter text (e.g., "Mon") and click OK → `promptMsg = "Mon"`.
      - Click Cancel → `promptMsg = null`.
      - Leave it empty and click OK → `promptMsg = ""`.
  - `console.log(promptMsg)`: Logs the user’s input (e.g., `"Mon"`, `null`, or `""`).

#### Example Outputs:
- **Prompt**:
  - Input "Mon", click OK → Console: `"Mon"`
  - Click Cancel → Console: `null`
  - Clear input, click OK → Console: `""`

- **Confirm (if uncommented)**:
  - Click OK → Console: `true`, `"Item Deleted"`
  - Click Cancel → Console: `false`, `"Item Not Deleted"`

- **Alert (if uncommented)**:
  - Shows "Test" dialog; console logs `"Test"`.

---

### Key Points
- **Blocking Nature**: Dialogs (`alert`, `confirm`, `prompt`) pause script execution until the user responds.
- **Returns**:
  - `alert`: No return value.
  - `confirm`: Boolean (`true`/`false`).
  - `prompt`: String or `null`.
- **UI**: Dialogs are browser-native, so styling is limited and varies by browser.
- **Use Case**: Simple interactions; for complex UI, use custom HTML/CSS modals.

---


- **Debug**: Log `promptMsg` or `confirmMsg` to verify user input.
- **Validation**: Check `promptMsg !== null` before using its value to handle Cancel.
- **Modern Alternative**: Use `<dialog>` elements or libraries (e.g., SweetAlert) for better control and styling.
- **Error Handling**: Ensure inputs are valid (e.g., `if (promptMsg && promptMsg.length === 3)`).
