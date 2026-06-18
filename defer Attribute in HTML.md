# `defer` Attribute in HTML

## Definition

`defer` is a Boolean attribute added to the `<script>` tag that tells the browser:

> **Download the JavaScript file immediately, but wait to execute it until the HTML document has been completely parsed.**

---

## Syntax

```html
<script src="index.js" defer></script>
```

---

## Why `defer` Is Needed

Consider this HTML:

```html
<head>
  <script src="index.js"></script>
</head>

<body>
  <div class="card">Hello</div>
</body>
```

The browser reads the page from top to bottom:

1. Encounters `<script src="index.js">`
2. Stops parsing the HTML
3. Downloads and executes `index.js`
4. Continues reading the rest of the HTML

At step 3, `.card` does not exist yet because the browser has not reached the `<body>` section.

So this code fails:

```javascript
document.querySelector(".card");
```

because it returns:

```javascript
null
```

---

## How `defer` Works

When you add `defer`:

```html
<script src="index.js" defer></script>
```

the browser behaves differently:

1. Starts parsing the HTML
2. Downloads `index.js` in the background
3. Continues parsing the HTML
4. Builds the entire DOM
5. Executes `index.js`

Now `.card` exists when JavaScript runs.

---

## Visual Comparison

### Without `defer`

```text
Parse HTML → Stop → Download JS → Execute JS → Continue HTML
```

### With `defer`

```text
Parse HTML → Download JS in background → Finish HTML → Execute JS
```

---

## Benefits of `defer`

* Prevents errors caused by accessing elements before they exist
* Improves page loading performance
* Keeps JavaScript files in the `<head>`
* Executes scripts after the DOM is ready

---

## Multiple Deferred Scripts

Deferred scripts execute **in the order they appear** in the HTML.

```html
<script src="first.js" defer></script>
<script src="second.js" defer></script>
```

Execution order:

```text
first.js → second.js
```

Even if `second.js` downloads first, it waits for `first.js`.

---

## `defer` vs `async`

| Feature                                       | `defer` | `async` |
| --------------------------------------------- | ------- | ------- |
| Downloads in background                       | ✅       | ✅       |
| Waits for HTML parsing to finish              | ✅       | ❌       |
| Maintains script order                        | ✅       | ❌       |
| Best for DOM manipulation                     | ✅       | ❌       |
| Best for independent scripts (analytics, ads) | ❌       | ✅       |

Example:

```html
<script src="app.js" defer></script>
<script src="analytics.js" async></script>
```

---

## Important Notes

* `defer` only works with **external scripts** that use `src`.

  ```html
  <script src="index.js" defer></script>
  ```

* It has no effect on inline scripts.

  ```html
  <script defer>
    console.log("Hello");
  </script>
  ```

* Most modern websites use `defer` for their main JavaScript files.

---

## Recommended Practice

For scripts that interact with HTML elements, use:

```html
<head>
  <script src="index.js" defer></script>
</head>
```

This is cleaner than moving the script tag to the bottom of the `<body>`.
