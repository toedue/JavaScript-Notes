## Object - Nested Object And Trainings

### What It Is
- **Nested Object**: An object within another object, allowing hierarchical data organization.
- **Trainings**: Practicing access methods (dot and bracket notation) and working with arrays and methods inside objects.
- **Use It**: To model complex entities like users with multiple addresses or skills.

#### Example:
- We’ll create a `user` object with nested properties, an array, and a method to check availability.

#### Code:
```javascript
/*
  Nested Object Example
  - Accessing nested properties, arrays, and methods.
*/

let available = true

let user = {
  name: "Osama",
  age: 38,
  skills: ["HTML", "CSS", "JS"],
  available: false,
  addresses: {
    ksa: "Riyadh",
    egypt: {
      one: "Cairo",
      two: "Giza",
    },
  },
  checkAv: function () {
    if (user.available === true) {
      return `Free For Work`
    } else {
      return `Not Free`
    }
  },
}

console.log(user.name) // "Osama"
console.log(user.age) // 38
console.log(user.skills) // ["HTML", "CSS", "JS"]
console.log(user.skills.join(" | ")) // "HTML | CSS | JS"
console.log(user.skills[2]) // "JS" (access with index)
console.log(user.addresses.ksa) // "Riyadh"
console.log(user.addresses.egypt.one) // "Cairo"
console.log(user["addresses"].egypt.one) // "Cairo"
console.log(user["addresses"]["egypt"]) // {one: "Cairo", two: "Giza"}
console.log(user["addresses"]["egypt"]["one"]) // "Cairo"
console.log(user.checkAv()) // "Not Free"
```

#### What Happens:
- **Top-Level Properties**:
  - `user.name` logs `"Osama"`.
  - `user.age` logs `38`.
  - `user.skills` logs the array `["HTML", "CSS", "JS"]`.

- **Array Manipulation**:
  - `user.skills.join(" | ")` joins the array with `" | "` as a separator, logging `"HTML | CSS | JS"`.
  - `user.skills[2]` accesses the third element (index 2), logging `"JS"`.

- **Nested Object Access**:
  - `user.addresses.ksa` logs `"Riyadh"`.
  - `user.addresses.egypt.one` logs `"Cairo"` (deep nesting with dot notation).
  - `user["addresses"].egypt.one` logs `"Cairo"` (bracket notation for the same path).
  - `user["addresses"]["egypt"]` logs the `egypt` object `{one: "Cairo", two: "Giza"}`.
  - `user["addresses"]["egypt"]["one"]` logs `"Cairo"` (fully bracketed path).

- **Method Call**:
  - `user.checkAv()` checks `user.available` (which is `false`, overriding the global `available = true`), logging `"Not Free"`.

---

### Key Points
- **Nested Depth**: Objects can nest as deeply as needed (e.g., `egypt` inside `addresses`).
- **Notation Flexibility**: Dot and bracket notation work for nested access; brackets are essential for dynamic or computed keys.
- **Scope Issue**: `user.checkAv()` uses `user.available` instead of the global `available` due to lexical scope—fixable with `this.available` (see below).
- **Arrays in Objects**: `skills` is an array, accessible like any array with indices or methods.

#### Fixed Method for `this`:
```javascript
checkAv: function () {
  if (this.available === true) {
    return `Free For Work`
  } else {
    return `Not Free`
  }
},
```
- **Why**: `this` refers to the `user` object, ensuring it checks the object’s `available` property.

---


- **Deep Access**: Chain dot or bracket notation (e.g., `user.addresses.egypt.two` or `user["addresses"]["egypt"]["two"]` for "Giza").
- **Dynamic Keys**: Use `let key = "ksa"; console.log(user.addresses[key]);` for runtime flexibility.
- **Method Context**: Use `this` inside methods to refer to the object’s properties.
- **Immutability**: Create copies of nested objects with `JSON.parse(JSON.stringify(user))` if needed.
