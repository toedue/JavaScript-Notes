## DOM - CSS

### 1. style
- **What it does**: The `style` property allows direct access to an element’s inline CSS styles, letting you get or set individual properties.
- **Use it**: For quick, element-specific style changes.
- **Note**: Uses camelCase (e.g., `fontWeight` instead of `font-weight`).

### 2. cssText
- **What it does**: Gets or sets the entire inline CSS style as a single string, overwriting existing inline styles.
- **Use it**: To apply multiple styles at once in a concise way.

### 3. removeProperty(propertyName)
- **What it does**: Removes a specific CSS property from an element’s inline styles or a stylesheet rule.
- **Use it**: To clear a style without replacing all styles.
- **Note**: Use kebab-case (e.g., `"font-size"`) for property names.

### 4. setProperty(propertyName, value, priority)
- **What it does**: Sets a CSS property with an optional priority (e.g., `"important"`).
- **Use it**: For precise control over styles, especially with `!important`.
- **Note**: Works on inline styles or stylesheet rules.

#### HTML (Assumed):
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge" />
  <title>Learn JavaScript</title>
  <style>
    #my-div {
      line-height: 1.5;
      background-color: blue;
    }
  </style>
</head>
<body>
  <div id="my-div">Hello Div</div>
  <script src="main.js"></script>
</body>
</html>
```

#### JavaScript (main.js):
```javascript
/*
  DOM CSS Example
  - Manipulating inline and stylesheet styles.
*/

let element = document.getElementById("my-div");

element.style.color = "red";
element.style.fontWeight = "bold";

element.style.cssText = "font-weight: bold; color: green; opacity: 0.9";

element.style.removeProperty("color");
element.style.setProperty("font-size", "40px", "important");

document.styleSheets[0].rules[0].style.removeProperty("line-height");
document.styleSheets[0].rules[0].style.setProperty("background-color", "red", "important");
```

#### What Happens:
- **Setup**:
  - `element` selects `<div id="my-div">`.
  - Initial stylesheet rule: `#my-div { line-height: 1.5; background-color: blue; }`.

- **style Property**:
  - `element.style.color = "red"`: Sets inline `color: red`.
  - `element.style.fontWeight = "bold"`: Sets inline `font-weight: bold`.
  - Result: `<div id="my-div" style="color: red; font-weight: bold;">`.

- **cssText**:
  - `element.style.cssText = "font-weight: bold; color: green; opacity: 0.9"`: Overwrites inline styles.
  - Result: `<div id="my-div" style="font-weight: bold; color: green; opacity: 0.9;">`.

- **removeProperty**:
  - `element.style.removeProperty("color")`: Removes `color` from inline styles.
  - Result: `<div id="my-div" style="font-weight: bold; opacity: 0.9;">`.

- **setProperty**:
  - `element.style.setProperty("font-size", "40px", "important")`: Adds `font-size: 40px !important` inline.
  - Result: `<div id="my-div" style="font-weight: bold; opacity: 0.9; font-size: 40px !important;">`.

- **Stylesheet Modifications**:
  - `document.styleSheets[0].rules[0].style.removeProperty("line-height")`: Removes `line-height` from `#my-div` rule.
  - `document.styleSheets[0].rules[0].style.setProperty("background-color", "red", "important")`: Sets `background-color: red !important` in the stylesheet.
  - Resulting rule: `#my-div { background-color: red !important; }`.

#### Visual Result:
- `<div>` has a bold, 40px font, 0.9 opacity, and a red background (from stylesheet `!important`).

#### Console Output (If Added):
- `console.log(element.style)`: Shows the inline styles (`font-weight`, `opacity`, `font-size`).
- `console.log(document.styleSheets[0].rules[0].style)`: Shows `{ background-color: red !important }`.

---

### Key Points
- **Inline vs Stylesheet**: `style` and `cssText` affect inline styles; `styleSheets` modifies CSS rules.
- **CamelCase vs Kebab-Case**:
  - `style.color` uses camelCase.
  - `setProperty("font-size", ...)` uses kebab-case.
- **Priority**: Use `"important"` in `setProperty` to override other styles.
- **Live Updates**: Stylesheet and inline style changes update the DOM in real-time.

---


- **Debug**: Log `element.style` or `document.styleSheets[0].rules` to inspect styles.
- **Stylesheet Access**: Use `cssRules` instead of `rules` for cross-browser compatibility (though `rules` works in most modern browsers).
- **Specificity**: Inline `!important` beats stylesheet styles unless the stylesheet also uses `!important`.
- **Safety**: Check `document.styleSheets[0]` exists before accessing `rules`.
