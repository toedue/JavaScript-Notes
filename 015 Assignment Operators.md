## Assignment Operators

### What They Are
- These operators let you update a variable in one go, like adding or subtracting and assigning the result back. It’s less typing and looks clean!

#### Example:
```javascript
/*
  Assignment Operators Example
  - Stepping through different assignments.
*/

let a = 10 // Start with 10

a = a + 20 // Add 20, now a is 30
console.log(a) // 30

a = a + 70 // Add 70, now a is 100
console.log(a) // 100

a += 100 // Add 100 (same as a = a + 100), now a is 200
console.log(a) // 200

a -= 50 // Subtract 50 (same as a = a - 50), now a is 150
console.log(a) // 150

a /= 50 // Divide by 50 (same as a = a / 50), now a is 3
console.log(a) // 3
```

---

## Quick Breakdown
- **`=`**: Basic assignment, sets the value (e.g., `a = 10`).
- **`+=`**: Adds and assigns (e.g., `a += 20` is `a = a + 20`).
- **`-=`**: Subtracts and assigns (e.g., `a -= 50` is `a = a - 50`).
- **`*=`**: Multiplies and assigns (e.g., `a *= 2` is `a = a * 2`).
- **`/=`**: Divides and assigns (e.g., `a /= 50` is `a = a / 50`).
- **Others**: There’s `%=`, `**=`, etc., for modulus and exponentiation too!

