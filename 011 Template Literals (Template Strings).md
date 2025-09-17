## Template Literals (Template Strings)

### First Example
- What it is: Template literals let you mix variables right into strings with `${}` instead of the old `+` mess. Plus, you can add new lines with `\n` or just let the backticks handle it!
- Why it’s awesome: Cleaner code and no need to escape quotes manually.

#### Examples:
```javascript
/*
  First Template Literal Example
  - Combining strings with old + method vs. template literals.
*/

let a = "We Love"
let b = "JavaScript"
let c = "And"
let d = "Programming"

console.log(a + " \"\" " + b + "\n" + c + " " + d) // Old way with + and \n
console.log(`${a} "" '' \\ ${b}
${c} ${d}`) // Template literal way, multi-line and embedded
```

---

### Second Example
- What it does: You can build HTML or multi-line text directly with template literals, tossing variables in with `${}`. It’s perfect for creating markup on the fly!
- When to use it: Great for dynamic web content or readable logs.

#### Example:
```javascript
/*
  Second Template Literal Example
  - Creating HTML with embedded variables.
*/

let title = "Elzero"
let desc = "Elzero Web School"

let markup = `
  <div class="card">
    <div class="child">
      <h2>${title}</h2>
      <p>${desc}</p>
    </div>
  </div>
`

document.write(markup) // Writes the HTML to the page
```

---
