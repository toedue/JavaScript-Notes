
## Filter
- **What It Does**: Creates a new array containing only the elements that pass a test implemented by a provided callback function.
- **Syntax**: `array.filter(callbackFunction(element, index, array) { }, thisArg)`
  - **element**: The current item being processed.
  - **index**: The current item’s position (optional).
  - **array**: The original array (optional).
  - **thisArg**: Value to use as `this` when executing the callback (optional).
- **Key Feature**: Returns a new array with filtered elements, leaving the original unchanged.

### Notes
- **New Array**: Like `map`, it doesn’t modify the original array.
- **Test**: The callback must return a boolean (`true` to keep, `false` to discard).

#### Example 1: Friends Starting With "A"
- Filter `friends` to get names starting with "A".

#### Example 2: Even Numbers
- Filter `numbers` to get even values.

#### Code:
```javascript
/*
  Filter Method Example
  - Filtering friends and even numbers.
*/

// Get Friends With Name Starts With A
let friends = ["Ahmed", "Sameh", "Sayed", "Asmaa", "Amgad", "Israa"]

let filteredFriends = friends.filter(function (el) {
  return el.startsWith("A") ? true : false
})

console.log(filteredFriends) // ["Ahmed", "Asmaa", "Amgad"]

// Get Even Numbers Only
let numbers = [11, 20, 2, 5, 17, 10]

let evenNumbers = numbers.filter(function (el) {
  return el % 2 === 0
})

console.log(evenNumbers) // [20, 2, 10]

// Test Map vs Filter (Commented)
// let addMap = numbers.map(function (el) {
//   return el + el;
// });

// console.log(addMap); // [22, 40, 4, 10, 34, 20]

// let addFilter = numbers.filter(function (el) {
//   return el + el;
// });

// console.log(addFilter); // [] (empty, as el + el is always truthy)
```

#### What Happens:
- **Filtered Friends**:
  - `el.startsWith("A")` checks each name.
  - Returns `true` for "Ahmed", "Asmaa", "Amgad", creating `["Ahmed", "Asmaa", "Amgad"]`.
  - The ternary `? true : false` is redundant here—`startsWith("A")` alone returns a boolean.

- **Even Numbers**:
  - `el % 2 === 0` tests for evenness (remainder 0 when divided by 2).
  - Returns `[20, 2, 10]` from `[11, 20, 2, 5, 17, 10]`.

- **Map vs Filter (Commented)**:
  - `map` transforms each element (e.g., `el + el` doubles to `[22, 40, 4, 10, 34, 20]`).
  - `filter` keeps elements where the callback returns `true`. Since `el + el` is always a number (truthy), `filter` with it returns an empty array `[]`—it doesn’t make sense as a filter condition.

---

### Key Differences: Map vs Filter
- **Purpose**: 
  - `map`: Transforms each element and returns a new array of the same length.
  - `filter`: Selects elements based on a condition, returning a new array of potentially different length.
- **Return Value**: 
  - `map` expects a transformation (any value).
  - `filter` expects a boolean to decide inclusion.
- **Use Case**: Use `map` to change data, `filter` to narrow it down.

---


- **Boolean Return**: Ensure the callback returns `true` or `false` for `filter` to work as intended.
- **Simplicity**: Avoid unnecessary ternaries—`return el.startsWith("A")` is enough.
- **Chaining**: Combine with `map` (e.g., `numbers.filter(el => el % 2 === 0).map(el => el * 2)` for even doubles).
- **Immutability**: Always get a new array, so the original stays safe.

