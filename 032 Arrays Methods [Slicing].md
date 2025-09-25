## Arrays Methods [Slicing]

### 1. slice(Start [Opt], End [Opt] Not Including End)
- What it does: Creates a new array by extracting a section from the original, from `Start` to `End` (not including `End`).
- Details:
  - `slice()` alone: Copies the entire array.
  - `Start` undefined: Defaults to 0.
  - Negative indices: Counts from the end.
  - `End` undefined or > `length`: Goes to the end.
  - Returns: A new array, leaving the original untouched.

#### Examples:
```javascript
/*
  slice Examples
  - Extracting parts of the array.
*/

let myFriends = ["Ahmed", "Sayed", "Ali", "Osama", "Gamal", "Ameer"]
console.log(myFriends) // ["Ahmed", "Sayed", "Ali", "Osama", "Gamal", "Ameer"]

console.log(myFriends.slice()) // ["Ahmed", "Sayed", "Ali", "Osama", "Gamal", "Ameer"] (full copy)
console.log(myFriends.slice(1)) // ["Sayed", "Ali", "Osama", "Gamal", "Ameer"] (from index 1 to end)
console.log(myFriends.slice(1, 3)) // ["Sayed", "Ali"] (from 1 to 3, not including 3)
console.log(myFriends.slice(-3)) // ["Osama", "Gamal", "Ameer"] (last 3 elements)
console.log(myFriends.slice(1, -2)) // ["Sayed", "Ali", "Osama"] (from 1 to second-to-last)
console.log(myFriends.slice(-4, -2)) // ["Ali", "Osama"] (from fourth-to-last to second-to-last)
console.log(myFriends) // ["Ahmed", "Sayed", "Ali", "Osama", "Gamal", "Ameer"] (original unchanged)
```

---

### 2. splice(Start [Mand], DeleteCount [Opt] [0 No Remove], The Items To Add [Opt])
- What it does: Modifies the original array by removing or replacing elements and optionally adding new ones.
- Details:
  - `Start`: Mandatory index to begin.
  - `DeleteCount`: How many to remove (0 to add without removing).
  - Items to Add: Optional elements to insert at `Start`.
  - Negative `Start`: Counts from the end.
  - Returns: Array of removed elements.

#### Example:
```javascript
/*
  splice Example
  - Removing and adding elements.
*/

myFriends.splice(1, 2, "Sameer", "Samara")
console.log(myFriends) // ["Ahmed", "Sameer", "Samara", "Osama", "Gamal", "Ameer"]
// Removes 2 elements from index 1 ("Sayed", "Ali") and adds "Sameer", "Samara"
```

---


- **slice()**: Non-destructive—perfect for copying or extracting without altering the original.
- **Negative Indices**: `-1` is the last element, `-2` second-to-last, etc.
- **splice()**: Destructive—changes the array, so use it when you want to modify.
- **No Delete**: Set `DeleteCount` to 0 in `splice()` to just add items.
- **Return**: `splice()` returns the removed items—save it if needed (e.g., `let removed = myFriends.splice(...)`).
