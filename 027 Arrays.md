
## Arrays

### 1. Create Arrays [Two Methods]
- **Method 1: Using `[]`**: The easy way—just list items inside square brackets.
- **Method 2: Using `new Array()`**: A constructor way, like `new Array("item1", "item2")`.
- Tip: `[]` is more common and cleaner!

#### Example (Using `[]` in your code):
```javascript
/*
  Create Arrays Example
  - Using [] with a nested array.
*/

let myFriends = ["Ahmed", "Mohamed", "Sayed", ["Marwan", "Ali"]]
```

---

### 2. Access Arrays Elements
- What it does: Use an index (starting at 0) in `[]` to grab an element.
- Nested: Use multiple `[]` for nested arrays (e.g., `myFriends[3][1]`).

#### Example:
```javascript
/*
  Access Arrays Elements Example
  - Grabbing elements and nested ones.
*/

console.log(`Hello ${myFriends[0]}`) // "Hello Ahmed"
console.log(`Hello ${myFriends[2]}`) // "Hello Sayed"
// Note: myFriends[1][2] is undefined (Mohamed has no index 2)
console.log(`Hello ${myFriends[3][1]}`) // "Hello Ali"
// Note: myFriends[3][1][2] is undefined (Ali is a string, no index 2)
console.log(`${myFriends[3][1][2]}`) // undefined
```

---

### 3. Nested Arrays
- What it is: Arrays inside arrays—great for grouping related data.
- Access: Use nested indices like `myFriends[3][1]` for "Ali".

#### Example (From your code):
- `myFriends[3]` is `["Marwan", "Ali"]`, so `myFriends[3][1]` is "Ali".

---

### 4. Change Arrays Elements
- What it does: Assign a new value to an index to update it.
- Nested: You can replace whole nested arrays too.

#### Example:
```javascript
/*
  Change Arrays Elements Example
  - Updating elements and nested arrays.
*/

console.log(myFriends) // ["Ahmed", "Mohamed", "Sayed", ["Marwan", "Ali"]]
myFriends[1] = "Gamal"
console.log(myFriends) // ["Ahmed", "Gamal", "Sayed", ["Marwan", "Ali"]]
myFriends[3] = ["Sameh", "Ameer"]
console.log(myFriends) // ["Ahmed", "Gamal", "Sayed", ["Sameh", "Ameer"]]
```

---

### 5. Check For Array Array.isArray(arr)
- What it does: Returns `true` if the value is an array, `false` if not.
- Use it: To confirm you’re dealing with an array.

#### Example:
```javascript
/*
  Check For Array Example
  - Using Array.isArray().
*/

console.log(Array.isArray(myFriends)) // true
```

---

## Quick Tips
- **Indices**: Start at 0, and watch out for `undefined` if you go too far.
- **Nested Access**: Double-check indices for nested arrays—mistakes like `myFriends[1][2]` (undefined) can trip you up.
- **Mutation**: Arrays are mutable, so changing elements is easy but affects the original.
- **isArray**: Handy for debugging or validating input.

