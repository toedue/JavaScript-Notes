
## Object - Create Object With Create Method

### What It Is
- **Definition**: `Object.create()` creates a new object with a specified prototype object and optional properties. It allows you to set up inheritance by linking the new object’s prototype to another object.
- **Syntax**: `Object.create(prototype, [propertiesObject])`
  - **prototype**: The object to use as the prototype (can be `null` or an object).
  - **propertiesObject**: Optional object defining additional properties (using descriptors like `value`, `writable`, etc.).
- **Use It**: To implement prototypal inheritance or create objects with a predefined prototype.

### Key Features
- **Prototype Chain**: The new object inherits properties and methods from the prototype.
- **Flexibility**: Can start with an empty prototype or inherit from an existing object.
- **Own vs Inherited**: Own properties are added directly; inherited ones come from the prototype.

#### Example:
- We’ll create a `user` object, use `Object.create()` to make a new object and a copy with inheritance, and test the results.

#### Code:
```javascript
/*
  Object.create() Example
  - Creating and inheriting objects with prototypes.
*/

let user = {
  age: 20,
  doubleAge: function () {
    return this.age * 2
  },
}

console.log(user) // {age: 20, doubleAge: ƒ}
console.log(user.age) // 20
console.log(user.doubleAge()) // 40

let obj = Object.create({})

obj.a = 100

console.log(obj) // {a: 100}

let copyObj = Object.create(user)

copyObj.age = 50

console.log(copyObj) // {age: 50}
console.log(copyObj.age) // 50
console.log(copyObj.doubleAge()) // 100
```

#### What Happens:
- **Original Object (`user`)**:
  - `user` has `age: 20` and `doubleAge: function() { return this.age * 2 }`.
  - `console.log(user)` logs `{age: 20, doubleAge: ƒ}`.
  - `console.log(user.age)` logs `20`.
  - `console.log(user.doubleAge())` logs `40` (20 * 2).

- **Empty Prototype (`obj`)**:
  - `let obj = Object.create({})` creates an object with an empty object as its prototype.
  - `obj.a = 100` adds an own property.
  - `console.log(obj)` logs `{a: 100}`.

- **Inherited Object (`copyObj`)**:
  - `let copyObj = Object.create(user)` creates an object with `user` as its prototype.
  - `copyObj.age = 50` adds an own `age` property, shadowing the prototype’s `age`.
  - `console.log(copyObj)` logs `{age: 50}` (own properties only).
  - `console.log(copyObj.age)` logs `50` (own property).
  - `console.log(copyObj.doubleAge())` logs `100` (50 * 2), using `copyObj.age` because `this` inside `doubleAge` refers to `copyObj`.

---

### Prototype Chain Explanation
- **Inheritance**: `copyObj` inherits `doubleAge` from `user`’s prototype.
- **Property Resolution**: JavaScript looks for `age` in `copyObj` first (finds 50), then in `user` (20) if not found—but `doubleAge` uses `this.age`, which is `copyObj.age`.
- **Check Prototype**: `console.log(Object.getPrototypeOf(copyObj) === user)` would log `true`.

#### Test Prototype Access:
```javascript
console.log(copyObj.hasOwnProperty("age")) // true (own property)
console.log(copyObj.hasOwnProperty("doubleAge")) // false (inherited)
console.log(Object.getPrototypeOf(copyObj).doubleAge()) // 40 (using user's age)
```

---

## Quick Tips
- **Prototype**: Use `null` for no prototype (`Object.create(null)`), or an object for inheritance.
- **Own Properties**: Added with `obj.key = value` override prototype values.
- **Method Context**: `this` in methods depends on the calling object (e.g., `copyObj.doubleAge()` uses `copyObj`’s `age`).
- **Descriptors**: Add `propertiesObject` for advanced control (e.g., `Object.create(user, { newProp: { value: "Test", writable: true } })`).
