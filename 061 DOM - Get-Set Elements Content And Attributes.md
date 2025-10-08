## DOM - Get / Set Elements Content And Attributes

### 1. innerHTML
- **What it does**: Gets or sets the HTML content inside an element, including tags.
- **Get**: Returns the full HTML (e.g., `<span>text</span>`).
- **Set**: Replaces content with new HTML, parsing it as markup.
- **Use it**: When you need to include or manipulate HTML tags.

### 2. textContent
- **What it does**: Gets or sets the text content inside an element, ignoring tags.
- **Get**: Returns only the text (e.g., `text` from `<span>text</span>`).
- **Set**: Replaces content with plain text, escaping HTML.
- **Use it**: For text-only updates to prevent XSS risks.

### 3. Change Attributes Directly
- **What it does**: Modifies element attributes (e.g., `src`, `alt`) using dot notation.
- **Use it**: Quick changes to standard attributes on DOM elements.

### 4. Change Attributes With Methods
- **getAttribute(attribute)**: Retrieves the value of a specified attribute.
- **setAttribute(attribute, value)**: Sets or updates an attribute’s value.
- **Use it**: For any attribute, including custom ones, with more control.

### Search: innerText
- **What it does**: Similar to `textContent`, but considers CSS visibility (`display: none` elements are ignored) and renders text as displayed.
- **Difference**: `textContent` includes all text, while `innerText` mimics what’s visually shown.
- **Use it**: When you need to match the rendered text (less common than `textContent`).

#### Example:
- We’ll manipulate a `<div class="js">` and an `<img>` based on an assumed HTML structure.

#### Code:
```javascript
/*
  DOM Get/Set Content and Attributes Example
  - Using innerHTML, textContent, and attribute methods.
*/

// Assuming HTML like:
// <div class="js"><span>Original</span> Text</div>
// <img src="old.jpg" alt="Old">
// <a class="link" href="http://example.com" title="Example">Link</a>

let myElement = document.querySelector(".js");

console.log(myElement.innerHTML); // "<span>Original</span> Text"
console.log(myElement.textContent); // "Original Text"

myElement.innerHTML = "Text From <span>Main.js</span> File"; // Renders with <span>
myElement.textContent = "Text From <span>Main.js</span> File"; // Renders as plain text

document.images[0].src = "https://google.com";
document.images[0].alt = "Alternate";
document.images[0].title = "Picture";
document.images[0].id = "pic";
document.images[0].className = "img";

let myLink = document.querySelector(".link");

console.log(myLink.getAttribute("class")); // "link"
console.log(myLink.getAttribute("href")); // "http://example.com"

myLink.setAttribute("href", "https://twitter.com");
myLink.setAttribute("title", "Twitter");
```

#### What Happens:
- **Content Access**:
  - `innerHTML`: Logs the HTML content (`<span>Original</span> Text`).
  - `textContent`: Logs the text only (`Original Text`).

- **Content Modification**:
  - `innerHTML = ...`: Updates to "Text From <span>Main.js</span> File" with the `<span>` rendered.
  - `textContent = ...`: Updates to plain "Text From <span>Main.js</span> File" (no `<span>`).

- **Direct Attribute Changes**:
  - `document.images[0].src = "https://google.com"` sets the image source.
  - `alt`, `title`, `id`, and `className` are updated on the first `<img>`.

- **Attribute Methods**:
  - `getAttribute("class")`: Logs `"link"`.
  - `getAttribute("href")`: Logs `"http://example.com"`.
  - `setAttribute("href", "https://twitter.com")`: Updates the link.
  - `setAttribute("title", "Twitter")`: Adds a title.

#### Assumed HTML:
```html
<!DOCTYPE html>
<html>
<head><title>My Page</title></head>
<body>
  <div class="js"><span>Original</span> Text</div>
  <img src="old.jpg" alt="Old">
  <a class="link" href="http://example.com" title="Example">Link</a>
  <script src="dom-content-attributes.js"></script>
</body>
</html>
```

---


- **innerHTML Risk**: Avoid setting untrusted input to prevent XSS—use `textContent` for safety.
- **textContent vs innerText**: `textContent` is preferred for raw text; `innerText` for rendered text (e.g., hidden elements).
- **Direct vs Methods**: Dot notation is faster for standard attributes; `get/setAttribute` works for any attribute.
- **Collections**: `document.images[0]` assumes at least one `<img>`—check `length` first.
