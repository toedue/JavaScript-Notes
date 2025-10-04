
## Conditional (Ternary) Operator

### What It Is
- Syntax: `condition ? valueIfTrue : valueIfFalse`
- What it does: Checks a condition and returns one value if true, another if false.
- Use it: Perfect for quick decisions or setting variables.

#### Example Setup:
```javascript
/*
  Ternary Operator Example
  - Using with gender, age, and name.
*/

let theName = "Mona"
let theGender = "Female"
let theAge = 30
```

---

### Basic Replacement for If-Else
- Old way with `if`:
```javascript
if (theGender === "Male") {
  console.log("Mr")
} else {
  console.log("Mrs")
}
```
- Ternary way:
```javascript
/*
  Basic Ternary Example
  - Replacing if-else with ? :
*/

theGender === "Male" ? console.log("Mr") : console.log("Mrs") // Logs "Mrs"
```

---

### Storing Result
- You can save the result in a variable for later use.

#### Example:
```javascript
/*
  Storing Ternary Result
  - Saving the title in a variable.
*/

let result = theGender === "Male" ? "Mr" : "Mrs"
document.write(result) // Writes "Mrs" to the page
```

---

### Inline Logging
- Use it directly in `console.log()`.

#### Example:
```javascript
/*
  Inline Ternary Example
  - Logging directly with ternary.
*/

console.log(theGender === "Male" ? "Mr" : "Mrs") // Logs "Mrs"
```

---

### In Template Literals
- Embed it inside a string for dynamic output.

#### Example:
```javascript
/*
  Ternary in Template Literal
  - Adding title to a greeting.
*/

console.log(`Hello ${theGender === "Male" ? "Mr" : "Mrs"} ${theName}`) // Logs "Hello Mrs Mona"
```

---

### Nested Ternary
- Chain ternaries for multiple conditions (like nested `if`s).

#### Example:
```javascript
/*
  Nested Ternary Example
  - Checking age ranges.
*/

theAge < 20
  ? console.log(20)                   // if age < 20
  : theAge > 20 && theAge < 60
  ? console.log("20 To 60")           // else if (20 < age < 60)
  : theAge > 60
  ? console.log("Larger Than 60")     // else if (age > 60)
  : console.log("Unknown");           // else  Logs "20 To 60" (30 is between 20 and 60)
```

---


- **Compact**: Ternary shines for simple choices—keep it readable!
- **Nesting**: Okay for a few levels, but too many get hard to follow (use `if` instead).
- **Assignment**: Great for setting variables based on conditions.
- **Debug**: Add `console.log()` inside to trace the flow if needed.
