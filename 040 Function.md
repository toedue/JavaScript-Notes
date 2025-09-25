
## Function

### 1. What Is Function?
- What it is: A block of code designed to perform a specific task, which you can call whenever you need it.
- Why it matters: Saves time, reduces repetition, and organizes your program.

### 2. User-Defined vs Built-In
- **User-Defined**: Functions you create, like `sayHello()` below.
- **Built-In**: Functions JavaScript provides, like `console.log()` or `Array.push()`.

### 3. Syntax + Basic Usage
- Syntax:
  ```javascript
  function functionName(parameter) {
    // Code to execute
  }
  functionName(argument); // Call it
  ```
- Usage: Define once, call multiple times with different inputs.

### 4. Example From Real Life
- Think of a coffee machine: You press a button (call the function) with a coffee type (argument), and it brews (executes the task) every time.

### 5. Parameter + Argument
- **Parameter**: A variable in the function definition (e.g., `userName`) that acts as a placeholder.
- **Argument**: The actual value passed when calling the function (e.g., `"Osama"`).

### 6. Practical Example
- Let’s create a function to greet users.

#### Code:
```javascript
/*
  Function Example
  - Greeting users with a parameter.
*/

function sayHello(userName) {
  console.log(`Hi ${userName}`);
}

sayHello("Osama"); // Hi Osama
sayHello("Sayed"); // Hi Sayed
sayHello("Ali"); // Hi Ali
```

#### What Happens:
- **Definition**: `sayHello` takes a `userName` parameter and logs a greeting.
- **Calls**: Each `sayHello("name")` passes an argument, printing a personalized message.
- **Result**: Three greetings for "Osama", "Sayed", and "Ali".

---


- **Naming**: Use descriptive names (e.g., `sayHello` vs. `doStuff`).
- **Parameters**: Optional—functions can work without them.
- **Reuse**: Call it anywhere to avoid rewriting code.
- **Return**: Add `return` to send back a value (we’ll cover this later!).
