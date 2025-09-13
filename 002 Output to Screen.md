# Output to Screen

JavaScript provides several methods to display output to the user or developer. These methods are essential for debugging, user interaction, and dynamically updating web pages. Below is a comprehensive explanation of the primary output methods, their use cases, and a practical example.

## Output Methods

### 1. `window.alert()`
- **Description**: Displays a modal dialog box with a specified message and an "OK" button.
- **Use Case**: Ideal for showing simple alerts or notifications to the user. It pauses script execution until the user acknowledges the alert.
- **Limitations**: Not suitable for complex output or frequent use, as it can be intrusive and block the user interface.
- **Browser Support**: Available in all modern browsers.

#### Example:
```javascript
/*
  window.alert() Example
  - Displays a popup alert to the user with a greeting.
*/

window.alert("Hello From JS File");
```

### 2. `document.write()`
- **Description**: Writes HTML expressions or JavaScript code directly to the document.
- **Use Case**: Useful for dynamically generating content on a web page during its loading phase. However, it should be used cautiously as it overwrites the entire document if called after the page has loaded.
- **Limitations**: Can cause performance issues or unintended page resets if misused. Generally avoided in production environments after the initial page load.
- **Browser Support**: Widely supported, but deprecated in favor of modern DOM manipulation methods.

#### Example:
```javascript
/*
  document.write() Example
  - Writes a styled heading directly into the HTML document.
*/

document.write("<h1>Hello <span style='color: blue;'>Page</span></h1>");
```

### 3. `console.log()`
- **Description**: Outputs a message to the browser's console, typically used for debugging purposes.
- **Use Case**: Perfect for developers to log variable values, track execution flow, or debug code without affecting the user interface.
- **Limitations**: The output is only visible in the browser's developer tools (e.g., F12 or right-click > Inspect), making it invisible to end users.
- **Browser Support**: Supported in all modern browsers with developer tools.

#### Example:
```javascript
/*
  console.log() Example
  - Logs a greeting message to the browser console.
*/

console.log("Hello From JS File");
```
