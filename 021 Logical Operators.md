## Logical Operators

### 1. ! Not
- What it does: Flips a boolean value—`true` becomes `false`, and `false` becomes `true`.
- Handy: Great for reversing a condition!

#### Example:
```javascript
/*
  ! Not Example
  - Flipping true and a comparison.
*/

console.log(true) // true
console.log(!true) // false
console.log(!(10 == "10")) // false (10 == "10" is true, so ! makes it false)
```

---

### 2. && And
- What it does: Returns `true` only if ALL conditions are true. If any are false, it’s `false`.
- How it works: Checks from left to right and stops at the first `false`.

#### Example:
```javascript
/*
  && And Example
  - Combining multiple conditions.
*/

console.log(10 == "10" && 10 > 8 && 10 > 50) // false (10 > 50 is false)
```

---

### 3. || Or
- What it does: Returns `true` if AT LEAST one condition is true. Only `false` if all are false.
- How it works: Stops at the first `true` it finds.

#### Example:
```javascript
/*
  || Or Example
  - Checking if any condition is true.
*/

console.log(10 == "10" || 10 > 80 || 10 > 50) // true (10 == "10" is true)
```

---


- **`!`**: Super for negating—use it to check the opposite of a condition.
- **`&&`**: Think of it as “all must pass” for it to work.
- **`||`**: Like “any one will do”—it’s more lenient.
- **Short-circuit**: These operators stop evaluating once the result is clear (e.g., `false && anything` is `false` right away).

