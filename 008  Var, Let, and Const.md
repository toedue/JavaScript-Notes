# JavaScript Notes / Var, Let, and Const

Hey! Let’s dive into the world of variable declarations in JavaScript with `var`, `let`, and `const`. These are the ways we set up variables, and they each have their own personality. Let’s break it down like we’re just hanging out!

## Var
- **Redeclare**: Yep, you can redeclare it! Like `var x = 1; var x = 2;`—it just overwrites the old value. Handy but can cause mix-ups.
- **Access Before Declare**: If you use it before declaring, you get `undefined`. JavaScript hoists it to the top but doesn’t set the value yet.
- **Variable Scope Drama**: It gets added to the global `window` object if declared outside a function, which can lead to unexpected clashes.
- **Block or Function Scope**: Only cares about function scope, not blocks like `{}`—so it leaks out!

#### Example:
```javascript
/*
  Var Example
  - Showing redeclare, access before, and scope.
*/

console.log(x) // undefined - hoisted but not set
var x = 5
var x = 10 // Redeclares fine
console.log(x) // 10
```

---

## Let
- **Redeclare**: Nope, can’t do it in the same scope—throws an error if you try `let x = 1; let x = 2;`.
- **Access Before Declare**: Big no-no! Trying to use it before declaration (temporal dead zone) crashes with an error.
- **Variable Scope Drama**: Stays out of the global `window` mess—keeps things local and safe.
- **Block or Function Scope**: Loves block scope (`{}`), so it’s contained within ifs, loops, etc.

#### Example:
```javascript
/*
  Let Example
  - Showing no redeclare and block scope.
*/

// console.log(y) // Error - can’t access before declaration
let y = 5
// let y = 10 // Error - can’t redeclare in same scope
if (true) {
  let y = 15
  console.log(y) // 15
}
console.log(y) // 5 - different block
```

---

## Const
- **Redeclare**: Not a chance—same as `let`, trying `const x = 1; const x = 2;` will error out.
- **Access Before Declare**: Same deal as `let`—hits the temporal dead zone, so you’ll get an error if you try before declaring.
- **Variable Scope Drama**: Like `let`, it avoids the global `window` chaos and stays local.
- **Block or Function Scope**: All about block scope, just like `let`, and keeps things tidy.

#### Example:
```javascript
/*
  Const Example
  - Showing no redeclare and block scope.
*/

// console.log(z) // Error - can’t access before
const z = 5
// const z = 10 // Error - can’t redeclare
if (true) {
  const z = 15
  console.log(z) // 15
}
console.log(z) // 5 - different block
```

---
