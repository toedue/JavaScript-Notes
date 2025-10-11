## BOM - setTimeout & clearTimeout

### 1. setTimeout(Function, Timeout, Additional Params)
- **What it does**: Schedules a function to run after a specified delay (in milliseconds).
- **Syntax**: `setTimeout(function, timeout, param1, param2, ...)`
  - `function`: The function to execute (can be a reference or inline).
  - `timeout`: Delay in milliseconds (e.g., `3000` = 3 seconds).
  - `param1, param2, ...`: Optional arguments passed to the function.
- **Returns**: A unique numeric ID (timeout identifier) to track or cancel the timeout.
- **Use it**: For one-time delayed actions (e.g., showing a message, triggering an animation).

### 2. clearTimeout(Identifier)
- **What it does**: Cancels a `setTimeout` before it executes, using its ID.
- **Syntax**: `clearTimeout(identifier)`
  - `identifier`: The ID returned by `setTimeout`.
- **Use it**: To stop a scheduled timeout from running (e.g., user cancels an action).

#### HTML (Assumed):
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge" />
  <title>Learn JavaScript</title>
</head>
<body>
  <button>Cancel Timeout</button>
  <script src="main.js"></script>
</body>
</html>
```

#### JavaScript (main.js):
```javascript
/*
  BOM setTimeout & clearTimeout Example
  - Scheduling and canceling a timeout.
*/

// setTimeout(function () {
//   console.log("Msg");
// }, 3000);

// setTimeout(sayMsg, 3000);

// function sayMsg() {
//   console.log(`Iam Message`);
// }

// setTimeout(sayMsg, 3000, "Osama", 38);

// function sayMsg(user, age) {
//   console.log(`Iam Message For ${user} Age Is : ${age}`);
// }

let btn = document.querySelector("button");

btn.onclick = function () {
  clearTimeout(counter);
};

function sayMsg(user, age) {
  console.log(`Iam Message For ${user} Age Is : ${age}`);
}

let counter = setTimeout(sayMsg, 3000, "Osama", 38);
```

#### What Happens:
- **Commented Code**:
  - `setTimeout(function () { console.log("Msg"); }, 3000)`: Would log "Msg" after 3 seconds.
  - `setTimeout(sayMsg, 3000)`: Would call `sayMsg` (logging "Iam Message") after 3 seconds.
  - `setTimeout(sayMsg, 3000, "Osama", 38)`: Would log "Iam Message For Osama Age Is : 38" after 3 seconds.

- **Active Code**:
  - **Setup**:
    - `btn`: Selects the `<button>Cancel Timeout</button>`.
    - `sayMsg`: A function that logs a message with a user and age.
  - **setTimeout**:
    - `let counter = setTimeout(sayMsg, 3000, "Osama", 38)`: Schedules `sayMsg("Osama", 38)` to run after 3 seconds, storing the timeout ID in `counter`.
    - After 3 seconds, logs: `Iam Message For Osama Age Is : 38`.
  - **clearTimeout**:
    - `btn.onclick`: When the button is clicked, `clearTimeout(counter)` cancels the timeout.
    - If clicked within 3 seconds, the message won’t appear.

#### Example Scenarios:
- **No Button Click**: After 3 seconds, console logs: `Iam Message For Osama Age Is : 38`.
- **Button Clicked Before 3 Seconds**: Timeout is canceled, no message logged.
- **Button Clicked After 3 Seconds**: Timeout already executed, so `clearTimeout` has no effect.

#### Output (Console):
- If button not clicked within 3 seconds:
  ```
  Iam Message For Osama Age Is : 38
  ```
- If button clicked within 3 seconds: No output.

---

### Key Points
- **Timeout ID**: `setTimeout` returns an ID (e.g., `counter`) for use with `clearTimeout`.
- **Parameters**: Extra params in `setTimeout` are passed to the callback function.
- **One-Time**: `setTimeout` runs once; use `setInterval` for repeated execution.
- **Scope**: `setTimeout` is a `window` method (`window.setTimeout`).

---


- **Debug**: Log the timeout ID (`console.log(counter)`) to verify it’s set.
- **Clear Early**: Call `clearTimeout` even if the timeout might not exist (it’s safe).
- **Alternative**: Use `setInterval` for recurring tasks, cleared with `clearInterval`.
- **Modern Use**: Consider `async/await` with `Promises` for complex timing logic.
