# JavaScript Variables: Complete Notes

## 1. What Is a Variable?

A **variable** is a named container used to store data values.

You can think of a variable as a labeled box:

```text
name ──► "Abudy"
age  ──► 20
```

JavaScript uses three keywords to create variables:

* `let`
* `const`
* `var`

---

## 2. Variable Declaration, Initialization, and Assignment

These terms are often confused, so let's separate them.

### Declaration

Creating a variable name.

```javascript
let age;
```

Here, `age` exists, but it has no value yet.

---

### Assignment

Giving a value to a variable.

```javascript
age = 20;
```

---

### Initialization

Declaring and assigning a value at the same time.

```javascript
let age = 20;
```

This is both declaration and assignment.

---

### Reassignment

Changing the value of an existing variable.

```javascript
let age = 20;

age = 21;
```

---

### Redeclaration

Creating a variable with the same name again in the same scope.

```javascript
let age = 20;
let age = 21; // Error
```

---

## 3. `let`

Introduced in ES6 (2015).

### Syntax

```javascript
let name = "Abudy";
```

### Features

* Block-scoped
* Can be reassigned
* Cannot be redeclared in the same scope
* Has a Temporal Dead Zone (TDZ)
* Hoisted

### Example

```javascript
let score = 10;

score = 15; // Allowed
```

---

## 4. `const`

Used for variables whose binding should not change.

### Syntax

```javascript
const PI = 3.14159;
```

### Features

* Block-scoped
* Cannot be reassigned
* Cannot be redeclared
* Must be initialized during declaration
* Has a Temporal Dead Zone (TDZ)
* Hoisted

### Example

```javascript
const country = "Ethiopia";
```

This is invalid:

```javascript
const country; // Error
```

---

### Important Note About Objects and Arrays

`const` prevents reassignment of the variable itself, not modification of its contents.

```javascript
const numbers = [1, 2, 3];

numbers.push(4); // Allowed
```

But:

```javascript
numbers = [5, 6, 7]; // Error
```

---

## 5. `var`

The old way to declare variables before ES6.

### Syntax

```javascript
var city = "Addis Ababa";
```

### Features

* Function-scoped
* Can be reassigned
* Can be redeclared
* Hoisted and initialized with `undefined`
* No Temporal Dead Zone

### Example

```javascript
var count = 1;

count = 2; // Allowed

var count = 3; // Also allowed
```

---

## 6. Scope

Scope determines where a variable can be accessed.

### Global Scope

Accessible everywhere.

```javascript
let name = "Abudy";

function show() {
  console.log(name);
}
```

---

### Block Scope

Variables declared with `let` and `const` exist only inside `{}`.

```javascript
{
  let x = 10;
  const y = 20;
}

console.log(x); // Error
console.log(y); // Error
```

---

### Function Scope

`var` exists throughout the function.

```javascript
function demo() {
  var x = 10;
}

console.log(x); // Error
```

---

## 7. Hoisting

Hoisting is JavaScript's behavior of moving declarations to the top of their scope before execution.

### Important Rule

Only the **declarations** are hoisted, not the assignments.

---

### `var` Hoisting

```javascript
console.log(a);

var a = 10;
```

Output:

```text
undefined
```

JavaScript interprets it as:

```javascript
var a;

console.log(a);

a = 10;
```

---

### `let` Hoisting

```javascript
console.log(b);

let b = 10;
```

Output:

```text
ReferenceError
```

---

### `const` Hoisting

```javascript
console.log(c);

const c = 10;
```

Output:

```text
ReferenceError
```

---

## 8. Temporal Dead Zone (TDZ)

The **Temporal Dead Zone** is the period between entering a scope and the point where a `let` or `const` variable is declared.

During this period, the variable exists but cannot be accessed.

```javascript
{
  console.log(score);

  let score = 100;
}
```

Output:

```text
ReferenceError: Cannot access 'score' before initialization
```

---

### Visual Representation

```text
Enter Scope
     │
     ▼
┌───────────────┐
│      TDZ      │
└───────────────┘
     │
let score = 100;
     │
     ▼
Variable usable
```

---

## 9. Declaration Rules Comparison

| Feature         | `var`    | `let` | `const` |
| --------------- | -------- | ----- | ------- |
| Scope           | Function | Block | Block   |
| Hoisted         | ✅        | ✅     | ✅       |
| TDZ             | ❌        | ✅     | ✅       |
| Reassignable    | ✅        | ✅     | ❌       |
| Redeclarable    | ✅        | ❌     | ❌       |
| Must initialize | ❌        | ❌     | ✅       |

---

## 10. Examples

### `var`

```javascript
var age = 20;

age = 21;

var age = 22;
```

Valid.

---

### `let`

```javascript
let age = 20;

age = 21;
```

Valid.

```javascript
let age = 20;
let age = 21;
```

Error.

---

### `const`

```javascript
const age = 20;
```

Valid.

```javascript
age = 21;
```

Error.

---

## 11. Which One Should You Use?

### Use `const` by default

```javascript
const taxRate = 0.15;
```

### Use `let` when the value changes

```javascript
let counter = 0;

counter++;
```

### Avoid `var`

Modern JavaScript rarely uses `var` because it can cause confusing bugs.

---

## 12. Quick Summary

```text
Declaration   → Creating a variable
Assignment    → Giving it a value
Initialization→ Declaration + Assignment together
Reassignment  → Changing the value
Redeclaration → Creating the same variable again
Hoisting      → Declarations move to the top of scope
TDZ           → Restricted area before let/const initialization
```

### Recommended Rule

```text
const → default choice
let   → if value changes
var   → avoid in modern JavaScript
```
