## Function - Arrow Function

### 1. Regular vs Arrow [Param + No Param]
- **Regular Function**: Defined with `function` keyword, e.g., `function() {}` or `function(param) {}`.
- **Arrow Function**: Uses `=>` syntax, e.g., `() =>` or `param =>`. More compact and has a different `this` binding (we’ll skip `this` for now).
- **No Param**: Both can work without parameters.
- **With Param**: Arrow functions simplify single-parameter cases by omitting parentheses (optional for clarity).

#### Examples:
- **No Param**:
  ```javascript
  let print = function () {
    return 10;
  };
  // vs
  let print = () => 10;
  ```

- **Single Param**:
  ```javascript
  let print = function (num) {
    return num;
  };
  // vs
  let print = num => num; // Parentheses optional for one param
  ```

- **Multiple Params**:
  ```javascript
  let print = function (num1, num2) {
    return num1 + num2;
  };
  // vs
  let print = (num1, num2) => num1 + num2; // Parentheses required for multiple params
  ```

### 2. Multiple Lines
- What it does: For complex logic, use curly braces `{}` and an explicit `return` (like regular functions).
- Use it: When you need multiple statements or a block of code.

#### Example:
```javascript
let print = (num1, num2) => {
  let sum = num1 + num2;
  return `Sum is ${sum}`;
};
console.log(print(100, 50)); // "Sum is 150"
```

---


- **Conciseness**: Arrow functions shine for one-liners—use them for simple tasks.
- **Parentheses**: Required for zero or multiple params; optional for one param.
- **Braces**: Use `{}` for multiple lines, and add `return` if needed.
- **No Hoisting**: Arrow functions aren’t hoisted like named functions—declare them before use.
- **This Binding**: Arrow functions don’t have their own `this` (inherit from surrounding scope)—useful for callbacks.
