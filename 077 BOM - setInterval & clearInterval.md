
## BOM - setInterval & clearInterval

### 1. setInterval(Function, Milliseconds, Additional Params)
- **What it does**: Executes a function repeatedly after a specified interval (in milliseconds).
- **Syntax**: `setInterval(function, milliseconds, param1, param2, ...)`
  - `function`: The function to execute (can be a reference or inline).
  - `milliseconds`: Interval between executions (e.g., `1000` = 1 second).
  - `param1, param2, ...`: Optional arguments passed to the function.
- **Returns**: A unique numeric ID (interval identifier) to track or cancel the interval.
- **Use it**: For recurring tasks (e.g., animations, counters, periodic updates).

### 2. clearInterval(Identifier)
- **What it does**: Stops a `setInterval` from continuing, using its ID.
- **Syntax**: `clearInterval(identifier)`
  - `identifier`: The ID returned by `setInterval`.
- **Use it**: To halt repeated execution (e.g., when a condition is met).

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
  <div>10</div>
  <script src="main.js"></script>
</body>
</html>
```

#### JavaScript (main.js):
```javascript
/*
  BOM setInterval & clearInterval Example
  - Creating a countdown timer.
*/

// setInterval(function () {
//   console.log(`Msg`);
// }, 1000);

// setInterval(sayMsg, 1000);

// function sayMsg() {
//   console.log(`Iam Message`);
// }

// setInterval(sayMsg, 1000, "Osama", 38);

// function sayMsg(user, age) {
//   console.log(`Iam Message For ${user} His Age Is: ${age}`);
// }

let div = document.querySelector("div");

function countdown() {
  div.innerHTML -= 1;
  if (div.innerHTML === "0") {
    clearInterval(counter);
  }
}

let counter = setInterval(countdown, 1000);
```

#### What Happens:
- **Commented Code**:
  - `setInterval(function () { console.log("Msg"); }, 1000)`: Would log "Msg" every second.
  - `setInterval(sayMsg, 1000)`: Would call `sayMsg` (logging "Iam Message") every second.
  - `setInterval(sayMsg, 1000, "Osama", 38)`: Would log "Iam Message For Osama His Age Is: 38" every second.

- **Active Code**:
  - **Setup**:
    - `div`: Selects `<div>10</div>`.
    - `countdown`: A function that decrements `div.innerHTML` by 1 and stops the interval when it reaches "0".
  - **setInterval**:
    - `let counter = setInterval(countdown, 1000)`: Runs `countdown` every second, storing the interval ID in `counter`.
    - Each second, `div.innerHTML -= 1` reduces the displayed number (10 → 9 → 8 → ...).
  - **clearInterval**:
    - When `div.innerHTML === "0"`, `clearInterval(counter)` stops the interval.
    - The countdown stops at 0.

#### Visual Output:
- The `<div>` starts at "10" and counts down to "0" over 10 seconds, then stops.

#### Console Output (If Added):
- Add `console.log(div.innerHTML)` in `countdown` to log: `10`, `9`, ..., `0`.

#### Note:
- `div.innerHTML -= 1` treats the content as a number due to JavaScript’s type coercion, but `innerHTML` is a string. The comparison `=== "0"` works because the result remains a string. For safer numeric operations, use `parseInt(div.innerHTML)`.

---

### Key Points
- **Interval ID**: `setInterval` returns an ID for use with `clearInterval`.
- **Parameters**: Extra params in `setInterval` are passed to the callback.
- **Continuous**: `setInterval` runs until stopped with `clearInterval`.
- **Type Coercion**: Be cautious with `innerHTML` as strings; parse to numbers if needed.

---


- **Debug**: Log `counter` to see the interval ID (`console.log(counter)`).
- **Numeric Safety**: Use `div.innerHTML = parseInt(div.innerHTML) - 1` for explicit number handling.
- **Clear Always**: Call `clearInterval` even if the interval might not exist (it’s safe).
- **Modern Alternative**: Use `requestAnimationFrame` for smoother animations.
