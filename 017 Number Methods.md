## Number Methods

### 1. Two Dots To Call A Method
- What it does: Use two dots (`.`) after a number to call its methods, but wrap it in parentheses if it’s a plain number like `(100).toString()`.
- Tip: Works smooth with decimals or variables too!

---

### 2. toString()
- What it does: Turns a number into a string. Useful when you need text instead of a number.
- Note: Works with decimals just fine.

#### Example:
```javascript
/*
  toString Example
  - Converting numbers to strings.
*/

console.log((100).toString()) // "100"
console.log(100.10.toString()) // "100.10"
```

---

### 3. toFixed()
- What it does: Rounds a number to a set number of decimal places (e.g., 2 for cents).
- Handy: Great for money or precise outputs.

#### Example:
```javascript
/*
  toFixed Example
  - Rounding to 2 decimal places.
*/

console.log(100.554555.toFixed(2)) // "100.55"
```

---

### 4. parseInt()
- What it does: Pulls out the first integer from a string, ignoring anything after (like text).
- Limit: Only grabs whole numbers, stops at decimals or letters.

#### Example:
```javascript
/*
  parseInt Example
  - Extracting integers from strings.
*/

console.log(Number("100 Osama")) // NaN
console.log(+"100 Osama") // NaN
console.log(parseInt("100 Osama")) // 100
console.log(parseInt("Osama 100 Osama")) // NaN
console.log(parseInt("100.500 Osama")) // 100 (ignores decimal)
```

---

### 5. parseFloat()
- What it does: Grabs the first number (including decimals) from a string, stopping at letters.
- Differs: Unlike `parseInt()`, it keeps the decimal part.

#### Example:
```javascript
/*
  parseFloat Example
  - Extracting floating-point numbers.
*/

console.log(parseFloat("100.500 Osama")) // 100.500
```

---

### 6. isInteger() [ES6]
- What it does: Checks if a value is a whole number (no decimals).
- Returns: `true` or `false`.

#### Example:
```javascript
/*
  isInteger Example
  - Testing for whole numbers.
*/

console.log(Number.isInteger("100")) // false (string)
console.log(Number.isInteger(100.500)) // false (has decimal)
console.log(Number.isInteger(100)) // true (whole number)
```

---

### 7. isNaN() [ES6]
- What it does: Checks if a value is `NaN` (Not a Number) after some operation.
- Note: Use `Number.isNaN()` to avoid confusion with the global `isNaN()`.

#### Example:
```javascript
/*
  isNaN Example
  - Checking for NaN.
*/

console.log(Number.isNaN("Osama" / 20)) // true (division of string and number is NaN)
```

---

## 
- Wrap plain numbers in `()` for methods like `toString()` to avoid syntax errors.
- `toFixed()` returns a string, so use `+` or `Number()` if you need a number again.
- `parseInt()` and `parseFloat()` are lifesavers for cleaning up user input.
- `isInteger()` and `isNaN()` are great for validating data.
