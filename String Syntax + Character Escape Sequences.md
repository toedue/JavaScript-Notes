## String Syntax + Character Escape Sequences

### 1. String Syntax
- What it is: Strings are text wrapped in single (`'`) or double (`"`) quotes. You can mix them up to avoid confusion!
- Tip: Use one style for the outside and the other inside if you’ve got quotes in your text.

#### Examples:
```javascript
/*
  String Syntax Examples
  - Mixing single and double quotes.
*/

console.log('Elzero Web "School"') // Single outside, double inside
console.log("Elzero Web 'School'") // Double outside, single inside
```

---

### 2. \ Escape + Line Continue
- What it does: The backslash (`\`) is your escape buddy! It lets you use quotes inside strings or continue a line without breaking it.
- How it works: Put `\` before a quote to include it, or use it at the end of a line to keep going on the next one.

#### Examples:
```javascript
/*
  Escape and Line Continue Examples
  - Using \ to escape quotes and continue lines.
*/

console.log("Elzero Web \"School\"") // Escapes the double quote
console.log('Elzero \\ Web \'School\'') // Escapes both backslash and single quote
console.log("Elzero \
Web \
School") // Continues the string across lines
```

---

### 3. \n (New Line)
- What it does: The `\n` escape sequence adds a new line—perfect for breaking text into multiple lines in the output.
- When to use it: Great for formatting logs or messages to look neat.

#### Example:
```javascript
/*
  \n Example
  - Adding new lines to the output.
*/

console.log("Elzero\nWeb\nSchool") // Prints each word on a new line
```

---
