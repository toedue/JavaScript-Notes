## DOM - What Is DOM
- **Definition**: The DOM (DOM stands for Document Object Model) is a programming interface for HTML and XML documents. It represents the structure of a webpage as a tree of objects, where each element, attribute, and text node is a node.
- **Purpose**: Allows JavaScript to dynamically access, modify, or manipulate the content, structure, and styles of a webpage.
- **Key Idea**: Think of it as a bridge between HTML and JavaScript, turning static markup into a live object model.

## DOM Selectors
### 1. Find Element By ID
- **Method**: `document.getElementById("id")`
- **What it does**: Returns the first element with the specified ID as an `Element` object.
- **Use it**: For unique elements.

### 2. Find Element By Tag Name
- **Method**: `document.getElementsByTagName("tag")`
- **What it does**: Returns a live `HTMLCollection` of all elements with the given tag name.
- **Use it**: To target multiple elements of the same type (e.g., all `<p>` tags).

### 3. Find Element By Class Name
- **Method**: `document.getElementsByClassName("class")`
- **What it does**: Returns a live `HTMLCollection` of elements with the specified class name.
- **Use it**: For elements sharing a class.

### 4. Find Element By CSS Selectors
- **Methods**: 
  - `document.querySelector("selector")`: Returns the first element matching the CSS selector.
  - `document.querySelectorAll("selector")`: Returns a static `NodeList` of all matching elements.
- **What it does**: Uses CSS syntax (e.g., `.class`, `#id`, `tag`) for flexible selection.
- **Use it**: For complex or modern selections.

### 5. Find Element By Collection
- **Properties**: Access predefined collections in the `document` object.
  - `document.title`: Gets or sets the document’s title.
  - `document.body`: References the `<body>` element.
  - `document.images`: An `HTMLCollection` of all `<img>` elements.
  - `document.forms`: An `HTMLCollection` of all `<form>` elements.
  - `document.links`: An `HTMLCollection` of all `<a>` elements with an `href`.

#### Example:
- We’ll use various selectors and collections based on an assumed HTML structure.

#### Code:
```javascript
/*
  DOM Selectors Example
  - Using different methods to select and access elements.
*/

// Assuming HTML like:
// <div id="my-div">Div Content</div>
// <p>Paragraph 1</p><p>Paragraph 2</p>
// <span class="my-span">Span 1</span><span class="my-span">Span 2</span>
// <form name="myForm"><input name="one" value="Test"></form>
// <a href="http://example1.com">Link 1</a><a href="http://example2.com">Link 2</a>

let myIdElement = document.getElementById("my-div");
let myTagElements = document.getElementsByTagName("p");
let myClassElement = document.getElementsByClassName("my-span");
let myQueryElement = document.querySelector(".my-span");
let myQueryAllElement = document.querySelectorAll(".my-span");

console.log(myIdElement); // <div id="my-div">Div Content</div>
console.log(myTagElements[1]); // <p>Paragraph 2</p>
console.log(myClassElement[1]); // <span class="my-span">Span 2</span>
console.log(myQueryElement); // <span class="my-span">Span 1</span> (first match)
console.log(myQueryAllElement[1]); // <span class="my-span">Span 2</span>

console.log(document.title); // Title of the page
console.log(document.body); // <body> element
console.log(document.forms[0].one.value); // "Test" (value of the first form's input named "one")
console.log(document.links[1].href); // "http://example2.com" (href of the second link)
```

#### What Happens:
- **By ID**: `myIdElement` gets the `<div id="my-div">` element.
- **By Tag Name**: `myTagElements` is an `HTMLCollection` with two `<p>` elements; `[1]` accesses the second.
- **By Class Name**: `myClassElement` is an `HTMLCollection` with two `<span>` elements; `[1]` gets the second.
- **By Query Selector**: `myQueryElement` finds the first `.my-span` element.
- **By Query All**: `myQueryAllElement` is a `NodeList` with all `.my-span` elements; `[1]` gets the second.
- **Collections**:
  - `document.title` shows the page title.
  - `document.body` returns the `<body>` element.
  - `document.forms[0].one.value` accesses the value of the first form’s input.
  - `document.links[1].href` gets the `href` of the second link.

#### Assumed HTML:
```html
<!DOCTYPE html>
<html>
<head><title>My Page</title></head>
<body>
  <div id="my-div">Div Content</div>
  <p>Paragraph 1</p><p>Paragraph 2</p>
  <span class="my-span">Span 1</span><span class="my-span">Span 2</span>
  <form name="myForm"><input name="one" value="Test"></form>
  <a href="http://example1.com">Link 1</a><a href="http://example2.com">Link 2</a>
  <script src="dom-selectors.js"></script>
</body>
</html>
```

---


- **Live vs Static**: `getElementsBy*` returns live collections (updates with DOM changes), while `querySelectorAll` returns a static `NodeList`.
- **Indexing**: Use `[n]` for collections, but check `length` to avoid out-of-bounds errors.
- **Case Sensitivity**: Tag names are case-insensitive; IDs and classes depend on HTML.
- **Debug**: Log elements and use `console.dir()` to inspect their properties.
