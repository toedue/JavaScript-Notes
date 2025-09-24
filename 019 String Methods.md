
## String Methods (Part 1)

### 1. Access With Index
- What it does: Grabs a character using its position (index starts at 0).
- Note: Out of range? You get `undefined`.

#### Example:
```javascript
/*
  Access With Index Example
  - Grabbing characters by position.
*/

let theName = "  Ahmed  ".trim()
console.log(theName[1]) // "h"
console.log(theName[2]) // "m"

```

---

### 2. Access With charAt()
- What it does: Same as index but with a method—returns the character at the given position.
- Bonus: Safer, returns empty string if out of range.

#### Example:
```javascript
/*
  charAt Example
  - Accessing characters with method.
*/

console.log(theName.charAt(1)) // "h"
console.log(theName.charAt(5)) // "m"
```

---

### 3. length
- What it does: Tells you how many characters are in the string, including spaces.
- Tip: Great for looping or checking size.

#### Example:
```javascript
/*
  length Example
  - Counting characters.
*/

console.log(theName.length) // 9 (including spaces)
```

---

### 4. trim()
- What it does: Strips off whitespace from both ends of the string.
- Handy: Cleans up user input!

#### Example:
```javascript
/*
  trim Example
  - Removing leading and trailing spaces.
*/

console.log(theName.trim()) // "Ahmed"
```

---

### 5. toUpperCase()
- What it does: Turns all characters to uppercase.
- Simple: Quick way to standardize text.

#### Example:
```javascript
/*
  toUpperCase Example
  - Converting to uppercase.
*/

console.log(theName.toUpperCase()) // "  AHMED  "
```

---

### 6. toLowerCase()
- What it does: Turns all characters to lowercase.
- Useful: For case-insensitive checks.

#### Example:
```javascript
/*
  toLowerCase Example
  - Converting to lowercase.
*/

console.log(theName.toLowerCase()) // "  ahmed  "
```

---

### 7. Chain Methods
- What it does: Link methods together (e.g., `trim().charAt().toUpperCase()`).
- Cool: Saves steps and keeps it clean.

#### Example:
```javascript
/*
  Chain Methods Example
  - Combining trim, charAt, and toUpperCase.
*/

console.log(theName.trim().charAt(2).toUpperCase()) // "M"
```

---

## String Methods (Part 2)

### 1. indexOf(Value [Mand], Start [Opt] 0)
- What it does: Finds the first spot where a value appears, starting from an optional position.
- Returns: Position or -1 if not found.

#### Example:
```javascript
/*
  indexOf Example
  - Finding positions of "Web" and "o".
*/

let a = "Elzero Web School"
console.log(a.indexOf("Web")) // 7
console.log(a.indexOf("Web", 8)) // -1 (starts after)
console.log(a.indexOf("o")) // 5
```

---

### 2. lastIndexOf(Value [Mand], Start [Opt] Length)
- What it does: Finds the last spot of a value, starting from the end or a given position.
- Returns: Last position or -1.

#### Example:
```javascript
/*
  lastIndexOf Example
  - Finding last "o".
*/

console.log(a.lastIndexOf("o")) // 15
```

---

### 3. slice(Start [Mand], End [Opt] Not Include End)
- What it does: Cuts out a piece of the string from start to end (end not included).
- Negative: Counts from the end with negatives.

#### Example:
```javascript
/*
  slice Example
  - Extracting substrings.
*/

console.log(a.slice(2, 6)) // "zero"
console.log(a.slice(-5, -3)) // "oo"
```

---

### 4. repeat(Times) [ES6]
- What it does: Repeats the string a set number of times.
- Fun: Great for patterns!

#### Example:
```javascript
/*
  repeat Example
  - Repeating the string.
*/

console.log(a.repeat(5)) // "Elzero Web School" x5
```

---

### 5. split(Separator [Opt], Limit [Opt])
- What it does: Splits a string into an array, using a separator (or none for characters).
- Limit: Caps the number of splits.

#### Example:
```javascript
/*
  split Example
  - Splitting into characters with limit.
*/

console.log(a.split("", 6)) // ["E", "l", "z", "e", "r", "o"]
```

---

## String Methods (Part 3)

### 1. substring(Start [Mand], End [Opt] Not Including End)
- What it does: Similar to `slice()`, but swaps start/end if start > end, and negative starts become 0.
- Length trick: Use with `.length` for the end.

#### Example:
```javascript
/*
  substring Example
  - Extracting with swapping and length.
*/

let a = "Elzero Web School"
console.log(a.length) // 17
console.log(a.substring(2, 6)) // "zero"
console.log(a.substring(6, 2)) // "zero" (swaps)
console.log(a.substring(-10, 6)) // "Elzero" (starts at 0)
console.log(a.substring(a.length - 5, a.length - 3)) // "oo"
```

---

### 2. substr(Start [Mand], Characters To Extract)
- What it does: Starts at a position and grabs a set number of characters.
- Negative: Counts from the end.
- Limit: Returns empty if start >= length.

#### Example:
```javascript
/*
  substr Example
  - Extracting with start and length.
*/

console.log(a.substr(0, 6)) // "Elzero"
console.log(a.substr(17)) // "" (beyond length)
console.log(a.substr(-3)) // "ool"
console.log(a.substr(-5, 2)) // "ho"
```

---

### 3. includes(Value [Mand], Start [Opt] Default 0) [ES6]
- What it does: Checks if a value is in the string, returns `true` or `false`.
- Start: Optional position to begin searching.

#### Example:
```javascript
/*
  includes Example
  - Checking for substrings.
*/

console.log(a.includes("Web")) // true
console.log(a.includes("Web", 8)) // false
```

---

### 4. startsWith(Value [Mand], Start [Opt] Default 0) [ES6]
- What it does: Checks if the string starts with a value, from a given start point.
- Returns: `true` or `false`.

#### Example:
```javascript
/*
  startsWith Example
  - Checking the start.
*/

console.log(a.startsWith("E")) // true
console.log(a.startsWith("E", 2)) // false
console.log(a.startsWith("zero", 2)) // true
```

---

### 5. endsWith(Value [Mand], Length [Opt] Default Full Length) [ES6]
- What it does: Checks if the string ends with a value, using an optional length to check.
- Returns: `true` or `false`.

#### Example:
```javascript
/*
  endsWith Example
  - Checking the end.
*/

console.log(a.endsWith("l")) // true
```

---
