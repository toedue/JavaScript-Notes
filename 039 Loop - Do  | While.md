## Loop - Do / While

### What It Is
- Syntax: `do { ... } while (condition)`
- What it does: Executes the code block once, then checks the condition. If true, it loops; if false, it stops.
- Key Difference: Unlike `while`, it runs at least once, even if the condition is false from the start.
- Use it: Perfect for situations where the initial execution is required.

#### Example:
- We’ve got a list of products, but we’ll use a simple counter to show how `do...while` works with a false condition.

#### Code:
```javascript
/*
  Do / While Loop Example
  - Running once despite false condition.
*/

let products = ["Keyboard", "Mouse", "Pen", "Pad", "Monitor", "iPhone"]
let i = 0

do {
  console.log(i)
  i++
} while (false)

console.log(i)
```

#### What Happens:
- **Do Block**: Runs first, logging `i` (0) and incrementing `i` to 1.
- **While Condition**: `false` is checked after the block, so the loop stops.
- **Result**: 
  - `console.log(i)` prints `0` (from the do block).
  - `console.log(i)` after the loop prints `1` (after increment).
- Output:
  ```
  0
  1
  ```

---

### Comparison to While
- If this were a `while (false)` loop, it wouldn’t run at all. `do...while` guarantees at least one pass.

#### With True Condition (For Reference):
```javascript
let j = 0
do {
  console.log(products[j])
  j++
} while (j < products.length)
// Output: Keyboard, Mouse, Pen, Pad, Monitor, iPhone
```

---


- **Guaranteed Run**: Use `do...while` when the code must execute at least once (e.g., user input validation).
- **Update**: Always increment or change the loop variable inside the `do` block.
- **Condition**: Check it carefully—`while (true)` with no `break` creates an infinite loop.
- **Debug**: Add `console.log()` inside to trace execution.
