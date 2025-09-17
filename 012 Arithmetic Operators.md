
## Arithmetic Operators

### 1. + Addition
- What it does: Adds two numbers together—or tries to! If you mix in a string, it concatenates instead.
- Fun twist: `10 + "Osama"` becomes "10Osama" because JavaScript sees the string and switches gears.

#### Example:
```javascript
/*
  Addition Example
  - Adding numbers and mixing with a string.
*/

console.log(10 + 20) // 30
console.log(10 + "Osama") // "10Osama"
```

---

### 2. - Subtraction
- What it does: Subtracts one number from another. If you throw in a string, you get `NaN` (Not a Number).
- Heads up: `NaN` is a special value when math fails—its type is still "number", weirdly!

#### Example:
```javascript
/*
  Subtraction Example
  - Subtracting numbers and testing with a string.
*/

console.log(10 - 20) // -10
console.log(10 - "Osama") // NaN
console.log(typeof NaN) // "number"
```

---

### 3. * Multiplication
- What it does: Multiplies two numbers. Works fine with negative numbers too.
- Simple stuff: Just give it numbers, and it crunches them!

#### Example:
```javascript
/*
  Multiplication Example
  - Multiplying positive and negative numbers.
*/

console.log(10 * 20) // 200
console.log(10 * -20) // -200
```

---

### 4. / Division
- What it does: Divides one number by another. Gives you decimals if it’s not even.
- Note: No zero division here, or you’ll get `Infinity`!

#### Example:
```javascript
/*
  Division Example
  - Dividing with whole and decimal results.
*/

console.log(20 / 5) // 4
console.log(20 / 3) // 6.666...
```

---

### 5. ** Exponentiation (ES7)
- What it does: Raises a number to the power of another—like 2 squared or cubed.
- Cool alternative: Same as doing multiple multiplications manually.

#### Example:
```javascript
/*
  Exponentiation Example
  - Using ** and comparing with manual multiplication.
*/

console.log(2 ** 4) // 16 (2 * 2 * 2 * 2)
console.log(2 * 2 * 2 * 2) // 16
```

---

### 6. % Modulus (Division Remainder)
- What it does: Gives you the leftover after division—like how much doesn’t fit evenly.
- Handy: Checks if a number is odd or even (0 or 1 remainder).

#### Example:
```javascript
/*
  Modulus Example
  - Showing remainders with even and odd numbers.
*/

console.log(10 % 2) // 0 (even, no remainder)
console.log(11 % 2) // 1 (odd, removes 1)
```

---

### 7. ++ Increment [Post / Pre]
- What it does: Adds 1 to a number. `x++` (post) uses the original value first, then adds 1. `++x` (pre) adds 1 first, then uses it.
- Play with it: Try both to see the difference!

#### Example:
```javascript
/*
  Increment Example
  - Testing post and pre increment.
*/

let num = 5
console.log(num++) // 5 (then becomes 6)
console.log(++num) // 7 (adds 1 first)
```

---

### 8. -- Decrement [Post / Pre]
- What it does: Subtracts 1 from a number. `x--` (post) uses the value first, then subtracts. `--x` (pre) subtracts first, then uses it.
- Same deal: Experiment with both!

#### Example:
```javascript
/*
  Decrement Example
  - Testing post and pre decrement.
*/

let num = 5
console.log(num--) // 5 (then becomes 4)
console.log(--num) // 3 (subtracts first)
```

---
