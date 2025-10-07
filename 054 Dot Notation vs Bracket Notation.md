## Object

### 1. Dot Notation vs Bracket Notation
- **Dot Notation** (`object.key`):
  - **What It Is**: A direct way to access properties using a literal name.
  - **Use It**: When the property name is a fixed, valid identifier (e.g., no spaces, starts with a letter).
  - **Example**: `user.theName` or `user.country`.
  - **Limitation**: Can’t use with dynamic values or special characters (e.g., `user."full name"` won’t work).

- **Bracket Notation** (`object["key"]`):
  - **What It Is**: Allows accessing properties using a string, which can be a variable or expression.
  - **Use It**: When the property name is dynamic, contains spaces, or uses special characters.
  - **Example**: `user[myVar]` or `user["full name"]`.
  - **Advantage**: More flexible for computed or variable property names.

### 2. Dynamic Property Name
- **What It Is**: A property name determined at runtime, often using a variable or expression inside bracket notation.
- **Use It**: To access or set properties based on user input, loops, or computed values.
- **Example**: `user[myVar]` uses the value of `myVar` ("country") as the property name.

#### Example:
- We’ll create a `user` object and explore different ways to access its properties, including a dynamic name.

#### Code:
```javascript
/*
  Object Dig Deeper Example
  - Comparing dot and bracket notation with dynamic property name.
*/

let myVar = "country"

let user = {
  theName: "Osama",
  country: "Egypt",
}

console.log(user.theName) // "Osama"
console.log(user.country) // "Egypt"
console.log(user.myVar) // undefined
console.log(user[myVar]) // "Egypt"
```

#### What Happens:
- **Dot Notation**:
  - `user.theName` accesses the property directly, logging `"Osama"`.
  - `user.country` accesses the property directly, logging `"Egypt"`.
  - `user.myVar` tries to access a property named `"myVar"` (which doesn’t exist), logging `undefined`.

- **Bracket Notation**:
  - `user[myVar]` evaluates `myVar` (which is `"country"`) and accesses the `country` property, logging `"Egypt"`.

- **Key Insight**:
  - Dot notation looks for the literal property name.
  - Bracket notation interprets the expression inside as the property name, making it dynamic.

---

### Key Differences
| Aspect             | Dot Notation         | Bracket Notation      |
|---------------------|----------------------|------------------------|
| **Syntax**          | `object.key`         | `object["key"]`        |
| **Property Name**   | Literal only         | String or variable     |
| **Dynamic Use**     | No                   | Yes                    |
| **Special Characters** | No (e.g., spaces) | Yes (e.g., `"full name"`) |

#### Dynamic Example with Variable:
```javascript
let prop = "theName"
console.log(user[prop]) // "Osama"
```

#### Special Characters Example:
```javascript
user["full name"] = "Osama Mohamed"
console.log(user["full name"]) // "Osama Mohamed"
// user.full name would cause a syntax error
```

---


- **Dynamic Keys**: Use bracket notation for loops or user input (e.g., `let key = prompt("Enter key"); console.log(user[key]);`).
- **Safety**: Check if a property exists (e.g., `user[key] !== undefined`) to avoid errors.
- **Adding Properties**: `user[newProp] = "Value";` works with variables (e.g., `let newProp = "city"; user[newProp] = "Cairo";`).
- **Performance**: Dot notation is slightly faster for fixed names, but the difference is negligible in most cases.
