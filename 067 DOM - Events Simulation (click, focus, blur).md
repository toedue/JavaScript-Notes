## DOM - Events Simulation

### 1. click()
- **What it does**: Simulates a mouse click on an element, triggering its `onclick` event or default behavior (e.g., navigating for a link).
- **Use it**: To mimic user clicks programmatically.

### 2. focus()
- **What it does**: Sets focus on an element (e.g., an input), triggering its `onfocus` event and making it active for user input.
- **Use it**: To direct the user’s cursor to a specific field.

### 3. blur()
- **What it does**: Removes focus from an element, triggering its `onblur` event.
- **Use it**: To simulate moving focus away from an element.

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
  <input class="one" type="text" placeholder="One" />
  <input class="two" type="text" placeholder="Two" />
  <a href="https://example.com">Link</a>
  <script src="main.js"></script>
</body>
</html>
```

#### JavaScript (main.js):
```javascript
/*
  DOM Events Simulation Example
  - Simulating focus, blur, and click events.
*/

let one = document.querySelector(".one");
let two = document.querySelector(".two");

window.onload = function () {
  two.focus();
};

one.onblur = function () {
  document.links[0].click();
};
```

#### What Happens:
- **Setup**:
  - `one`: Selects the `<input class="one">` element.
  - `two`: Selects the `<input class="two">` element.

- **window.onload**:
  - When the page fully loads, `two.focus()` is called.
  - This sets the cursor to the `<input class="two">`, simulating a user clicking into it.
  - Triggers any `onfocus` event (none defined here).

- **one.onblur**:
  - When the `<input class="one">` loses focus (e.g., user clicks out or tabs away), `document.links[0].click()` is called.
  - This simulates clicking the first `<a>` link, triggering its default behavior (navigating to `https://example.com`).
  - Note: If the link has an `onclick` handler, that would run too.

#### Example Flow:
1. Page loads → `two.focus()` puts the cursor in the second input.
2. User clicks into `<input class="one">` → Focus moves to `one`.
3. User clicks elsewhere (or tabs out) → `one` loses focus, triggering `onblur` → `document.links[0].click()` navigates to `https://example.com`.

#### Output (Behavior):
- On load, the cursor appears in `<input class="two">`.
- If you focus `<input class="one">` and then blur it (e.g., click elsewhere), the browser attempts to navigate to `https://example.com`.

---

### Key Points
- **Event Simulation**: `click()`, `focus()`, and `blur()` mimic user actions, firing associated events.
- **Default Behavior**: `click()` on a link triggers navigation unless `preventDefault()` is used.
- **Event Chaining**: `onblur` triggering `click()` shows how events can cascade.
- **Context**: Simulated events behave like user-triggered ones, respecting defined handlers.

---


- **Testing**: Use `console.log` in event handlers to debug (e.g., `one.onblur = () => console.log("Blurred")`).
- **Prevent Default**: Add `event.preventDefault()` in an `onclick` for the link to block navigation.
- **Dynamic**: Combine with `addEventListener` for more flexible event handling.
- **Edge Cases**: Ensure elements exist before calling methods (e.g., check `if (two) two.focus()`).
