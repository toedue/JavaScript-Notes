Non-Primitive Data Types: `Date`, `Map`, `Set`, and Objects

## What Are Non-Primitive Data Types?

Non-primitive (reference) data types store collections of values or more complex data.

Unlike primitive values, they are **stored by reference**.

Examples:

* Object
* Array
* Function
* Date
* Map
* Set

---

## Primitive vs Non-Primitive

| Feature   | Primitive               | Non-Primitive                 |
| --------- | ----------------------- | ----------------------------- |
| Stored by | Value                   | Reference                     |
| Mutable   | ❌                       | ✅                             |
| Examples  | String, Number, Boolean | Object, Array, Date, Map, Set |

### Example

```javascript
const user1 = { name: "Abudy" };
const user2 = user1;

user2.name = "Ali";

console.log(user1.name); // "Ali"
```

Both variables refer to the same object.

---

# 1. Object

An object stores data as **key-value pairs**.

## Syntax

```javascript
const person = {
  name: "Abudy",
  age: 20,
};
```

## Accessing Properties

```javascript
console.log(person.name);      // "Abudy"
console.log(person["age"]);    // 20
```

## Adding Properties

```javascript
person.city = "Addis Ababa";
```

## Updating Properties

```javascript
person.age = 21;
```

## Deleting Properties

```javascript
delete person.city;
```

---

# 2. Array

An array stores an ordered collection of values.

## Syntax

```javascript
const colors = ["red", "green", "blue"];
```

## Accessing Elements

```javascript
console.log(colors[0]); // "red"
```

## Common Methods

```javascript
colors.push("yellow");
colors.pop();
colors.shift();
colors.unshift("black");
```

---

# 3. Function

Functions are reusable blocks of code.

## Example

```javascript
function greet(name) {
  return `Hello, ${name}`;
}
```

Functions are objects in JavaScript.

```javascript
console.log(typeof greet); // "function"
```

---

# 4. `Date`

The `Date` object represents dates and times.

## Creating a Date

### Current Date and Time

```javascript
const now = new Date();

console.log(now);
```

---

### Specific Date

```javascript
const birthday = new Date("2026-06-20");
```

---

### Using Numbers

```javascript
const date = new Date(2026, 5, 20);
```

> Months are zero-based.

```text
0 = January
1 = February
...
5 = June
```

---

## Useful Date Methods

```javascript
const now = new Date();
```

| Method          | Description              |
| --------------- | ------------------------ |
| `getFullYear()` | Get the year             |
| `getMonth()`    | Get the month (0–11)     |
| `getDate()`     | Get the day of the month |
| `getDay()`      | Get the weekday (0–6)    |
| `getHours()`    | Get the hour             |
| `getMinutes()`  | Get the minutes          |
| `getSeconds()`  | Get the seconds          |

### Examples

```javascript
console.log(now.getFullYear());
console.log(now.getMonth());
console.log(now.getDate());
```

---

## Converting Dates to Strings

```javascript
console.log(now.toDateString());
console.log(now.toLocaleDateString());
console.log(now.toLocaleTimeString());
```

---

## Getting a Timestamp

```javascript
console.log(Date.now());
```

Returns the number of milliseconds since:

```text
January 1, 1970 (UTC)
```

---

# 5. `Map`

A `Map` stores key-value pairs, similar to objects, but with more flexibility.

## Why Use `Map`?

* Keys can be any data type.
* Maintains insertion order.
* Provides useful built-in methods.

---

## Creating a Map

```javascript
const user = new Map();
```

---

## Adding Entries

```javascript
user.set("name", "Abudy");
user.set("age", 20);
```

---

## Using Non-String Keys

```javascript
const key = { id: 1 };

user.set(key, "Admin");
```

---

## Getting Values

```javascript
console.log(user.get("name"));
```

---

## Checking Keys

```javascript
console.log(user.has("age"));
```

---

## Deleting Entries

```javascript
user.delete("age");
```

---

## Size of a Map

```javascript
console.log(user.size);
```

---

## Clearing a Map

```javascript
user.clear();
```

---

## Iterating Through a Map

```javascript
const user = new Map([
  ["name", "Abudy"],
  ["age", 20],
]);

for (const [key, value] of user) {
  console.log(key, value);
}
```

---

## Map vs Object

| Feature         | Map      | Object              |
| --------------- | -------- | ------------------- |
| Key types       | Any type | Strings and Symbols |
| Maintains order | ✅        | Usually             |
| Size property   | ✅        | ❌                   |
| Easy iteration  | ✅        | ❌                   |

---

# 6. `Set`

A `Set` stores unique values.

Duplicate values are automatically removed.

---

## Creating a Set

```javascript
const numbers = new Set();
```

---

## Adding Values

```javascript
numbers.add(10);
numbers.add(20);
numbers.add(10);
```

The duplicate `10` is ignored.

---

## Viewing the Set

```javascript
console.log(numbers);
```

Output:

```text
Set(2) {10, 20}
```

---

## Checking for a Value

```javascript
console.log(numbers.has(20));
```

---

## Removing a Value

```javascript
numbers.delete(10);
```

---

## Getting the Size

```javascript
console.log(numbers.size);
```

---

## Clearing a Set

```javascript
numbers.clear();
```

---

## Iterating Through a Set

```javascript
const colors = new Set(["red", "green", "blue"]);

for (const color of colors) {
  console.log(color);
}
```

---

## Removing Duplicates from an Array

A common use case for `Set`.

```javascript
const values = [1, 2, 2, 3, 3, 4];

const uniqueValues = [...new Set(values)];

console.log(uniqueValues);
```

Output:

```javascript
[1, 2, 3, 4]
```

---

## Set vs Array

| Feature           | Set | Array |
| ----------------- | --- | ----- |
| Allows duplicates | ❌   | ✅     |
| Indexed access    | ❌   | ✅     |
| Maintains order   | ✅   | ✅     |
| Fast lookups      | ✅   | ❌     |

---

# Summary Table

| Type     | Purpose                    | Example               |
| -------- | -------------------------- | --------------------- |
| Object   | Store key-value pairs      | `{ name: "Abudy" }`   |
| Array    | Store ordered values       | `[1, 2, 3]`           |
| Function | Reusable code              | `function greet() {}` |
| Date     | Work with dates and times  | `new Date()`          |
| Map      | Flexible key-value storage | `new Map()`           |
| Set      | Store unique values        | `new Set()`           |

---

# Quick Notes

```text
Objects → General key-value storage

Arrays → Ordered collections

Functions → Reusable code blocks

Date → Handle dates and times

Map → Key-value pairs with any key type

Set → Unique values only
```

```text
Non-primitive data types are:

- Mutable
- Stored by reference
- Compared by reference, not by value
```

Example:

```javascript
console.log({} === {}); // false
console.log([] === []); // false
```

Because each object or array has a different reference in memory.
