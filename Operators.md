## What Are Operators?

**Operators** are symbols or keywords that perform operations on values (called **operands**).

Example:

```javascript
const sum = 10 + 5;
```

* `10` and `5` are **operands**
* `+` is the **operator**

---

## Types of Operators

```text
Operators
├── Arithmetic
├── Assignment
├── Comparison
├── Logical
├── Increment/Decrement
├── String
├── Conditional (Ternary)
├── Nullish Coalescing
├── Optional Chaining
├── Type
├── Bitwise
└── Spread and Rest
```

---

# 1. Arithmetic Operators

Used for mathematical calculations.

| Operator | Description    | Example  |
| -------- | -------------- | -------- |
| `+`      | Addition       | `10 + 5` |
| `-`      | Subtraction    | `10 - 5` |
| `*`      | Multiplication | `10 * 5` |
| `/`      | Division       | `10 / 5` |
| `%`      | Remainder      | `10 % 3` |
| `**`     | Exponentiation | `2 ** 3` |

### Examples

```javascript
console.log(10 + 5);  // 15
console.log(10 - 5);  // 5
console.log(10 * 5);  // 50
console.log(10 / 5);  // 2
console.log(10 % 3);  // 1
console.log(2 ** 3);  // 8
```

---

## The `+` Operator and Strings

When one operand is a string, JavaScript performs concatenation.

```javascript
console.log("Hello " + "World"); // "Hello World"
console.log("5" + 2);            // "52"
```

---

# 2. Assignment Operators

Used to assign values to variables.

| Operator | Equivalent To    |
| -------- | ---------------- |
| `=`      | `x = value`      |
| `+=`     | `x = x + value`  |
| `-=`     | `x = x - value`  |
| `*=`     | `x = x * value`  |
| `/=`     | `x = x / value`  |
| `%=`     | `x = x % value`  |
| `**=`    | `x = x ** value` |

### Examples

```javascript
let x = 10;

x += 5;  // 15
x -= 2;  // 13
x *= 2;  // 26
```

---

# 3. Comparison Operators

Used to compare values.

The result is always a boolean (`true` or `false`).

| Operator | Description               |
| -------- | ------------------------- |
| `==`     | Equal (with coercion)     |
| `===`    | Strict equal              |
| `!=`     | Not equal (with coercion) |
| `!==`    | Strict not equal          |
| `>`      | Greater than              |
| `<`      | Less than                 |
| `>=`     | Greater than or equal     |
| `<=`     | Less than or equal        |

### Examples

```javascript
console.log(10 > 5);     // true
console.log(10 < 5);     // false

console.log(5 == "5");   // true
console.log(5 === "5");  // false
```

> Prefer `===` and `!==` to avoid unexpected type coercion.

---

# 4. Logical Operators

Used to combine or invert boolean values.

| Operator | Description |   |            |
| -------- | ----------- | - | ---------- |
| `&&`     | Logical AND |   |            |
| `        |             | ` | Logical OR |
| `!`      | Logical NOT |   |            |

### AND (`&&`)

Returns `true` if both operands are truthy.

```javascript
console.log(true && true);   // true
console.log(true && false);  // false
```

### OR (`||`)

Returns `true` if at least one operand is truthy.

```javascript
console.log(true || false);  // true
console.log(false || false); // false
```

### NOT (`!`)

Reverses the boolean value.

```javascript
console.log(!true);   // false
console.log(!false);  // true
```

---

## Short-Circuit Evaluation

```javascript
console.log("Hello" || "World"); // "Hello"
console.log("" || "World");      // "World"

console.log(0 && "Hello");       // 0
console.log("Hi" && 123);        // 123
```

---

# 5. Increment and Decrement Operators

| Operator | Description   |
| -------- | ------------- |
| `++`     | Increase by 1 |
| `--`     | Decrease by 1 |

### Postfix

```javascript
let x = 5;

console.log(x++); // 5
console.log(x);   // 6
```

### Prefix

```javascript
let y = 5;

console.log(++y); // 6
console.log(y);   // 6
```

---

# 6. String Operators

Concatenate strings using `+` or `+=`.

```javascript
const first = "Java";
const second = "Script";

console.log(first + second); // "JavaScript"
```

---

# 7. Conditional (Ternary) Operator

A shorthand for `if...else`.

## Syntax

```javascript
condition ? valueIfTrue : valueIfFalse;
```

### Example

```javascript
const age = 20;

const message = age >= 18 ? "Adult" : "Minor";

console.log(message);
```

Output:

```text
Adult
```

---

# 8. Nullish Coalescing Operator (`??`)

Returns the right value only when the left value is `null` or `undefined`.

```javascript
const username = null;

console.log(username ?? "Guest");
```

Output:

```text
Guest
```

---

## Difference Between `||` and `??`

```javascript
console.log(0 || 100);   // 100
console.log(0 ?? 100);   // 0
```

`||` treats all falsy values as missing.

`??` treats only `null` and `undefined` as missing.

---

# 9. Optional Chaining (`?.`)

Safely accesses nested properties.

```javascript
const user = {};

console.log(user.address?.city);
```

Output:

```text
undefined
```

Without optional chaining:

```javascript
console.log(user.address.city);
```

This causes an error.

---

# 10. Type Operators

## `typeof`

Returns the data type of a value.

```javascript
console.log(typeof "Hello"); // "string"
console.log(typeof 42);      // "number"
console.log(typeof true);    // "boolean"
```

---

## `instanceof`

Checks whether an object belongs to a specific class or constructor.

```javascript
const arr = [];

console.log(arr instanceof Array); // true
```

---

# 11. Bitwise Operators

Perform operations at the binary level.

| Operator | Description |    |
| -------- | ----------- | -- |
| `&`      | AND         |    |
| `        | `           | OR |
| `^`      | XOR         |    |
| `~`      | NOT         |    |
| `<<`     | Left shift  |    |
| `>>`     | Right shift |    |

Example:

```javascript
console.log(5 & 1); // 1
```

> Bitwise operators are common in low-level programming and competitive programming.

---

# 12. Spread and Rest Operators (`...`)

The same syntax (`...`) has two different uses.

---

## Spread Operator

Expands elements.

### Arrays

```javascript
const a = [1, 2];
const b = [...a, 3];

console.log(b); // [1, 2, 3]
```

### Objects

```javascript
const user = { name: "Abudy" };

const copy = { ...user };
```

---

## Rest Parameters

Collect multiple values into an array.

```javascript
function sum(...numbers) {
  return numbers;
}

console.log(sum(1, 2, 3));
```

Output:

```javascript
[1, 2, 3]
```

---

# Operator Precedence

Some operators execute before others.

Example:

```javascript
console.log(2 + 3 * 4);
```

Output:

```text
14
```

Because multiplication has higher precedence than addition.

Use parentheses to control execution order.

```javascript
console.log((2 + 3) * 4);
```

Output:

```text
20
```

---

# Quick Summary Table

| Category            | Operators                 |   |    |
| ------------------- | ------------------------- | - | -- |
| Arithmetic          | `+ - * / % **`            |   |    |
| Assignment          | `= += -= *= /= %= **=`    |   |    |
| Comparison          | `== === != !== > < >= <=` |   |    |
| Logical             | `&&                       |   | !` |
| Increment/Decrement | `++ --`                   |   |    |
| Conditional         | `? :`                     |   |    |
| Nullish             | `??`                      |   |    |
| Optional Chaining   | `?.`                      |   |    |
| Type                | `typeof`, `instanceof`    |   |    |
| Spread/Rest         | `...`                     |   |    |

---

# Best Practices

* Use `===` and `!==` instead of `==` and `!=`.
* Use `??` when `0`, `false`, or `""` are valid values.
* Use optional chaining (`?.`) to avoid property access errors.
* Use parentheses to make expressions easier to read.
* Avoid overusing `++` and `--` in complex expressions.
