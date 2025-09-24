## Logical Or (||)

### What It Is
- What it does: `||` returns the first "truthy" value it finds, or the last value if all are "falsy".
- Falsy values: `0`, `""` (empty string), `null`, `undefined`, `NaN`, `false`.
- Truthy values: Everything else (like `100`, `-100`, any non-empty string).

#### Examples:
```javascript
/*
  Logical Or Examples
  - Testing Boolean conversion of values.
*/

console.log(Boolean(100)) // true
console.log(Boolean(-100)) // true
console.log(Boolean(0)) // false
console.log(Boolean("")) // false
console.log(Boolean(null)) // false
```

---

### Default Value with ||
- What it does: If the first value is falsy, it picks the next one as a default.
- Catch: `0` or `""` are falsy, so it might skip them unexpectedly.

#### Example:
```javascript
/*
  Logical Or Default Value
  - Using || to set a default price.
*/

let price = 0
console.log(`The Price Is ${price || 200}`) // "The Price Is 200" (0 is falsy, so 200)
```

---

## Nullish Coalescing Operator (??)

### What It Is
- What it does: `??` returns the first defined value, only treating `null` and `undefined` as falsy. Other falsy values like `0` or `""` are kept.
- Introduced: ES11 (2020)—more precise than `||` for defaults.

#### Example:
```javascript
/*
  Nullish Coalescing Default Value
  - Using ?? to set a default price.
*/

console.log(`The Price Is ${price ?? 200}`) // "The Price Is 0" (0 is not null/undefined)
```

---

- **`||`**: Good for broad defaults, but watch out—it treats `0` as falsy.
- **`??`**: Better for strict checks when you only care about `null` or `undefined`.
- **Combine**: Use `??` when `0` or `""` should be valid, `||` when they shouldn’t.
- **Test**: Log with `console.log(Boolean(value))` to see what’s truthy or falsy.

