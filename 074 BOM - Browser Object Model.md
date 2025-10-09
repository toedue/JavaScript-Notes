## BOM - Introduction

### What Is the Browser Object Model (BOM)?
- **Definition**: The BOM is a collection of objects provided by the browser to interact with the browser window and its components, beyond just the DOM (Document Object Model).
- **Key Object**: The `window` object is the top-level object representing the browser window or tab.
- **Key Points**:
  - **Window Contains Document**: The `document` object (DOM) is a property of `window` (e.g., `window.document`).
  - **Global Scope**: All global variables, functions, and objects are members of `window` (e.g., `window.alert`, `window.console`).
  - **Test**: `window.document === document` and `window.console === console` are `true`.

### What Can We Do With the Window Object?
- **Open/Close Windows**: Create or close browser windows/tabs.
- **Move/Resize Windows**: Adjust the position or size of windows.
- **Print Document**: Trigger the browser’s print dialog.
- **Timing Functions**: Run code after delays (`setTimeout`) or repeatedly (`setInterval`).
- **Control URL**: Manipulate the browser’s location (e.g., `window.location`).
- **Local Storage**: Store data persistently in the browser (e.g., `localStorage`).

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
  <h1>Welcome to BOM</h1>
  <script src="main.js"></script>
</body>
</html>
```

#### JavaScript (main.js):
```javascript
/*
  BOM Introduction Example
  - Manipulating the window object.
*/

window.document.title = "Hello JS";
```

#### Enhanced Example (Demonstrating BOM Features):
```javascript
// Change document title
window.document.title = "Hello JS";

// Test global scope
var myVar = 10;
console.log(window.myVar); // 10

// Open a new window
let newWindow = window.open("https://example.com", "_blank", "width=500,height=300");

// Close window after 2 seconds
setTimeout(() => newWindow.close(), 2000);

// Move window (if supported)
window.moveTo(100, 100);

// Resize window (if supported)
window.resizeTo(800, 600);

// Print document
// window.print();

// Run code after delay
setTimeout(() => console.log("Delayed Message"), 1000);

// Run code repeatedly
let counter = 0;
let interval = setInterval(() => {
  console.log(`Interval: ${counter++}`);
  if (counter === 3) clearInterval(interval);
}, 1000);

// Control URL
console.log(window.location.href); // Current page URL
// window.location.href = "https://google.com"; // Redirect

// Local Storage
window.localStorage.setItem("theme", "dark");
console.log(window.localStorage.getItem("theme")); // "dark"
```

#### What Happens:
- **Provided Code**:
  - `window.document.title = "Hello JS"`: Changes the browser tab’s title to "Hello JS".

- **Enhanced Example**:
  - **Global Scope**: `window.myVar` accesses the global variable `myVar`.
  - **Open Window**: `window.open("https://example.com", "_blank", "width=500,height=300")` opens a new window with specified dimensions.
  - **Close Window**: `newWindow.close()` closes it after 2 seconds.
  - **Move/Resize**: `moveTo` and `resizeTo` adjust the window (limited by modern browsers for security).
  - **Print**: `window.print()` triggers the print dialog (commented to avoid annoyance).
  - **Timing**:
    - `setTimeout`: Logs a message after 1 second.
    - `setInterval`: Logs a counter every second, stopping after 3 iterations.
  - **URL**: `window.location.href` logs the current URL; setting it redirects the page.
  - **Storage**: `localStorage.setItem` and `getItem` store and retrieve data.

#### Output (Console, Enhanced Example):
```
10
"https://your-local-server-url"
"dark"
Delayed Message
Interval: 0
Interval: 1
Interval: 2
```

#### Visual Output:
- Tab title changes to "Hello JS".
- A new window opens to `example.com` and closes after 2 seconds.
- Page may resize/move (if allowed by the browser).
- Local storage saves `"theme": "dark"`.

---

### Key Points
- **Window as Global**: `window` is implied for global objects (e.g., `document` is `window.document`).
- **Security Restrictions**: Modern browsers limit `moveTo`, `resizeTo`, and `open` for security.
- **Timing Functions**:
  - `setTimeout(callback, delay)`: Runs once.
  - `setInterval(callback, delay)`: Runs repeatedly until `clearInterval(id)`.
- **Local Storage**: Persists across sessions; use `sessionStorage` for temporary data.

---


- **Debug**: Log `window` or `window.location` to explore properties.
- **Browser Compatibility**: Test `open`, `moveTo`, etc., as some features are restricted.
- **Clear Intervals**: Always clear `setInterval` to avoid memory leaks.
- **Storage Limits**: `localStorage` is ~5-10MB; use sparingly.
