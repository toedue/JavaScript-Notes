JavaScript provides the **`Number` object** with useful properties and methods for working with numbers.

---

## Number Properties

These are accessed directly from `Number`.

### `Number.MAX_VALUE`

Returns the largest possible number JavaScript can represent.

```javascript id="6g4y7s"
console.log(Number.MAX_VALUE);
```

Output:

```text id="5ej4f6"
1.7976931348623157e+308
```

---

### `Number.MIN_VALUE`

Returns the smallest positive number greater than `0`.

```javascript id="zpk7mb"
console.log(Number.MIN_VALUE);
```

Output:

```text id="p8jvzt"
5e-324
```

---

### `Number.MAX_SAFE_INTEGER`

Largest integer that can be represented accurately.

```javascript id="5az1mk"
console.log(Number.MAX_SAFE_INTEGER);
```

Output:

```text id="i76myk"
9007199254740991
```

---

### `Number.MIN_SAFE_INTEGER`

Smallest integer that can be represented accurately.

```javascript id="dpk99x"
console.log(Number.MIN_SAFE_INTEGER);
```

Output:

```text id="q8e8zq"
-9007199254740991
```

---

### `Number.EPSILON`

The smallest difference between `1` and the next representable number.

Useful for comparing floating-point numbers.

```javascript id="vjlwmn"
console.log(Number.EPSILON);
```

Output:

```text id="7qv3ko"
2.220446049250313e-16
```

---

## Number Checking Methods

### `Number.isNaN()`

Checks whether a value is `NaN`.

```javascript id="3s4t5y"
console.log(Number.isNaN(NaN));     // true
console.log(Number.isNaN("hello")); // false
```

> Prefer `Number.isNaN()` over the global `isNaN()`.

---

### `Number.isFinite()`

Checks whether a value is a finite number.

```javascript id="fk0b2n"
console.log(Number.isFinite(10));        // true
console.log(Number.isFinite(Infinity));  // false
console.log(Number.isFinite("10"));      // false
```

---

### `Number.isInteger()`

Checks whether a value is an integer.

```javascript id="y0a3ow"
console.log(Number.isInteger(10));   // true
console.log(Number.isInteger(10.5)); // false
```

---

### `Number.isSafeInteger()`

Checks whether a value is a safe integer.

```javascript id="q1vn1g"
console.log(Number.isSafeInteger(100)); // true

console.log(
  Number.isSafeInteger(9007199254740992)
); // false
```

---

## Instance Methods

These methods are called on a number value.

---

### `toFixed()`

Formats a number with a fixed number of decimal places.

```javascript id="p0a2jy"
const price = 19.987;

console.log(price.toFixed(2));
```

Output:

```text id="i4zibj"
"19.99"
```

> Returns a string.

---

### `toPrecision()`

Formats a number to a specified total number of significant digits.

```javascript id="2y98mu"
const num = 123.456;

console.log(num.toPrecision(4));
```

Output:

```text id="n5l6xv"
"123.5"
```

---

### `toString()`

Converts a number to a string.

```javascript id="l7x8zq"
const num = 100;

console.log(num.toString());
```

Output:

```text id="h4k1de"
"100"
```

You can also convert to different bases.

```javascript id="vl4yqf"
const num = 10;

console.log(num.toString(2));  // "1010"
console.log(num.toString(16)); // "a"
```

---

### `toExponential()`

Returns a number in exponential notation.

```javascript id="dtxqho"
const num = 123456;

console.log(num.toExponential(2));
```

Output:

```text id="j81s7n"
"1.23e+5"
```

---

## Converting Values to Numbers

### `Number()`

Converts a value to a number.

```javascript id="0xj9v7"
console.log(Number("42"));   // 42
console.log(Number(true));   // 1
console.log(Number(false));  // 0
```

If conversion fails:

```javascript id="7t2fmc"
console.log(Number("hello"));
```

Output:

```text id="jbjlwm"
NaN
```

---

### `parseInt()`

Extracts an integer from a string.

```javascript id="x59xq2"
console.log(parseInt("100px")); // 100
console.log(parseInt("42.9"));  // 42
```

Specify the radix when possible:

```javascript id="xhf4go"
console.log(parseInt("1010", 2));
```

Output:

```text id="8qyd6p"
10
```

---

### `parseFloat()`

Extracts a floating-point number from a string.

```javascript id="syjlwm"
console.log(parseFloat("3.14px"));
```

Output:

```text id="7d9mhn"
3.14
```

---

## Common Math Operations

These belong to the global `Math` object, not `Number`, but are frequently used together.

### Rounding Methods

```javascript id="frzqk0"
console.log(Math.round(4.6)); // 5
console.log(Math.floor(4.9)); // 4
console.log(Math.ceil(4.1));  // 5
console.log(Math.trunc(4.9)); // 4
```

---

### Other Useful Methods

```javascript id="mjlwmk"
console.log(Math.abs(-10));      // 10
console.log(Math.max(1, 5, 3));  // 5
console.log(Math.min(1, 5, 3));  // 1
console.log(Math.pow(2, 3));     // 8
console.log(Math.sqrt(25));      // 5
```

Modern exponent syntax:

```javascript id="0v81oq"
console.log(2 ** 3); // 8
```

---

### Random Numbers

```javascript id="by9vtx"
console.log(Math.random());
```

Returns a number between `0` (inclusive) and `1` (exclusive).

Generate a random integer from `1` to `10`:

```javascript id="ec6zuw"
const random = Math.floor(Math.random() * 10) + 1;

console.log(random);
```

---

## Quick Reference Table

| Method / Property        | Purpose                  |
| ------------------------ | ------------------------ |
| `Number()`               | Convert to number        |
| `Number.isNaN()`         | Check for `NaN`          |
| `Number.isFinite()`      | Check for finite numbers |
| `Number.isInteger()`     | Check for integers       |
| `Number.isSafeInteger()` | Check safe integers      |
| `toFixed()`              | Fixed decimal places     |
| `toPrecision()`          | Significant digits       |
| `toString()`             | Convert to string        |
| `parseInt()`             | Parse integer            |
| `parseFloat()`           | Parse decimal            |
| `Math.round()`           | Round normally           |
| `Math.floor()`           | Round down               |
| `Math.ceil()`            | Round up                 |
| `Math.trunc()`           | Remove decimal part      |
| `Math.random()`          | Generate random numbers  |

---

## Best Practices

* Use `Number.isNaN()` instead of `isNaN()`.
* Use `parseInt(value, 10)` to avoid radix confusion.
* Remember that `toFixed()` returns a string.
* Use `Number.EPSILON` when comparing decimal values.
* Use `Math.floor(Math.random() * n)` for random integers.
* Prefer `2 ** 3` over `Math.pow(2, 3)` for readability.
