## Loop - Loop On Sequences

### What It Is
- What it does: A `for` loop can run through an array’s elements using an index, checking each one based on its position.
- Use it: Perfect for looping over sequences (arrays, strings, etc.) to perform actions or collect data.

#### Example:
- We’ve got a mixed array with numbers and strings, and we’ll loop to grab only the names.

#### Code:
```javascript
/*
  Loop On Sequences Example
  - Filtering strings from a mixed array.
*/

let myFriends = [1, 2, "Osama", "Ahmed", 3, 4, "Sayed", 6, "Ali"]
let onlyNames = []

for (let i = 0; i < myFriends.length; i++) {
  if (typeof myFriends[i] === "string") {
    onlyNames.push(myFriends[i])
  }
}

console.log(onlyNames) // ["Osama", "Ahmed", "Sayed", "Ali"]
```

#### What Happens:
- **Initialization**: `let i = 0` starts at the first index.
- **Condition**: `i < myFriends.length` (9) keeps looping while `i` is less than 9.
- **Update**: `i++` moves to the next index each time.
- **Check**: `typeof myFriends[i] === "string"` tests if the element is a string.
- **Action**: `onlyNames.push(myFriends[i])` adds matching strings to the new array.
- **Result**: `onlyNames` gets `["Osama", "Ahmed", "Sayed", "Ali"]`, skipping numbers.

---


- **length**: Use `myFriends.length` to dynamically loop over any array size.
- **Condition**: Add `if` checks (like `typeof`) to filter or process specific items.
- **Push**: `push()` is great for building a new array as you loop.
- **Index**: `i` gives you the position—useful for nested arrays or calculations.
