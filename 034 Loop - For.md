
## Loop - For

### What It Is
- Syntax: `for ([1] [2] [3]) { ... }`
  - **[1] Initialization**: Sets a starting point (e.g., `let i = 0`).
  - **[2] Condition**: Runs the loop as long as this is true (e.g., `i < 10`).
  - **[3] Update**: Changes the counter each iteration (e.g., `i++`).
- What it does: Repeats the code block until the condition fails.

#### Example:
```javascript
/*
  For Loop Example
  - Counting from 0 to 9.
*/

for (let i = 0; i < 10; i++) {
  console.log(i)
}
// Output: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9
```

#### What Happens:
- **Initialization**: `let i = 0` sets the starting value.
- **Condition**: `i < 10` checks if `i` is less than 10—loops while true.
- **Update**: `i++` increments `i` by 1 each time.
- **Block**: `console.log(i)` prints the current value, running 10 times (0 through 9).

---


- **Variables**: Use `let` inside the `for` to keep `i` scoped to the loop—avoids conflicts.
- **Step Size**: Change `i++` to `i += 2` for skipping numbers (e.g., 0, 2, 4...).
- **Reverse**: Start with `i = 9` and `i >= 0` with `i--` for countdown.
- **Break**: Add `break` inside to stop early if needed.
