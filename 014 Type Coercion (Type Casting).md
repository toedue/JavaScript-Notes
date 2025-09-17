## Type Coercion (Type Casting)

### 1. + (Addition or Concatenation)
- What it does: If you use `+` with a string, it tries to concatenate (stick things together) instead of adding. With numbers, it adds normally.
- Tricky part: A string like "100" with a number can turn the whole thing into a string if it hits first!

#### Example:
```javascript
/*
  + Coercion Example
  - Mixing string and number with +.
*/

let a = "100"
let b = 20
console.log(a + b) // "10020" (concatenates because of the string)
```

---

### 2. - (Subtraction)
- What it does: Forces a conversion to numbers before subtracting. Strings get turned into numbers, or you get `NaN` if it can’t.
- Cool bit: It’s stricter about becoming a number than `+`.

#### Example:
```javascript
/*
  - Coercion Example
  - Subtracting with a string turned to number.
*/

console.log("" - 2) // -2 (empty string becomes 0, then -2)
```

---

### 3. false - true
- What it does: Booleans get coerced to numbers (`false` is 0, `true` is 1), then the math happens.
- Simple math: `0 - 1 = -1`.

#### Example:
```javascript
/*
  Boolean Coercion Example
  - Subtracting true from false.
*/

console.log(false - true) // -1 (0 - 1)
```

---

### Your Example
- Let’s see what happens with your code—`+a` turns the string into a number, then adds everything.

#### Example:
```javascript
/*
  Type Coercion Full Example
  - Using unary + to convert and add.
*/

let a = "100"
let b = 20
let c = true

console.log(+a + b + c) // 121 (100 + 20 + 1)
```

---

- **Use `+` carefully**: Stick a `+` in front (unary plus) to force number conversion if you want addition, not concatenation.
- **`-` is safer**: It almost always tries to make numbers, so fewer surprises.
- **Booleans**: Remember `false` is 0 and `true` is 1 when doing math.
- **Debug**: If you get weird results, check `typeof` to see what’s what!
