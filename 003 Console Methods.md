# Console Methods

The JavaScript `console` object provides various methods to output messages and data to the browser's console, which is invaluable for debugging and development. 

## Console Methods

### 1. `console.log()`
- **Description**: Outputs a message or data to the console.
- **Use Case**: General-purpose logging for debugging or tracking the flow of execution.
- **Browser Support**: Available in all modern browsers.
- **Additional Feature**: Supports multiple arguments and can be styled using `%c`.

#### Example:
```javascript
/*
  console.log() Example
  - Logs a simple message to the console.
  - Demonstrates styling with %c directive.
*/

console.log("Log");
console.log("Hello From %cJS %cFile", "color: red; font-size: 40px", "color: blue; font-size: 40px");
```



### 2. `console.error()`
- **Description**: Outputs an error message to the console, typically with a red icon or text to indicate an issue.
- **Use Case**: Used to log errors or exceptions for debugging purposes, making it easy to spot problems.
- **Browser Support**: Available in all modern browsers.
- **Additional Feature**: Can include a stack trace in some environments.

#### Example:
```javascript
/*
  console.error() Example
  - Logs an error message to the console.
*/

console.error("Error");
```


---

### 3. `console.table()`
- **Description**: Displays tabular data in the console, making it easier to visualize arrays or objects.
- **Use Case**: Ideal for inspecting structured data like arrays or object properties during debugging.
- **Browser Support**: Supported in most modern browsers (e.g., Chrome, Edge, Firefox).
- **Limitations**: May not render perfectly in all environments or older browsers.

#### Example:
```javascript
/*
  console.table() Example
  - Displays an array as a table in the console.
*/

console.table(["Osama", "Ahmed", "Sayed"]);
```


## Web API
- The `console` object is part of the Web API, a set of browser-provided interfaces that extend JavaScript's capabilities. These methods interact with the browser's developer tools, providing a bridge between JavaScript code and the browser environment.

## Styling Console
- **Directive `%c`**: Allows styling of console output using CSS-like syntax. Each `%c` in the string corresponds to a CSS style passed as a subsequent argument.
- **Use Case**: Enhances readability or highlights important messages in the console.
- **Example**: See the `console.log()` example above with styled text.

