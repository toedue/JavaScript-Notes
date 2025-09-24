
## Nested If

### What It Is
- Nested `if` means putting an `if` statement inside another `if` or `else` block. It lets you check extra conditions based on the first one.
- Use it: When you need to drill down into more specific cases.

#### Example
- We’ve got a price, discount flag, discount amount, country, and student status. Let’s adjust the price with some nested logic!

#### Code:
```javascript
/*
  Nested If Example
  - Adjusting price with nested conditions.
*/

let price = 100
let discount = false
let discountAmount = 30
let country = "Egypt"
let student = true

if (discount === true) {
  price -= discountAmount
} else if (country === "Egypt") {
  if (student === true) {
    price -= discountAmount + 30
  } else {
    price -= discountAmount + 10
  }
} else {
  price -= 10
}

console.log(price) // 40
```

#### What Happens:
- `discount === true` is `false`, so it skips that.
- `country === "Egypt"` is `true`, so it moves to the nested `if`.
- Inside, `student === true` is `true`, so it subtracts `discountAmount (30) + 30` (total 60) from `price` (100).
- Result: `price` becomes 40.
- The `else` block doesn’t run since the condition was met.

---


- **Nesting**: Keep it shallow—too many levels can get messy!
- **Clarity**: Use braces `{}` and comments to show what’s happening.
- **Order**: Outer conditions filter first, inner ones refine.
- **Debug**: Log values inside nests to track the flow.
