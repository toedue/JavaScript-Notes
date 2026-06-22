Understanding **stack memory** and **heap memory** helps explain:

* Why primitive values behave differently from objects
* Why changing one object can affect another variable
* How JavaScript stores variables internally

---

## Two Main Memory Areas

JavaScript uses two types of memory:

```text
Memory
├── Stack
└── Heap
```

---

# 1. Stack Memory

The **stack** stores:

* Primitive values
* Function calls
* References (memory addresses) to objects in the heap

The stack is:

* Fast
* Ordered
* Automatically managed

---

## Primitive Data Types Stored in the Stack

* String
* Number
* Boolean
* Undefined
* Null
* BigInt
* Symbol

Example:

```javascript
let age = 20;
let name = "Abudy";
let isStudent = true;
```

The actual values are stored directly in the stack.

```text
Stack

age ─────────► 20
name ────────► "Abudy"
isStudent ───► true
```

---

## Copying Primitive Values

When you assign one primitive variable to another, JavaScript copies the value.

```javascript
let a = 10;
let b = a;

b = 20;

console.log(a); // 10
console.log(b); // 20
```

### Memory Representation

Before changing `b`:

```text
Stack

a ───► 10
b ───► 10
```

After changing `b`:

```text
Stack

a ───► 10
b ───► 20
```

Changing `b` does not affect `a`.

---

# 2. Heap Memory

The **heap** stores non-primitive data.

Examples:

* Objects
* Arrays
* Functions
* Maps
* Sets
* Dates

The heap is:

* Larger than the stack
* Less organized
* Used for dynamic data

---

## Objects Are Stored in the Heap

```javascript
const person = {
  name: "Abudy",
};
```

The object itself lives in the heap.

The variable `person` stores only a reference (address) in the stack.

### Memory Representation

```text
Stack                  Heap

person ───────► 0x101 ─────► { name: "Abudy" }
```

---

## Copying Objects

When assigning one object variable to another, JavaScript copies the reference, not the object.

```javascript
const user1 = {
  name: "Abudy",
};

const user2 = user1;

user2.name = "Ali";

console.log(user1.name); // "Ali"
console.log(user2.name); // "Ali"
```

### Memory Representation

```text
Stack                  Heap

user1 ───────► 0x101 ─────► { name: "Ali" }

user2 ───────► 0x101
```

Both variables point to the same object.

---

## Arrays in the Heap

```javascript
const numbers = [1, 2, 3];
```

Memory:

```text
Stack                  Heap

numbers ─────► 0x201 ─────► [1, 2, 3]
```

---

## Functions in the Heap

Functions are objects in JavaScript and are stored in the heap.

```javascript
function greet() {
  console.log("Hello");
}
```

Memory:

```text
Stack                  Heap

greet ───────► 0x301 ─────► function
```

---

# Stack vs Heap

| Feature      | Stack                           | Heap                             |
| ------------ | ------------------------------- | -------------------------------- |
| Stores       | Primitive values and references | Objects and other non-primitives |
| Size         | Smaller                         | Larger                           |
| Speed        | Faster                          | Slower                           |
| Organization | Ordered                         | Dynamic                          |
| Access       | Direct                          | Through references               |

---

# Pass by Value vs Pass by Reference

## Primitive Values → Pass by Value

```javascript
let x = 10;
let y = x;

y = 20;
```

`x` remains unchanged.

---

## Objects → Pass by Reference

```javascript
const a = { value: 10 };
const b = a;

b.value = 20;
```

Both `a` and `b` see the change.

---

# Creating Independent Copies

To avoid modifying the original object, create a copy.

## Using the Spread Operator

```javascript
const user1 = {
  name: "Abudy",
};

const user2 = { ...user1 };

user2.name = "Ali";

console.log(user1.name); // "Abudy"
console.log(user2.name); // "Ali"
```

### Memory Representation

```text
Stack                  Heap

user1 ─────► 0x101 ─────► { name: "Abudy" }

user2 ─────► 0x102 ─────► { name: "Ali" }
```

---

## Copying Arrays

```javascript
const arr1 = [1, 2, 3];

const arr2 = [...arr1];
```

---

# The Call Stack

The stack also manages function execution.

When a function is called:

1. A new execution context is pushed onto the stack.
2. When the function finishes, it is removed.

Example:

```javascript
function first() {
  second();
}

function second() {
  console.log("Hello");
}

first();
```

### Execution Flow

```text
Call Stack

┌─────────┐
│ second  │
├─────────┤
│ first   │
├─────────┤
│ Global  │
└─────────┘
```

After `second()` finishes:

```text
Call Stack

┌─────────┐
│ first   │
├─────────┤
│ Global  │
└─────────┘
```

---

# Garbage Collection

JavaScript automatically frees heap memory when objects are no longer reachable.

```javascript
let user = {
  name: "Abudy",
};

user = null;
```

If no references point to the object, the garbage collector removes it from memory.

---

# Common Mistakes

## Comparing Objects

```javascript
console.log({} === {}); // false
```

Each object has a different memory reference.

---

## Sharing References Accidentally

```javascript
const a = [1, 2, 3];
const b = a;

b.push(4);

console.log(a); // [1, 2, 3, 4]
```

---

# Quick Summary

```text
Stack:
- Primitive values
- References
- Function calls
```

```text
Heap:
- Objects
- Arrays
- Functions
- Maps
- Sets
- Dates
```

```text
Primitives → copied by value

Objects → copied by reference
```

```text
Stack = fast and ordered

Heap = dynamic and flexible
```
