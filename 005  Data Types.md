## Data Types Intro

### 1. String
- What it is: Text stuff, like words or sentences, always wrapped in quotes (single or double).
- When to use it: For names, messages, or anything texty.
- Fun fact: You can check its type with `typeof`.

#### Example:
```javascript
/*
  String Example
  - Logging a name and checking its type.
*/

console.log("Osama Mohamed")
console.log(typeof "Osama Mohamed") // Should say "string"
```

---

### 2. Number
- What it is: Any number, whether it’s a whole number (like 5000) or a decimal (like 5000.99).
- When to use it: For counting, math, or anything numeric.
- Cool bit: `typeof` works here too!

#### Example:
```javascript
/*
  Number Example
  - Logging integers and decimals with their types.
*/

console.log(typeof 5000) // Should say "number"
console.log(typeof 5000.99) // Still "number"
```

---

### 3. Array (which is an Object)
- What it is: A list of things, like [10, 15, 17], and guess what? Under the hood, it’s treated as an object!
- When to use it: When you’ve got a bunch of related items to keep together.
- Heads up: `typeof` will say "object" even though it’s an array.

#### Example:
```javascript
/*
  Array Example
  - Logging an array and its type.
*/

console.log(typeof [10, 15, 17]) // Says "object"
```

---

### 4. Object
- What it is: A collection of key-value pairs, like { name: "Osama", age: 17, country: "Eg" }—kinda like a mini database.
- When to use it: For storing detailed info about something, like a person or product.
- Note: `typeof` calls it "object" too.

#### Example:
```javascript
/*
  Object Example
  - Logging an object and its type.
*/

console.log(typeof { name: "Osama", age: 17, country: "Eg" }) // Says "object"
```

---

### 5. Boolean
- What it is: Just true or false—simple yes/no values.
- When to use it: For decisions in your code, like if something is on or off.
- Quick tip: `typeof` will tell you it’s "boolean".

#### Example:
```javascript
/*
  Boolean Example
  - Logging true and false with their types.
*/

console.log(typeof true) // Says "boolean"
console.log(typeof false) // Also "boolean"
```

---

### 6. Undefined
- What it is: A variable that’s been declared but not given a value yet.
- When to use it: You don’t really “use” it—it just happens when you forget to set something.
- Check it: `typeof` says "undefined".

#### Example:
```javascript
/*
  Undefined Example
  - Logging the type of an undefined value.
*/

console.log(typeof undefined) // Says "undefined"
```

---

### 7. Null
- What it is: A special value meaning “nothing” or “no value”—kinda weird, right?
- When to use it: When you want to explicitly say a variable has no value.
- Tricky part: `typeof` says "object" here, which is a long-standing JavaScript quirk!

#### Example:
```javascript
/*
  Null Example
  - Logging the type of null.
*/

console.log(typeof null) // Says "object" (yep, a bug in JS!)
```
