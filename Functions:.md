## What Is a Function?

A **function** is a reusable block of code designed to perform a specific task.

Instead of writing the same code repeatedly, you can place it inside a function and use it whenever needed.

### Benefits of Functions

* Reuse code
* Improve readability
* Organize programs into smaller parts
* Make code easier to maintain and debug

---

## Basic Syntax

```javascript id="s1f4g9"
function functionName() {
  // code to execute
}
```

### Example

```javascript id="q4h8m2"
function greet() {
  console.log("Hello!");
}
```

The function is defined, but it does not run automatically.

---

## Calling (Invoking) a Function

To execute a function, use its name followed by parentheses.

```javascript id="m7k3p1"
greet();
```

### Output

```text id="o9d6v5"
Hello!
```

---

## Function Parameters

Parameters are variables listed inside the parentheses of a function definition.

They allow a function to receive data.

```javascript id="u2n8c7"
function greet(name) {
  console.log(`Hello, ${name}!`);
}
```

Here, `name` is a parameter.

---

## Function Arguments

Arguments are the actual values passed to a function when it is called.

```javascript id="r6y5w3"
greet("Abudy");
```

### Output

```text id="x8j2k4"
Hello, Abudy!
```

* **Parameter:** `name`
* **Argument:** `"Abudy"`

---

## Multiple Parameters

```javascript id="z3n4f6"
function add(a, b) {
  console.log(a + b);
}

add(10, 20);
```

### Output

```text id="v1p9m8"
30
```

---

## Returning Values

Functions can send a value back using the `return` keyword.

```javascript id="h5t7q2"
function add(a, b) {
  return a + b;
}

const result = add(10, 20);

console.log(result);
```

### Output

```text id="j4r8u1"
30
```

### Important Notes

* A function stops executing when `return` is reached.
* A function can return only one value.

---

## Function Without `return`

If no value is returned, the function returns `undefined`.

```javascript id="e7m1n5"
function sayHello() {
  console.log("Hello");
}

const result = sayHello();

console.log(result);
```

### Output

```text id="c3v6b9"
Hello
undefined
```

---

## Default Parameters

You can provide default values for parameters.

```javascript id="w2g9d4"
function greet(name = "Guest") {
  console.log(`Hello, ${name}`);
}

greet();
```

### Output

```text id="b8k5n7"
Hello, Guest
```

---

## Function Expressions

A function can be stored in a variable.

```javascript id="p6r2m1"
const greet = function () {
  console.log("Hello!");
};
```

Call it like this:

```javascript id="d9q7t3"
greet();
```

---

## Arrow Functions

Arrow functions provide a shorter syntax.

### Syntax

```javascript id="f1n5w8"
const functionName = () => {
  // code
};
```

### Example

```javascript id="y3m8r2"
const greet = () => {
  console.log("Hello!");
};

greet();
```

---

## Arrow Function with Parameters

```javascript id="a7v4c6"
const add = (a, b) => {
  return a + b;
};
```

---

## Implicit Return

If the function body contains only one expression, you can omit `return` and braces.

```javascript id="l2q9x5"
const add = (a, b) => a + b;
```

---

## Function Declaration vs Function Expression

| Feature                  | Function Declaration  | Function Expression           |
| ------------------------ | --------------------- | ----------------------------- |
| Syntax                   | `function greet() {}` | `const greet = function() {}` |
| Hoisted                  | ✅ Yes                 | ❌ No                          |
| Called before definition | ✅ Yes                 | ❌ No                          |

### Example

Function declaration:

```javascript id="g5k2m8"
sayHi();

function sayHi() {
  console.log("Hi");
}
```

Works because declarations are hoisted.

Function expression:

```javascript id="u8n1f4"
sayHi();

const sayHi = function () {
  console.log("Hi");
};
```

Produces an error.

---

## Scope

Variables declared inside a function are available only within that function.

```javascript id="j6m3v9"
function demo() {
  let message = "Hello";
}

console.log(message);
```

### Output

```text id="r4p8x2"
ReferenceError
```

---

## Local and Global Variables

### Global Variable

```javascript id="t9w5q1"
const language = "JavaScript";

function show() {
  console.log(language);
}
```

Accessible everywhere.

---

### Local Variable

```javascript id="k3r7m2"
function show() {
  const message = "Hello";
}
```

Accessible only inside the function.

---

## Higher-Order Functions

Functions can:

* Be stored in variables
* Be passed as arguments
* Be returned from other functions

Example:

```javascript id="m1v8c5"
function greet(callback) {
  callback();
}

greet(() => {
  console.log("Hello");
});
```

---

## Callback Functions

A callback function is a function passed to another function.

```javascript id="x5n2d7"
function processUser(name, callback) {
  callback(name);
}

processUser("Abudy", (user) => {
  console.log(`Welcome, ${user}`);
});
```

---

## Immediately Invoked Function Expression (IIFE)

Runs immediately after it is defined.

```javascript id="q2r6m4"
(function () {
  console.log("Executed!");
})();
```

---

## Rest Parameters

Accept multiple arguments as an array.

```javascript id="z8v3k1"
function sum(...numbers) {
  console.log(numbers);
}

sum(1, 2, 3, 4);
```

### Output

```text id="f7m2x9"
[1, 2, 3, 4]
```

---

## The `arguments` Object

Available in regular functions.

```javascript id="n4t8q2"
function show() {
  console.log(arguments);
}

show(1, 2, 3);
```

> Arrow functions do not have their own `arguments` object.

---

## Hoisting

Function declarations are hoisted.

```javascript id="y9w4m1"
greet();

function greet() {
  console.log("Hello");
}
```

Works correctly.

Function expressions and arrow functions are not hoisted in the same way.

---

## Best Practices

* Use descriptive function names.
* Keep functions focused on one task.
* Prefer `const` for function expressions and arrow functions.
* Use `return` when you need a result.
* Use arrow functions for short callbacks.
* Use regular functions when you need `this`, `arguments`, or constructor behavior.

---

## Quick Summary

```text id="h2k7m4"
Function → Reusable block of code
Parameter → Variable in function definition
Argument → Value passed to a function
Return → Sends a value back
```

```text id="p8v5q3"
Function Declaration → Hoisted
Function Expression → Not hoisted
Arrow Function → Short syntax
```

```text id="u6m9r2"
Regular functions have:
- this
- arguments

Arrow functions do not.
```
