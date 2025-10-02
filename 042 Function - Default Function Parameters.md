## Function - Default Function Parameters

### 1. Default Function Parameters
- What it is: Allows you to specify default values for parameters if no argument or `undefined` is passed.
- Introduced: ES6 (2015) makes it cleaner than older methods.
- Use it: To avoid errors or provide sensible defaults.

### 2. Function Parameters Default [Undefined]
- Behavior: If a parameter is omitted or explicitly set to `undefined`, the default value kicks in.
- Old Problem: Before ES6, you had to check and assign defaults manually.

### 3. Old Strategies [Condition + Logical Or]
- **Condition**: Use an `if` statement to set a default if the parameter is `undefined`.
- **Logical Or (`||`)**: Use the OR operator to pick the parameter or a default if it’s falsy (e.g., `undefined`, `0`, `""`).
- Limitation: `||` treats `0` or `""` as falsy, which might not always be desired.

### 4. ES6 Method
- What it does: Directly assign default values in the parameter list (e.g., `param = value`).
- Advantage: More concise and only triggers on `undefined`, not other falsy values.

#### Example:
- We’ll create a function with default parameters and show old vs. new approaches.

#### Code:
```javascript
/*
  Default Function Parameters Example
  - Using ES6 defaults with commented old strategies.
*/

function sayHello(username = "Unknown", age = "Unknown") {
  // if (age === undefined) {
  //   age = "Unknown";
  // }
  // age = age || "Unknown";
  return `Hello ${username} Your Age Is ${age}`;
}

console.log(sayHello()); // "Hello Unknown Your Age Is Unknown"
```

#### What Happens:
- **ES6 Default**: `username = "Unknown"` and `age = "Unknown"` are set if no arguments or `undefined` are passed.
- **Call**: `sayHello()` passes no arguments, so defaults are used.
- **Output**: `"Hello Unknown Your Age Is Unknown"`.
- **Commented Old Ways**:
  - **Condition**: `if (age === undefined) age = "Unknown";` would manually set the default.
  - **Logical Or**: `age = age || "Unknown";` would work but also replace `0` or `""` with "Unknown".

#### Testing Variations:
```javascript
console.log(sayHello("Osama")); // "Hello Osama Your Age Is Unknown"
console.log(sayHello("Ali", 25)); // "Hello Ali Your Age Is 25"
console.log(sayHello("Sayed", undefined)); // "Hello Sayed Your Age Is Unknown"
```

---


- **ES6 Precision**: Use `= value` for defaults—it only applies to `undefined`, not `null`, `0`, or `""`.
- **Old Ways**: `||` is quick but risky with falsy values; conditions are safer but verbose.
- **Multiple Params**: Set defaults for all or some parameters—later ones can depend on earlier ones (e.g., `age = username ? 20 : 30`).
- **Readability**: Default params make intent clear at a glance.
