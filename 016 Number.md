## Number

### 1. Double Precision
- What it is: JavaScript uses 64-bit floating-point numbers (double precision) for all numbers, so it handles both integers and decimals under the hood.
- Fun fact: This means every number you see is stored with some decimal precision, even if it looks like a whole number!

#### Example:
```javascript
/*
  Double Precision Example
  - Showing a big number as a double.
*/

console.log(1000000) // 1000000 (stored as a 64-bit float)
```

---

### 2. Syntactic Sugar "_"
- What it does: The underscore (`_`) acts like a comma for readability in big numbers—JavaScript ignores it when calculating.
- When to use it: Makes long numbers like 1,000,000 easier to read as 1_000_000.

#### Example:
```javascript
/*
  Syntactic Sugar Example
  - Using _ for readable numbers.
*/

console.log(1_000_000) // 1000000
```

---

### 3. e (Scientific Notation)
- What it does: `e` stands for exponent—`1e6` means 1 multiplied by 10 to the power of 6 (1,000,000).
- Handy: Great for super big or small numbers!

#### Example:
```javascript
/*
  Scientific Notation Example
  - Using e for a million.
*/

console.log(1e6) // 1000000
```

---

### 4. ** (Exponentiation)
- What it does: Raises a number to a power, like `10 ** 6` for 10 multiplied by itself 6 times.
- Alternative: Same as the `e` trick but written out.

#### Example:
```javascript
/*
  Exponentiation Example
  - Powering up with **.
*/

console.log(10 ** 6) // 1000000
console.log(10 * 10 * 10 * 10 * 10 * 10) // 1000000 (same thing!)
```

---

### 5. With Decimal
- What it is: Numbers can have decimals, and JavaScript treats 1000000.0 the same as 1000000 internally.
- Note: The `.0` just shows it’s a float, but it doesn’t change the value.

#### Example:
```javascript
/*
  Decimal Example
  - Adding a decimal for clarity.
*/

console.log(1000000.0) // 1000000
```

---

### 6. Number + BigInt
- Quick mention: You can mix `Number` with `BigInt` for huge numbers beyond safe limits, but we’ll skip that here—check `BigInt` later!
- For now: Stick to regular numbers for this example.

---

### 7. Number Min Value
- What it is: The smallest safe integer JavaScript can handle is stored in `Number.MIN_SAFE_INTEGER` (-9007199254740991).
- Note: We’re not logging it here, but it’s good to know!

---

### 8. Number Max Value
- What it is: The biggest safe integer is `Number.MAX_SAFE_INTEGER` (9007199254740991). Beyond that, you hit precision issues.
- Beyond max: `Number.MAX_VALUE` is the absolute max number JavaScript can represent, and adding more just pushes it toward `Infinity`.

#### Example:
```javascript
/*
  Max Value Examples
  - Checking safe max and absolute max.
*/

console.log(Number.MAX_SAFE_INTEGER) // 9007199254740991
console.log(Number.MAX_VALUE) // 1.7976931348623157e+308
console.log(Number.MAX_VALUE + 23434343434) // Still close to MAX_VALUE, no precision
```

---


- Use `_` or `e` to make big numbers readable—your eyes will thank you!
- Watch out past `MAX_SAFE_INTEGER`—results get fuzzy.
- `MAX_VALUE` is the ceiling; adding more won’t give exact numbers.
