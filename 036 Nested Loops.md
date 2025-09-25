## Loop - Nested Loops

### What It Is
- What it does: A nested loop runs an inner loop for each iteration of the outer loop, creating a grid-like structure.
- Use it: Great for pairing items from different arrays (e.g., every product with every color).

#### Example:
- We’ve got products, colors, and models, and we’ll use nested loops to list all combinations.

#### Code:
```javascript
/*
  Nested Loops Example
  - Combining products with colors and models.
*/

let products = ["Keyboard", "Mouse", "Pen", "Pad", "Monitor"]
let colors = ["Red", "Green", "Black"]
let models = [2020, 2021]

for (let i = 0; i < products.length; i++) {
  console.log("#".repeat(15))
  console.log(`# ${products[i]}`)
  console.log("#".repeat(15))
  console.log("Colors: ")
  for (let j = 0; j < colors.length; j++) {
    console.log(`- ${colors[j]}`)
  }
  console.log("Models: ")
  for (let k = 0; k < models.length; k++) {
    console.log(`- ${models[k]}`)
  }
}
```

#### What Happens:
- **Outer Loop (`i`)**: Runs 5 times (0 to 4) for each product.
- **First Inner Loop (`j`)**: For each product, runs 3 times (0 to 2) for each color.
- **Second Inner Loop (`k`)**: For each product, runs 2 times (0 to 1) for each model.
- **Output**: For every product, it prints a header, then lists all colors and models.
- **Result**: 5 blocks, each with 15 `#`s, the product name, 3 colors, and 2 models.

#### Sample Output:
```
###############
# Keyboard
###############
Colors:
- Red
- Green
- Black
Models:
- 2020
- 2021
###############
# Mouse
###############
Colors:
- Red
- Green
- Black
Models:
- 2020
- 2021
[... and so on for Pen, Pad, Monitor]
```

---


- **Variables**: Use unique loop counters (`i`, `j`, `k`) to avoid confusion.
- **Depth**: Two or three levels are common—too many can get slow or hard to read.
- **Formatting**: `console.log("#".repeat(15))` is a neat way to add separators.
- **Performance**: Nested loops multiply iterations (e.g., 5 × 3 × 2 = 30 total loops here).

