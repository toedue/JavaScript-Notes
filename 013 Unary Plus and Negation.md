## Unary Plus and Negation

### 1. + Unary Plus
- What it does: Tries to convert whatever’s after it into a number. If it can’t, you get `NaN` (Not a Number).
- When to use it: Handy for quickly turning strings into numbers without `parseInt` or `Number()`.

### 2. - Unary Negation
- What it does: Also converts to a number but flips it to negative. If it can’t convert, it’s `NaN` again.
- Cool twist: Works the same as unary plus but adds that negative spin!

## Tests
Let’s run these through different types to see what happens:

#### Examples:
```javascript
/*
  Unary Plus and Negation Examples
  - Testing with various inputs.
*/

// Unary Plus (+)
console.log(+100) // 100 (normal number)
console.log(+"100") // 100 (string number becomes number)
console.log(+"-100") // -100 (string negative becomes number)
console.log(+"Osama") // NaN (text can’t convert)
console.log(+"15.5") // 15.5 (float works)
console.log(+0xff) // 255 (hex converts to decimal)
console.log(+null) // 0 (null becomes 0)
console.log(+false) // 0 (false becomes 0)
console.log(+true) // 1 (true becomes 1)

// Unary Negation (-)
console.log(-100) // -100 (normal number negated)
console.log(-"100") // -100 (string number becomes -100)
console.log(-"-100") // 100 (string negative flips to positive)
console.log(-"Osama") // NaN (text can’t convert)
console.log(-"15.5") // -15.5 (float becomes negative)
console.log(-0xff) // -255 (hex converts to -255)
console.log(-null) // -0 (null becomes -0)
console.log(-false) // -0 (false becomes -0)
console.log(-true) // -1 (true becomes -1)

// Bonus: Number() for comparison
console.log(Number("100")) // 100 (same as + but explicit)
```

---


- **Unary Plus**: Great shortcut for number conversion—`+"100"` is like `Number("100")` but shorter!
- **Unary Negation**: Flips the sign after converting, so `-"100"` gives `-100`.
- **Tricky Bits**: Text like "Osama" breaks it with `NaN`, and hex (like `0xff`) turns into decimal (255).
- **Null/Booleans**: `null` and `false` become `0`, `true` becomes `1`—pretty neat conversion!
