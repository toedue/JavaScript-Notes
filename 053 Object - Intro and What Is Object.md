
## Object
### 1. Intro and What Is Object
- **What It Is**: An object is a collection of key-value pairs, where keys (properties) can hold data (values) or functions (methods). It’s like a real-world entity with attributes and actions.
- **Use It**: To group related data and functionality (e.g., a user with a name and a greeting method).
- **Syntax**: Defined with curly braces `{}`.
  - **Properties**: `key: value` pairs (e.g., `theName: "Osama"`).
  - **Methods**: Functions attached to the object (e.g., `sayHello: function() { ... }`).

### 2. Testing Window Object
- **What It Is**: The `window` object is the global object in a browser environment, representing the browser window. It contains properties (e.g., `location`, `document`) and methods (e.g., `alert`, `setTimeout`).
- **Access**: Available globally—no need to declare it.
- **Example**: `console.log(window)` or `console.log(this)` in the global scope (in a browser, `this` is `window`).

### 3. Accessing Object
- **Dot Notation**: `object.key` (e.g., `user.theName`).
- **Bracket Notation**: `object["key"]` (e.g., `user["theName"]`—useful for dynamic keys).
- **Method Call**: `object.method()` (e.g., `user.sayHello()`).

#### Example:
- We’ll create a `user` object, access its properties and method, and test the `window` object.

#### Code:
```javascript
/*
  Object Example
  - Creating and accessing a user object.
*/

let user = {
  // Properties
  theName: "Osama",
  theAge: 38,
  // Methods
  sayHello: function () {
    return `Hello`;
  },
};

console.log(user.theName); // "Osama"
console.log(user.theAge); // 38
console.log(user.sayHello()); // "Hello"

// Testing Window Object
console.log(window); // Entire window object
console.log(this === window); // true (in browser global scope)
```

#### What Happens:
- **Object Creation**:
  - `user` has two properties (`theName`, `theAge`) and one method (`sayHello`).
- **Accessing**:
  - `user.theName` logs `"Osama"`.
  - `user.theAge` logs `38`.
  - `user.sayHello()` executes the function, logging `"Hello"`.
- **Window Object**:
  - `console.log(window)` dumps the massive `window` object (try it in the console!).
  - `console.log(this === window)` confirms `this` is `window` in the global scope (browser context).

---

### Key Points
- **Properties**: Store data (strings, numbers, etc.).
- **Methods**: Store behavior (functions).
- **Window**: A built-in object—access it to manipulate the browser (e.g., `window.alert("Hi")`).
- **Access Flexibility**: Use dot or bracket notation; brackets allow computed keys (e.g., `user["the" + "Name"]`).

---


- **Dynamic Keys**: Use `user[key]` with variables (e.g., `let key = "theName"; console.log(user[key]);`).
- **Adding Properties**: `user.newProp = "Test";` adds dynamically.
- **Method Context**: Inside `sayHello`, `this` refers to `user` (e.g., `this.theName` would be `"Osama"`).
- **Browser Only**: `window` is browser-specific; in Node.js, use `global`.

