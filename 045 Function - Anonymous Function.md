
## Function - Anonymous Function

### 1. Anonymous Function
- What it is: A function defined without a name, typically assigned to a variable or passed directly.
- Syntax: `let var = function() { ... };` or `function() { ... }`.
- Use it: When you need a function for a one-off task or to pass around.

### 2. Calling Named Function vs Anonymous Function
- **Named Function**: Defined with `function name() { ... }`, called by name (e.g., `sayHello()`).
- **Anonymous Function**: Called via the variable it’s assigned to (e.g., `calculator(10, 20)`).
- Difference: Named functions can be called before declaration (hoisted), while anonymous ones depend on their variable assignment.

### 3. Argument To Other Function
- What it does: Anonymous functions can be passed as arguments to other functions (e.g., event handlers, `setTimeout`).
- Use it: To customize behavior inline.

### 4. Task Without Name
- What it is: An anonymous function can execute a task without needing a permanent name, ideal for temporary use.

### 5. SetTimeout
- What it does: Runs a function after a delay (in milliseconds). Anonymous functions are commonly used here.
- Example: Delays execution for a specified time.

#### Example:
- We’ll create an anonymous function for a calculator, compare it with a named function, and use one with `setTimeout`.

#### Code:
```javascript
/*
  Anonymous Function Example
  - Calculator, named function call, and setTimeout.
*/

// Anonymous Function
let calculator = function (num1, num2) {
  return num1 + num2;
};
console.log(calculator(10, 20)); // 30

// Named Function
function sayHello() {
  console.log("Hello Osama");
}
document.getElementById("show").onclick = sayHello; // Triggers on button click

// Anonymous Function with setTimeout
setTimeout(function () {
  console.log("Good");
}, 2000); // Logs "Good" after 2 seconds
```

#### What Happens:
- **Anonymous Function (`calculator`)**:
  - Assigned to `calculator`, called with `calculator(10, 20)`, returns `30`.
  - No name, used via the variable.
- **Named Function (`sayHello`)**:
  - Defined with a name, assigned to the `onclick` event of an element with id `"show"`.
  - Logs "Hello Osama" when the button is clicked (assuming an HTML button with `id="show"` exists).
- **SetTimeout with Anonymous Function**:
  - `function ()` is an anonymous function (it’s not accessible outside `setTimeout`).
  - Executes `console.log("Good")` after a 2000ms (2-second) delay.

---
#### HTML Assumption:
```html
<button id="show">Click Me</button>
```

---


- **Assignment**: Store anonymous functions in variables for reuse.
- **Events**: Use them for event handlers (e.g., `onclick`) to keep code inline.
- **Delay**: `setTimeout` with anonymous functions is common for delayed tasks.
- **Hoisting**: Named functions are hoisted; anonymous ones aren’t unless the variable is declared with `var` (use `let`/`const` for block scope).

