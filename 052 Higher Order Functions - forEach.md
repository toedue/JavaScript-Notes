## forEach
- **What It Does**: Executes a provided callback function once for each element in an array (or NodeList, like `querySelectorAll` returns).
- **Syntax**: `array.forEach(callbackFunction(element, index, array) { }, thisArg)`
  - **element**: The current item being processed.
  - **index**: The current item’s position (optional).
  - **array**: The original array/NodeList (optional).
  - **thisArg**: Value to use as `this` when executing the callback (optional).
- **Key Features**:
  - **No Return**: Returns `undefined`—it’s for side effects (e.g., modifying elements).
  - **No Break**: `break` won’t stop the loop; use a `return` or external flag if needed.

### Notes
- **NodeList**: Works with `querySelectorAll` results, treating them like arrays.
- **Use Case**: Ideal for iterating and performing actions (e.g., event handling, DOM manipulation).

#### HTML:
```html
<ul>
  <li class="active">One</li>
  <li>Two</li>
  <li>Three</li>
</ul>
<div class="content">
  <div>Div One</div>
  <div>Div Two</div>
  <div>Div Three</div>
</div>
```

#### JavaScript:
```javascript
/*
  forEach Method Example
  - Handling li clicks to toggle active class and div visibility.
*/

let allLis = document.querySelectorAll("ul li")
let allDivs = document.querySelectorAll(".content div")

allLis.forEach(function (ele) {
  ele.onclick = function () {
    // Remove Active Class From All Elements
    allLis.forEach(function (ele) {
      ele.classList.remove("active")
    })
    // Add Active Class To This Element
    this.classList.add("active")
    // Hide All Divs
    allDivs.forEach(function (ele) {
      ele.style.display = "none"
    })
  }
})
```

#### What Happens:
- **Setup**:
  - `allLis`: NodeList of all `<li>` elements (`["One", "Two", "Three"]`).
  - `allDivs`: NodeList of all `<div>` elements inside `.content` (`["Div One", "Div Two", "Div Three"]`).

- **Outer forEach**:
  - Iterates over each `<li>`.
  - Assigns an `onclick` event handler to each.

- **onclick Handler**:
  - **Remove Active Class**: Loops through `allLis`, removing `"active"` from all `<li>`s.
  - **Add Active Class**: Adds `"active"` to the clicked `<li>` (using `this`).
  - **Hide All Divs**: Loops through `allDivs`, setting `style.display = "none"`.
  - **Note**: The code hides all divs but doesn’t show a specific one—let’s enhance it below.

- **Behavior**:
  - Clicking "One" removes `active` from all, adds it to "One", and hides all divs.
  - Same for "Two" and "Three", but no div is shown (we’ll fix that).

#### Enhanced Version (Showing Matching Div):
```javascript
allLis.forEach(function (ele, index) {
  ele.onclick = function () {
    // Remove Active Class From All Elements
    allLis.forEach(function (ele) {
      ele.classList.remove("active")
    })
    // Add Active Class To This Element
    this.classList.add("active")
    // Hide All Divs
    allDivs.forEach(function (div) {
      div.style.display = "none"
    })
    // Show Matching Div
    allDivs[index].style.display = "block"
  }
})
```
- **What Changes**: Uses `index` to match the clicked `<li>`’s position to the corresponding `<div>`, setting its `display` to `"block"`.

- **Output**:
  - Click "One" → `active` on "One", shows "Div One".
  - Click "Two" → `active` on "Two", shows "Div Two".
  - Click "Three" → `active` on "Three", shows "Div Three".

---


- **No Return**: Use `forEach` for side effects (e.g., DOM changes), not transformations.
- **Index Use**: Leverage `index` to correlate elements (like `<li>` to `<div>`).
- **Break Limitation**: To stop early, use a `for` loop or a flag (e.g., `let stop = false; allLis.forEach((ele) => { if (stop) return; ... });`).
- **Chaining**: Can’t chain directly since it returns `undefined`, but use it with `map`/`filter` results.
