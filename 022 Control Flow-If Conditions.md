
## Control Flow

### What It Is
- Control flow lets you run different blocks of code based on conditions. Think of it as “if this happens, do that” logic.
- Structure: `if` checks a condition, `else if` adds more options, and `else` catches everything else.

#### Syntax:
```javascript
if (Condition) {
  // Block of code if true
} else if (AnotherCondition) {
  // Block of code if that’s true
} else {
  // Block of code if nothing else is true
}
```

---

### Example
- We’ve got a price, a discount flag, a discount amount, and a country. Let’s adjust the price based on conditions!

#### Code:
```javascript
/*
  Control Flow Example
  - Adjusting price based on discount and country.
*/

let price = 100
let discount = true
let discountAmount = 30
let country = "KSA"

if (discount === true) {
  price -= discountAmount // price = price - discountAmount
} else if (country === "Egypt") {
  price -= 40
} else if (country === "Syria") {
  price -= 50
} else {
  price -= 10
}

console.log(price) // 70
```

#### What Happens:
- `discount === true` is true, so it subtracts `discountAmount` (30) from `price` (100).
- Result: `price` becomes 70.
- The `else if` and `else` blocks don’t run since the first condition was met.

---


- **Conditions**: Use `===` for strict checks (value + type) to avoid surprises.
- **Order matters**: Put the most likely condition first for efficiency.
- **Blocks**: Always use `{}` for clarity, even for one line.
- **Else**: Optional, use it for a fallback.

