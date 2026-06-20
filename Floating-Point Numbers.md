## What Is a Floating-Point Number?

A **floating-point number** is a number with a decimal point.

Examples:

```javascript
3.14
0.5
-10.75
100.001
```

In JavaScript, all regular numbers (integers and decimals) use the **`Number`** data type.

```javascript
const a = 10;      // Integer
const b = 10.5;    // Floating-point number

console.log(typeof a); // "number"
console.log(typeof b); // "number"
```

---

## How JavaScript Stores Numbers

JavaScript stores all `Number` values using the **IEEE 754 double-precision floating-point format**.

This format uses **64 bits** to represent numbers.

```text
Sign | Exponent | Fraction (Mantissa)
 1 bit | 11 bits | 52 bits
```

Because only a limited number of bits are available, some decimal values cannot be represented exactly in binary.

---

## Why Floating-Point Issues Happen

Computers store numbers in **binary (base 2)**.

Some decimal fractions that are simple in base 10 become repeating fractions in base 2.

For example:

```text
0.1  = 0.00011001100110011... (binary)
0.2  = 0.0011001100110011... (binary)
```

These repeating values must be rounded when stored.

The tiny rounding errors can affect calculations.

---

## Common Floating-Point Issue

```javascript
console.log(0.1 + 0.2);
```

Output:

```text
0.30000000000000004
```

Expected:

```text
0.3
```

Actual:

```text
0.30000000000000004
```

This happens because `0.1` and `0.2` are not stored exactly.

---

## More Examples

```javascript
console.log(0.1 + 0.7); // 0.7999999999999999

console.log(0.3 - 0.2); // 0.09999999999999998

console.log(0.1 + 0.2 === 0.3); // false
```

---

## Why Direct Comparison Is Dangerous

Avoid comparing floating-point numbers with `===`.

```javascript
console.log(0.1 + 0.2 === 0.3);
```

Output:

```text
false
```

Instead, compare the difference using a small tolerance value.

```javascript
const result = Math.abs((0.1 + 0.2) - 0.3);

console.log(result < Number.EPSILON);
```

Output:

```text
true
```

---

## `Number.EPSILON`

`Number.EPSILON` is the smallest difference between `1` and the next representable number.

```javascript
console.log(Number.EPSILON);
```

Output:

```text
2.220446049250313e-16
```

It helps you compare floating-point values safely.

Example:

```javascript
function nearlyEqual(a, b) {
  return Math.abs(a - b) < Number.EPSILON;
}

console.log(nearlyEqual(0.1 + 0.2, 0.3)); // true
```

---

## How to Avoid Floating-Point Problems

### 1. Work with Integers When Possible

Instead of:

```javascript
const price = 19.99;
```

Use the smallest unit:

```javascript
const priceInCents = 1999;
```

Then convert when displaying:

```javascript
console.log(priceInCents / 100); // 19.99
```

This approach is common in financial applications.

---

### 2. Use `toFixed()`

Format numbers to a fixed number of decimal places.

```javascript
const result = 0.1 + 0.2;

console.log(result.toFixed(2));
```

Output:

```text
"0.30"
```

> `toFixed()` returns a string.

---

### 3. Round Explicitly

```javascript
const result = 0.1 + 0.2;

const rounded = Math.round(result * 100) / 100;

console.log(rounded);
```

Output:

```text
0.3
```

---

### 4. Use Decimal Libraries for Financial Calculations

For applications requiring high precision, such as banking or accounting, use specialized libraries instead of regular JavaScript numbers.

Examples:

* `decimal.js`
* `big.js`

---

## Safe Integer Limits

JavaScript numbers can safely represent integers only within this range:

```javascript
console.log(Number.MAX_SAFE_INTEGER);
console.log(Number.MIN_SAFE_INTEGER);
```

Output:

```text
9007199254740991
-9007199254740991
```

Beyond this range, precision issues occur.

Example:

```javascript
console.log(9007199254740992 === 9007199254740993);
```

Output:

```text
true
```

For very large integers, use `BigInt`.

```javascript
const big = 9007199254740993n;
```

---

## Summary

```text
JavaScript stores all numbers as 64-bit floating-point values.
```

```text
Some decimal values cannot be represented exactly in binary.
```

```text
0.1 + 0.2 !== 0.3
```

### Best Practices

* Avoid direct equality comparisons with decimals.
* Use `Number.EPSILON` for comparisons.
* Store money as integers (cents, paise, etc.).
* Use `toFixed()` or rounding for display purposes.
* Use `BigInt` for very large integers.
* Use decimal libraries for financial calculations.
