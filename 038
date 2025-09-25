## Loop - While

### What It Is
- Syntax: `while (condition) { ... }`
- What it does: Runs the code block repeatedly as long as the condition is `true`. You must manually update the loop variable to avoid infinite loops.
- Use it: Perfect for scenarios where the number of iterations isn’t fixed upfront.

#### Example:
- We’ve got a list of products, and we’ll loop through them using a `while` loop.

#### Code:
```javascript
/*
  While Loop Example
  - Looping through products array.
*/

let products = ["Keyboard", "Mouse", "Pen", "Pad", "Monitor", "iPhone"]
let index = 0

while (index < products.length) {
  console.log(products[index])
  index += 1
}
// Output:
// Keyboard
// Mouse
// Pen
// Pad
// Monitor
// iPhone
```

#### What Happens:
- **Initialization**: `let index = 0` sets the starting point.
- **Condition**: `index < products.length` (6) checks if `index` is less than 6—loops while true.
- **Block**: `console.log(products[index])` prints the current product.
- **Update**: `index += 1` increments `index` to move to the next item.
- **Result**: Prints each product from index 0 to 5.

---


- **Manual Update**: Always increment or change `index` inside the loop, or it’ll run forever!
- **Condition**: Keep it simple—`index < length` is a common pattern.
- **Break**: Add `break` if you need to exit early based on a condition.
- **Infinite Loop**: Use `while (true)` with a `break` if you want controlled repetition.
