## Identifiers

### 1. Name Conventions and Rules
- What they are: Identifiers are the names you create for variables, functions, etc. There are some guidelines to keep things smooth.
- Rules to follow:
  - Start with a letter, underscore (`_`), or dollar sign (`$`)—no numbers at the start.
  - Use letters, numbers, underscores, or dollar signs after the first character.
  - No spaces or special characters like `@` or `#`.
  - Case matters! `userName` and `username` are different.
  - Keep it descriptive—`userName` beats `x` any day!
- Tips: CamelCase (like `userName`) is super common in JavaScript.

#### Example:
```javascript
/*
  Identifier Example
  - A nice variable name following the rules.
*/

var userName = "Sayed"
console.log(userName)
```

---

### 2. Reserved Words
- What they are: Words JavaScript already uses for its own stuff, like `var`, `if`, `for`, `function`, etc. You can’t use these as identifiers.
- Why it matters: If you try, you’ll get errors or weird behavior—JavaScript gets confused!
- Some examples: `let`, `const`, `class`, `return`, `this`—there’s a whole list, so it’s good to avoid them.
- Tip: Stick to unique names like `myVariable` instead of `for`.

#### Example (What NOT to do):
```javascript
/*
  Reserved Word Example (Avoid this!)
  - Don’t use reserved words like 'var' as names.
*/

// This will cause issues!
var var = "Test" // Nope, 'var' is reserved!
console.log(var)
```

#### Better Example:
```javascript
/*
  Safe Identifier Example
  - Using a non-reserved name instead.
*/

var myVar = "Test"
console.log(myVar)
```

---
