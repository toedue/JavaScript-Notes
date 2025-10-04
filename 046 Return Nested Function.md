## Function - Function Inside Function & Return Function

### 1. Function Inside Function
- What it is: A function defined within another function, with access to the outer function’s scope (closure).
- Use it: To encapsulate logic or create private helpers.

### 2. Return Function
- What it does: A function can return another function, allowing dynamic behavior or delayed execution.
- Use it: For factories, callbacks, or building complex workflows.

#### Example 1: Nested Function Modifies Outer Variable
```javascript
/*
  Function Inside Function Example 1
  - Nested function modifies outer message.
*/

function sayMessage(fName, lName) {
  let message = `Hello`
  // Nested Function
  function concatMsg() {
    message = `${message} ${fName} ${lName}`
  }
  concatMsg()
  return message
}

console.log(sayMessage("Osama", "Mohamed")) // "Hello Osama Mohamed"
```
- **What Happens**: 
  - `concatMsg()` modifies the outer `message` by concatenating it with `fName` and `lName`.
  - Returns the updated `message`.
- **Key Point**: The nested function has access to `message` and can change it.

#### Example 2: Nested Function Returns Value
```javascript
/*
  Function Inside Function Example 2
  - Nested function returns a new string.
*/

function sayMessage(fName, lName) {
  let message = `Hello`
  // Nested Function
  function concatMsg() {
    return `${message} ${fName} ${lName}`
  }
  return concatMsg()
}

console.log(sayMessage("Osama", "Mohamed")) // "Hello Osama Mohamed"
```
- **What Happens**: 
  - `concatMsg()` returns a new string without altering the outer `message`.
  - The outer function returns this result.
- **Key Point**: The nested function creates a fresh value, leaving `message` unchanged.

#### Example 3: Multiple Nested Functions
```javascript
/*
  Function Inside Function Example 3
  - Multiple nested functions for full name.
*/

function sayMessage(fName, lName) {
  let message = `Hello`
  // Nested Function
  function concatMsg() {
    function getFullName() {
      return `${fName} ${lName}`
    }
    return `${message} ${getFullName()}`
  }
  return concatMsg()
}

console.log(sayMessage("Osama", "Mohamed")) // "Hello Osama Mohamed"
```
- **What Happens**: 
  - `getFullName()` returns the combined name.
  - `concatMsg()` uses this to build the final message.
  - The outer function returns the result.
- **Key Point**: Shows deeper nesting, with each function handling a specific task.

---


- **Closure**: Nested functions retain access to outer scope variables, even after the outer function finishes.
- **Return Flexibility**: Returning a function (e.g., `return concatMsg`) can create a function that “remembers” its context.
- **Modularity**: Break complex logic into smaller, nested functions for readability.
- **Performance**: Avoid excessive nesting if it’s not needed—keep it logical.
