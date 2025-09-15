## ES6 Basics

### 1. Variable Declaration with `var`
- What it does: The old-school way to declare a variable using `var`. It’s been around forever but has some quirks—like being function-scoped and letting you redeclare stuff.
- When to use it: Still works, but we’re moving to newer ways now. Just here for context!
- Note: You might notice it can cause issues if you’re not careful with scope.

#### Example:
```javascript
/*
  ES6 Example with var
  - Using the old var to set a name.
*/

var myName = "Osama"
console.log("Hello " + myName)
```

---

### 2. Template Literals with `` ` ``
- What it does: A super neat ES6 feature that lets you use backticks (`` ` ``) to create strings. You can embed variables right inside with `${}`—no more messy concatenation!
- When to use it: Perfect for readable strings, especially when you’ve got variables or expressions to toss in.
- Why it’s cool: Makes your code look cleaner and is easier to work with.

#### Example:
```javascript
/*
  ES6 Template Literal Example
  - Using backticks and ${} to insert the name.
*/

console.log(`Hello ${myName}`)
```

---

## Why ES6 Rocks
- ES6 brought template literals to save us from the old `+` string mashups. It’s part of a bunch of updates that make JavaScript more modern and fun to write.
- The `var` thing is still okay, but later we’ll see `let` and `const` which are tighter with scope—more on that another time!
