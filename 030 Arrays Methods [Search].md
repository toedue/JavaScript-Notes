
## Arrays Methods [Search]

### 1. indexOf(Search Element, From Index [Opt])
- What it does: Finds the first index of an element, starting from a given index (default 0). Returns `-1` if not found.
- Use it: To locate where an item first shows up.

#### Example:
```javascript
/*
  indexOf Example
  - Finding the first "Ahmed" and from index 2.
*/

let myFriends = ["Ahmed", "Mohamed", "Sayed", "Alaa", "Ahmed"]
console.log(myFriends) // ["Ahmed", "Mohamed", "Sayed", "Alaa", "Ahmed"]

console.log(myFriends.indexOf("Ahmed")) // 0 (first "Ahmed")
console.log(myFriends.indexOf("Ahmed", 2)) // 4 (next "Ahmed" after index 2)
```

---

### 2. lastIndexOf(Search Element, From Index [Opt])
- What it does: Finds the last index of an element, searching backward from a given index (default end). Returns `-1` if not found.
- Negative index: Counts from the end (e.g., `-2` is second from last).

#### Example:
```javascript
/*
  lastIndexOf Example
  - Finding the last "Ahmed" and from -2.
*/

console.log(myFriends.lastIndexOf("Ahmed")) // 4 (last "Ahmed")
console.log(myFriends.lastIndexOf("Ahmed", -2)) // 0 (stops at second-to-last, finds first "Ahmed")
```

---

### 3. includes(valueToFind, fromIndex [Opt]) [ES7]
- What it does: Checks if an element exists, returning `true` or `false`. Starts from a given index (default 0).
- Bonus: More readable than index checks.

#### Example:
```javascript
/*
  includes Example
  - Checking if "Ahmed" exists and from index 2.
*/

console.log(myFriends.includes("Ahmed")) // true
console.log(myFriends.includes("Ahmed", 2)) // true (still finds it at 4)
```

---

### Using in Conditions
- What it does: Combine with `if` to handle cases where an element isn’t found (e.g., `indexOf()` returns `-1`).

#### Example:
```javascript
/*
  Conditional Search Example
  - Checking for "Osama".
*/

if (myFriends.lastIndexOf("Osama") === -1) {
  console.log("Not Found") // "Not Found"
}

console.log(myFriends.indexOf("Osama")) // -1
console.log(myFriends.lastIndexOf("Osama")) // -1
```

---


- **indexOf()**: Stops at the first match—use it when you need the earliest spot.
- **lastIndexOf()**: Great for the last occurrence, especially with duplicates.
- **includes()**: Perfect for a simple yes/no—no need to check `-1`.
- **From Index**: Negative values count from the end, positive from the start.
- **Duplicates**: All three handle repeats—`indexOf()` picks first, `lastIndexOf()` picks last.

