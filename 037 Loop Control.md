## Loop Control

### 1. Break
- What it does: Exits the entire loop immediately, stopping all further iterations.
- Use it: To jump out when a condition is met.

### 2. Continue
- What it does: Skips the current iteration and moves to the next one.
- Use it: To avoid processing certain cases.

### 3. Label
- What it does: Names a loop block, allowing `break` or `continue` to target a specific loop in nested setups.
- Use it: With nested loops to control outer loops.

#### Example:
- We’ve got products and colors, and we’ll use loop control to manage the output.

#### Code:
```javascript
/*
  Loop Control Example
  - Using break with a label in nested loops.
*/

let products = ["Keyboard", "Mouse", "Pen", "Pad", "Monitor"]
let colors = ["Red", "Green", "Black"]

mainLoop: for (let i = 0; i < products.length; i++) {
  console.log(products[i])
  nestedLoop: for (let j = 0; j < colors.length; j++) {
    console.log(`- ${colors[j]}`)
    if (colors[j] === "Green") {
      break mainLoop
    }
  }
}
```

#### What Happens:
- **Outer Loop (`mainLoop`)**: Starts with `i = 0` ("Keyboard").
- **Inner Loop (`nestedLoop`)**: Runs for each color.
  - Prints `- Red`.
  - Prints `- Green` and hits the `if` condition.
- **Break**: `break mainLoop` exits the entire `mainLoop`, stopping all further iterations.
- **Result**: Only prints:
  ```
  Keyboard
  - Red
  - Green
  ```
  (It doesn’t process "Mouse" or beyond.)

---

### Notes on Other Controls
- **Continue with Label**: Could skip to the next product if, say, a color condition fails (e.g., `continue mainLoop`).
- **Break without Label**: Would only exit the inner `nestedLoop`, moving to the next product.
- **Continue**: Could skip the current color and move to the next one (e.g., `continue` inside `nestedLoop`).

#### Alternative with Continue:
```javascript
mainLoop: for (let i = 0; i < products.length; i++) {
  console.log(products[i])
  nestedLoop: for (let j = 0; j < colors.length; j++) {
    if (colors[j] === "Green") {
      continue mainLoop
    }
    console.log(`- ${colors[j]}`)
  }
}
// Output: "Keyboard", "- Red", "Mouse", "- Red", ...
// Skips "Green" and moves to next product
```

---


- **Label**: Use descriptive names (e.g., `mainLoop`) and colon `:` after.
- **Break**: Exits the labeled loop entirely—use cautiously.
- **Continue**: Jumps to the next iteration of the labeled loop—great for skipping.
- **Scope**: Labels work with nested loops; without labels, `break`/`continue` affect the innermost loop.
