
## Function - Random Argument 

### What It Is
- Create a `showDetails` function that accepts 3 parameters (`a`, `b`, `c`) with random data types.
- Data Types: String (name), Number (age), Boolean (status).
- Goal: Output a consistent message regardless of argument order, using ternary operators.
- Output: "Hello [Name], Your Age Is [Age], You Are [Available/Not Available] For Hire".

#### Code:
```javascript
/*
  Random Argument Challenge Example
  - Handling unsorted name, age, and status with ternary.
*/

function showDetails(a, b, c) {
  let name = typeof a === "string" ? a : typeof b === "string" ? b : c;
  let age = typeof a === "number" ? a : typeof b === "number" ? b : c;
  let status = typeof a === "boolean" ? a : typeof b === "boolean" ? b : c;

  document.write(`Hello ${name}, Your Age Is ${age}, You Are ${status ? "Available" : "Not Available"} For Hire<br>`);
}

showDetails("Osama", 38, true); // Hello Osama, Your Age Is 38, You Are Available For Hire
showDetails(38, "Osama", true); // Hello Osama, Your Age Is 38, You Are Available For Hire
showDetails(true, 38, "Osama"); // Hello Osama, Your Age Is 38, You Are Available For Hire
showDetails(false, "Osama", 38); // Hello Osama, Your Age Is 38, You Are Not Available For Hire
```

#### What Happens:
- **Ternary Logic**: 
  - `name` is set to the string using nested ternaries: checks `a`, then `b`, then `c`.
  - `age` is set to the number similarly.
  - `status` is set to the boolean, with `? "Available" : "Not Available"` converting it to text.
- **Calls**: 
  - `"Osama", 38, true`: `name = "Osama"`, `age = 38`, `status = true`.
  - `38, "Osama", true`: `name = "Osama"`, `age = 38`, `status = true`.
  - `true, 38, "Osama"`: `name = "Osama"`, `age = 38`, `status = true`.
  - `false, "Osama", 38`: `name = "Osama"`, `age = 38`, `status = false`.
- **Output**: Consistent message with correct values, adapting to random order.

---


- **Ternary Nesting**: Chain ternaries to check each parameter—works since only one of each type is expected.
- **Type Check**: `typeof` is key to identify data types dynamically.
- **Boolean Conversion**: `status ? "Available" : "Not Available"` is a clean ternary for true/false output.
- **Output**: `document.write` adds `<br>` for line breaks—use `console.log` or DOM for better control.
