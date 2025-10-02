## Function - Return

### 1. Return
- What it does: Ends the function immediately and sends a value back to where it was called. If no value is specified, it returns `undefined`.
- Use it: To output results or stop execution early.

### 2. Automatic Semicolon Insertion [No Line Terminator Allowed]
- What it is: JavaScript automatically adds semicolons in certain cases, but a line break after `return` can cause issues. You can’t have a line terminator (e.g., newline) between `return` and its expression, or it’ll return `undefined`.
- Fix: Keep the expression on the same line or use parentheses.

### 3. Interrupting
- What it does: When `return` is hit, the function stops, and no further code in that function runs.
- Use it: To exit early based on a condition.

#### Example:
- We’ll generate numbers and interrupt with a `return` when we hit 15.

#### Code:
```javascript
/*
  Function with Return Example
  - Interrupting loop with return.
*/

function generate(start, end) {
  for (let i = start; i <= end; i++) {
    if (i === 15) {
      return `Interrupting`
    }
    console.log(i)
  }
}

generate(10, 20)
```

#### What Happens:
- **Loop**: Starts at 10 and checks each number up to 20.
- **Condition**: When `i === 15`, the `if` block triggers.
- **Return**: `return "Interrupting"` stops the function and returns that string.
- **Output**: 
  - Prints: `10, 11, 12, 13, 14` (stops before 15).
  - The function exits, so no further `console.log` or loop iterations occur.
- **Result**: The call to `generate(10, 20)` effectively returns `"Interrupting"`, but since it’s not stored, it’s just logged up to 14.

---

### Automatic Semicolon Insertion Caution
- Bad Example (with line break):
  ```javascript:disable-run
  function badReturn() {
    return  // Semicolon inserted here
    "value" // Ignored
  }
  console.log(badReturn()) // undefined
  ```
- Good Example (same line or grouped):
  ```javascript
  function goodReturn() {
    return "value"
  }
  console.log(goodReturn()) // "value"
  ```

---


- **Early Exit**: Use `return` to bail out when a condition is met (e.g., error checks).
- **Value**: Always return something useful—avoid leaving it implicit.
- **No Break**: After `return`, the function is done—no need for `break`.
- **Line Care**: Keep `return` expressions on the same line to avoid ASI pitfalls.

