## Math Object

### 1. round()
- What it does: Rounds a number to the nearest integer. If it’s .5 or higher, it rounds up; below .5, it rounds down.
- Fun part: Perfect for cleaning up decimals!

#### Example:
```javascript
/*
  round Example
  - Rounding to the nearest integer.
*/

console.log(Math.round(99.2)) // 99
console.log(Math.round(99.5)) // 100
```

---

### 2. ceil()
- What it does: Always rounds up to the next integer, no matter how close to the current one.
- Use it: When you need the ceiling value every time!

#### Example:
```javascript
/*
  ceil Example
  - Always rounding up.
*/

console.log(Math.ceil(99.2)) // 100
```

---

### 3. floor()
- What it does: Always rounds down to the previous integer, even if it’s super close to the next one.
- Handy: Great for dropping decimals completely!

#### Example:
```javascript
/*
  floor Example
  - Always rounding down.
*/

console.log(Math.floor(99.9)) // 99
```

---

### 4. min()
- What it does: Finds the smallest number in a list you give it.
- Cool: Takes as many numbers as you throw at it!

#### Example:
```javascript
/*
  min Example
  - Finding the smallest value.
*/

console.log(Math.min(10, 20, 100, -100, 90)) // -100
```

---

### 5. max()
- What it does: Picks the largest number from a list you provide.
- Nice: Works with any number of arguments too!

#### Example:
```javascript
/*
  max Example
  - Finding the largest value.
*/

console.log(Math.max(10, 20, 100, -100, 90)) // 100
```

---

### 6. pow()
- What it does: Raises a number to a power—like 2 to the 4th is 16.
- Alternative: Same as using `**`!

#### Example:
```javascript
/*
  pow Example
  - Raising a number to a power.
*/

console.log(Math.pow(2, 4)) // 16
```

---

### 7. random()
- What it does: Gives you a random number between 0 (inclusive) and 1 (exclusive).
- Use it: Perfect for games or random picks—multiply and round to get bigger ranges!

#### Example:
```javascript
/*
  random Example
  - Generating a random number.
*/

console.log(Math.random()) // Some number between 0 and 1, like 0.723
```

---

### 8. trunc() [ES6]
- What it does: Chops off the decimal part, leaving the integer—no rounding, just cuts!
- Differs: Unlike `floor()`, it doesn’t care about the sign.

#### Example:
```javascript
/*
  trunc Example
  - Truncating to remove decimals.
*/

console.log(Math.trunc(99.5)) // 99
```

---


- `round()` is your go-to for natural rounding; `ceil()` and `floor()` are for forcing up or down.
- `min()` and `max()` are awesome for comparing lists.
- `random()` is 0 to 1, so multiply by a number (e.g., `Math.floor(Math.random() * 10)`) for a range like 0-9.
- `trunc()` is like a clean cut—no fuss!
