JavaScript is a **dynamically typed language**, which means variables can hold values of different types at different times.

Because of this flexibility, JavaScript often needs to convert values from one type to another.

There are two ways this happens:

1. **Type Conversion (Explicit Conversion)**
2. **Type Coercion (Implicit Conversion)**

---

## Type Conversion vs Type Coercion

| Feature        | Type Conversion     | Type Coercion       |
| -------------- | ------------------- | ------------------- |
| Performed by   | Programmer          | JavaScript engine   |
| Also called    | Explicit conversion | Implicit conversion |
| Predictability | High                | Lower               |
| Example        | `Number("42")`      | `"42" * 2`          |

---

# 1. Type Conversion (Explicit Conversion)

You intentionally convert a value from one type to another.

---

## Converting to a Number

### `Number()`

```javascript
console.log(Number("42"));      // 42
console.log(Number("3.14"));    // 3.14
console.log(Number(true));      // 1
console.log(Number(false));     // 0
console.log(Number(null));      // 0
console.log(Number(""));        // 0
console.log(Number("hello"));   // NaN
```

---

### `parseInt()`

Converts a string to an integer.

```javascript
console.log(parseInt("100"));      // 100
console.log(parseInt("100px"));    // 100
console.log(parseInt("3.14"));     // 3
```

Specify the radix when possible:

```javascript
console.log(parseInt("1010", 2));  // 10
```

---

### `parseFloat()`

Converts a string to a floating-point number.

```javascript
console.log(parseFloat("3.14"));     // 3.14
console.log(parseFloat("3.14px"));   // 3.14
```

---

## Converting to a String

### `String()`

```javascript
console.log(String(42));         // "42"
console.log(String(true));       // "true"
console.log(String(null));       // "null"
```

---

### `toString()`

```javascript
const num = 42;

console.log(num.toString());     // "42"
```

> `null` and `undefined` do not have a `toString()` method.

```javascript
console.log(String(null));       // "null"
```

---

## Converting to a Boolean

### `Boolean()`

```javascript
console.log(Boolean(1));         // true
console.log(Boolean(0));         // false
console.log(Boolean("hello"));   // true
console.log(Boolean(""));        // false
```

---

## Falsy Values

These values become `false` when converted to a boolean:

```javascript
false
0
-0
0n
""
null
undefined
NaN
```

Everything else is **truthy**.

---

# 2. Type Coercion (Implicit Conversion)

JavaScript automatically converts values when performing operations.

---

## String Coercion

When using the `+` operator and one operand is a string, JavaScript converts the other operand to a string.

```javascript
console.log("5" + 2);       // "52"
console.log("Hello " + 5);  // "Hello 5"
```

---

## Numeric Coercion

Operators like `-`, `*`, `/`, and `%` convert values to numbers.

```javascript
console.log("5" - 2);   // 3
console.log("5" * 2);   // 10
console.log("10" / 2);  // 5
```

---

## Boolean Coercion

Conditions automatically convert values to booleans.

```javascript
if ("hello") {
  console.log("Runs");
}

if (0) {
  console.log("Does not run");
}
```

---

## Examples of Coercion

```javascript
console.log(true + 1);      // 2
console.log(false + 1);     // 1

console.log(null + 1);      // 1
console.log(undefined + 1); // NaN
```

Explanation:

```text
true      → 1
false     → 0
null      → 0
undefined → NaN
```

---

# Equality Operators and Coercion

## Loose Equality (`==`)

Performs type coercion before comparing.

```javascript
console.log(5 == "5");        // true
console.log(false == 0);      // true
console.log(null == undefined); // true
```

This can produce unexpected results.

---

## Strict Equality (`===`)

Compares both value and type.

```javascript
console.log(5 === "5");   // false
console.log(false === 0); // false
```

Use `===` in most cases.

---

## `==` vs `===`

| Expression           | Result  |
| -------------------- | ------- |
| `5 == "5"`           | `true`  |
| `5 === "5"`          | `false` |
| `0 == false`         | `true`  |
| `0 === false`        | `false` |
| `null == undefined`  | `true`  |
| `null === undefined` | `false` |

---

# Common Coercion Examples

```javascript
console.log("5" + 1);      // "51"
console.log("5" - 1);      // 4

console.log(1 + true);     // 2
console.log(1 + false);    // 1

console.log("5" * "2");    // 10

console.log([] + []);      // ""
console.log([] + 1);       // "1"

console.log(null + 1);     // 1
console.log(undefined + 1); // NaN
```

---

# How to Avoid Coercion Bugs

* Prefer explicit conversions.
* Use `===` and `!==` instead of `==` and `!=`.
* Be careful when mixing strings and numbers.
* Understand truthy and falsy values.
* Validate user input before using it.

---

# Quick Reference Table

| Conversion | Method                                   |
| ---------- | ---------------------------------------- |
| To Number  | `Number()`, `parseInt()`, `parseFloat()` |
| To String  | `String()`, `toString()`                 |
| To Boolean | `Boolean()`                              |

---

# Summary

```text
Type Conversion = Explicit conversion by the programmer.

Type Coercion = Automatic conversion by JavaScript.
```

```text
+ operator with a string → string conversion

-, *, /, % operators → number conversion
```

```text
Use === instead of == whenever possible.
```

```text
Falsy values:
false, 0, -0, 0n, "", null, undefined, NaN
```
