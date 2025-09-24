
## Switch Statement

### What It Is
- Syntax:
  ```javascript
  switch (expression) {
    case value1:
      // Code block
      break;
    case value2:
      // Code block
      break;
    default:
      // Code block
  }
  ```
- What it does: Checks the `expression` against each `case` value using strict equality (`===`), and runs the matching block until a `break` or the end.
- Use it: Great for menus, days, or states with clear options.

---

### Key Features
- **Default Ordering**: The `default` can go anywhere—first, last, or middle—but it’s usually at the end as a fallback.
- **Multiple Match**: Use multiple `case` labels without `break` to group actions.
- **===**: Uses strict equality (checks type and value), no coercion like `==`.

---

### Example
- We’ve got a `day` variable, and we’ll match it to print the day of the week—or an unknown message.

#### Code:
```javascript
/*
  Switch Statement Example
  - Matching day with default, multiple cases, and strict check.
*/

let day = "A"

switch (day) {
  default:
    console.log("Unknown Day")
    break
  case 0:
    console.log("Saturday")
    break
  case 1:
    console.log("Sunday")
    break
  case 2:
  case 3:
    console.log("Monday")
    break
}
```

#### What Happens:
- `day` is `"A"`, which doesn’t match `0`, `1`, `2`, or `3` (all numbers, and `"A"` is a string—`===` fails).
- Since no `case` matches and `default` is first, it runs `console.log("Unknown Day")` and hits `break`.
- Result: Logs "Unknown Day".

---


- **Break**: Always add `break` to stop falling through to the next case—forget it, and it keeps going!
- **Default**: Put it where it makes sense—top if you want it to catch first, bottom if it’s a last resort.
- **Multiple Cases**: Stack `case` values for the same action, like `2` and `3` both being "Monday".
- **Type Check**: `===` means `"0"` won’t match `0`—keep types consistent.
