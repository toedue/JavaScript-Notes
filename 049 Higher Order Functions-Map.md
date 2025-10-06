
## Higher Order Functions

### What Is a Higher Order Function?
- **Definition**: A function that accepts other functions as parameters and/or returns a function.
- **Examples**: `map`, `filter`, `reduce`—they take callbacks to customize behavior.
- **Use It**: Enables flexible, reusable code by abstracting operations.

## Map
- **What It Does**: Creates a new array by applying a provided callback function to every element of the calling array.
- **Syntax**: `array.map(callbackFunction(element, index, array) { }, thisArg)`
  - **element**: The current item being processed.
  - **index**: The current item’s position (optional).
  - **array**: The original array (optional).
  - **thisArg**: Value to use as `this` when executing the callback (optional).
- **Key Feature**: Always returns a new array, leaving the original unchanged.

### Notes
- **New Array**: `map` doesn’t modify the original array; it returns a fresh one.
- **Callback**: The function can be anonymous, named, or an arrow function.

#### Example:
- We’ll double each number in `myNums` using a `for` loop and then replicate it with `map`.

#### Code:
```javascript
/*
  Map Method Example
  - Doubling numbers with for loop and map.
*/

let myNums = [1, 2, 3, 4, 5, 6]

let newArray = []

for (let i = 0; i < myNums.length; i++) {
  newArray.push(myNums[i] + myNums[i])
}

console.log(newArray) // [2, 4, 6, 8, 10, 12]

// Same Idea With Map

// Anonymous Function Example (Commented)
// let addSelf = myNums.map(function (element, index, arr) {
//   console.log(`Current Element => ${element}`);
//   console.log(`Current Index => ${index}`);
//   console.log(`Array => ${arr}`);
//   console.log(`This => ${this}`);
//   return element + element;
// }, 10);

// Arrow Function Example (Commented)
// let addSelf = myNums.map((a) => a + a);

function addition(ele) {
  return ele + ele
}

let add = myNums.map(addition)

console.log(add) // [2, 4, 6, 8, 10, 12]
```

#### What Happens:
- **For Loop**:
  - Iterates over `myNums`, doubles each element (`1+1`, `2+2`, etc.), and pushes to `newArray`.
  - Output: `[2, 4, 6, 8, 10, 12]`.

- **Map with Named Function**:
  - `addition(ele)` defines a function that doubles its input.
  - `myNums.map(addition)` applies `addition` to each element, returning a new array.
  - Output: `[2, 4, 6, 8, 10, 12]`.

- **Commented Alternatives**:
  - **Anonymous Function**: `function (element, index, arr) { return element + element; }` logs details and doubles each element.
  - **Arrow Function**: `(a) => a + a` is a concise version doing the same.
  - **thisArg**: The `10` in the first example sets `this` to 10 inside the callback (useful with object methods).

---

### Key Differences from For Loop
- **Immutability**: `map` creates a new array; the loop modifies `newArray`.
- **Functional**: `map` is declarative (what to do), while the loop is imperative (how to do it).
- **Reusability**: `map` with a named function (like `addition`) is reusable across arrays.

---


- **Return Required**: The callback must `return` a value to populate the new array.
- **No Side Effects**: Avoid modifying the original array inside `map`—use it for transformations.
- **Debugging**: Use `index` and `array` params to log context if needed.
- **Chaining**: Combine with other methods (e.g., `map(...).filter(...)`).
