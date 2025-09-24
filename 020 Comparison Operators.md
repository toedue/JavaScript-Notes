
## Comparison Operators

### 1. == Equal
- What it does: Checks if two values are equal, ignoring their type (does some automatic conversion).
- Note: Can be tricky because it might coerce types!

#### Example:
```javascript
/*
  == Equal Example
  - Comparing values only.
*/

console.log(10 == "10") // true (converts string to number)
console.log(-100 == "-100") // true (converts string to number)
console.log(10 != "10") // false (opposite of equal)
```

---

### 2. === Identical
- What it does: Checks if two values are equal AND the same type—no type coercion here!
- Safer: Avoids the weirdness of `==`.

#### Example:
```javascript
/*
  === Identical Example
  - Comparing value and type.
*/

console.log(10 === "10") // false (different types)
console.log(10 !== "10") // true (different types)
console.log(10 !== 10) // false (same value and type)
```

---

### 3. > Larger Than
- What it does: Sees if the left value is greater than the right.
- Straightforward: Just compares numbers (or converts if needed).

#### Example:
```javascript
/*
  > Larger Than Example
  - Checking if one number is bigger.
*/

console.log(10 > 20) // false
console.log(10 > 10) // false
```

---

### 4. >= Larger Than Or Equal
- What it does: Checks if the left value is greater than or equal to the right.
- Includes: Catches equality too!

#### Example:
```javascript
/*
  >= Larger Than Or Equal Example
  - Including equality.
*/

console.log(10 >= 10) // true
```

---

### 5. < Smaller Than
- What it does: Sees if the left value is less than the right.
- Simple: Compares directly.

#### Example:
```javascript
/*
  < Smaller Than Example
  - Checking if one number is smaller.
*/

console.log(10 < 20) // true
console.log(10 < 10) // false
```

---

### 6. <= Smaller Than Or Equal
- What it does: Checks if the left value is less than or equal to the right.
- Includes: Covers equality as well.

#### Example:
```javascript
/*
  <= Smaller Than Or Equal Example
  - Including equality.
*/

console.log(10 <= 10) // true
```

---

### Bonus: Type Comparison
- What it does: Use `===` to compare types too, like checking if two strings are the same type.

#### Example:
```javascript
/*
  Type Comparison Example
  - Comparing typeof values.
*/

console.log(typeof "Osama" === typeof "Ahmed") // true (both are strings)
```

---


- **`==` vs `===`**: Use `===` to avoid type coercion surprises—`10 == "10"` is true, but `10 === "10"` is false.
- **Order matters**: `10 > 20` is different from `20 > 10`!
- **Booleans**: Comparisons return `true` or `false`, perfect for `if` statements.
- **Test types**: `typeof` with `===` is great for debugging type issues.
