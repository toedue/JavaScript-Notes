## Function this Keyword

### 1. this Introduction
- **What It Is**: `this` is a special keyword that refers to the context in which a function is executed. Its value depends on how and where the function is called.
- **Use It**: To access the current object or context (e.g., object properties or the global scope).

### 2. this Inside Object Method
- **What Happens**: When a function is called as a method of an object, `this` is set to the object the method is called on.
- **Example**: In `user.ageInDays()`, `this` points to `user`.

### 3. Global Object
- **What It Is**: In a browser, the global object is `window`. `this` in the global scope typically refers to `window` (unless in strict mode).
- **Behavior**: Global variables become properties of `window`.

### 4. Test Variables With Window And This
- **What It Is**: Variables declared without `let`, `const`, or `var` (implicit globals) are attached to `window` and accessible via `this`.

### 5. Global Context
- **What It Is**: The default context when code runs outside any function—`this` is `window` in browsers.

### 6. Function Context
- **What It Is**: The context inside a function depends on how it’s called (e.g., standalone or as a method). In a regular function, `this` is `window` (non-strict mode).

### Search: Strict Mode
- **What It Is**: In strict mode (`"use strict";`), `this` is `undefined` in a function unless explicitly set, preventing accidental global bindings. It also enforces better coding practices (e.g., no implicit globals).

#### Example:
- We’ll test `this` in various contexts, including an object method and an event handler.

#### HTML (Assumed):
```html
<button id="cl">Click Me</button>
<script src="this-example.js"></script>
```

#### JavaScript:
```javascript
/*
  this Keyword Example
  - Testing this in global, function, and object contexts.
*/

console.log(this) // window (global context)
console.log(this === window) // true (in browser)

myVar = 100 // Implicit global

console.log(window.myVar) // 100
console.log(this.myVar) // 100

function sayHello() {
  console.log(this) // window (non-strict mode)
  return this
}
sayHello()

console.log(sayHello() === window) // true

document.getElementById("cl").onclick = function () {
  console.log(this) // <button id="cl"> (event target)
}

let user = {
  age: 38,
  ageInDays: function () {
    console.log(this) // {age: 38, ageInDays: ƒ}
    return this.age * 365
  },
}

console.log(user.age) // 38
console.log(user.ageInDays()) // 13870
```

#### What Happens:
- **Global Context**:
  - `console.log(this)` logs the `window` object.
  - `console.log(this === window)` logs `true` (browser environment).

- **Implicit Global**:
  - `myVar = 100` creates a global variable, accessible via `window.myVar` and `this.myVar`, logging `100`.

- **Function Context**:
  - `sayHello()` logs `window` (non-strict mode) because it’s a regular function called in the global scope.
  - `console.log(sayHello() === window)` logs `true` since it returns `window`.

- **Event Handler Context**:
  - `document.getElementById("cl").onclick` sets `this` to the clicked element (`<button id="cl">`) when triggered.

- **Object Method Context**:
  - `user.ageInDays()` sets `this` to `user`, logging `{age: 38, ageInDays: ƒ}`.
  - Returns `this.age * 365 = 38 * 365 = 13870`.

- **Output** (Console + Browser Interaction):
  - `window` object (huge dump).
  - `true`.
  - `100`.
  - `100`.
  - `window` object.
  - `true`.
  - `<button id="cl">` (on click).
  - `38`.
  - `{age: 38, ageInDays: ƒ}`.
  - `13870`.

---

### Strict Mode Impact
- Add `"use strict";` at the top:
  ```javascript:disable-run
  "use strict"
  function sayHello() {
    console.log(this) // undefined
    return this
  }
  ```
  - `this` becomes `undefined` in non-method functions, preventing accidental global assignments.

---


- **Context Matters**: `this` depends on the call site—method calls use the object, standalone functions use global (`window` or `undefined` in strict mode).
- **Event Handlers**: `this` is the element unless changed (e.g., with `.bind()`).
- **Fixing `this`**: Use arrow functions (`() => {}`) for lexical `this`, or `.bind()` to set it.
- **Avoid Globals**: Use `let`/`const` to prevent implicit `window` properties.

```
