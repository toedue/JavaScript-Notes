## Object - Create With New Keyword `new Object()`

### What It Is
- **Definition**: The `new Object()` constructor creates a new object instance, which can be initialized with properties using an object literal.
- **Syntax**: `let obj = new Object({ key: value });` or `let obj = new Object();` (properties added later).
- **Use It**: An alternative to the object literal `{}` syntax, useful for dynamic object creation or when working with constructor patterns.
- **Note**: Less concise than `{}` but functionally equivalent for simple cases.

### Key Features
- **Initialization**: Can pass an object literal to set initial properties.
- **Extensibility**: Properties and methods can be added or modified after creation.
- **Prototype**: Inherits from `Object.prototype`, like objects created with `{}`.

#### Example:
- We’ll create a `user` object with `new Object()`, modify it, and log the results.

#### Code:
```javascript
/*
  Object Creation With new Object() Example
  - Creating, modifying, and accessing an object.
*/

let user = new Object({
  age: 20,
})

console.log(user) // {age: 20}

user.age = 38
user["country"] = "Egypt"

user.sayHello = function () {
  return `Hello`
}

console.log(user) // {age: 38, country: "Egypt", sayHello: ƒ}
console.log(user.age) // 38
console.log(user.country) // "Egypt"
console.log(user.sayHello()) // "Hello"
```

#### What Happens:
- **Creation**:
  - `new Object({ age: 20 })` creates a new object with an initial `age` property set to `20`.
  - `console.log(user)` logs `{age: 20}`.

- **Modification**:
  - `user.age = 38` updates the `age` property to `38`.
  - `user["country"] = "Egypt"` adds a `country` property using bracket notation.
  - `user.sayHello = function() { return `Hello`; }` adds a method.

- **Accessing**:
  - `console.log(user)` logs the updated object `{age: 38, country: "Egypt", sayHello: ƒ}`.
  - `console.log(user.age)` logs `38`.
  - `console.log(user.country)` logs `"Egypt"`.
  - `console.log(user.sayHello())` executes the method, logging `"Hello"`.

---

### Comparison to Object Literal `{}`
- **Literal**: `let user = { age: 20 };` is shorter and more common.
- **Constructor**: `new Object({ age: 20 })` is more explicit, useful in constructor-heavy code or when dynamically building objects.
- **Functionality**: Both create objects with the same prototype and behavior.

#### Dynamic Example:
```javascript
let prop = "age"
let value = 25
let dynamicUser = new Object()
dynamicUser[prop] = value
console.log(dynamicUser) // {age: 25}
```

---


- **Preference**: Use `{}` for simplicity unless you need the constructor pattern.
- **Dynamic Addition**: Bracket notation (`user[key]`) is great for adding properties with variables.
- **Method Context**: Inside `sayHello`, `this` refers to `user` (e.g., `this.age` would be `38`).
- **Empty Start**: `let obj = new Object();` creates an empty object, populated later.
