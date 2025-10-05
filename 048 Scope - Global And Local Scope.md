## Scope - Global And Local Scope

### 1. Global Scope
- What it is: Variables declared outside any function or block are in the global scope, accessible everywhere in the code.
- Behavior: 
  - `var` variables are globally scoped if declared outside functions (and redeclared inside won’t affect the global unless assigned).
  - `let` and `const` are block-scoped but become globally accessible if declared in the global context.

### 2. Local Scope
- What it is: Variables declared inside a function or block are local, only accessible within that function or block.
- Behavior: 
  - `var` is function-scoped, meaning it’s local to the function it’s declared in.
  - `let` and `const` are block-scoped, limited to the `{}` block they’re in.

#### Example:
- We’ll define variables globally and locally to compare their behavior.

#### Code:
```javascript
/*
  Scope Example
  - Global vs Local scope with var and let.
*/

var a = 1; // Global scope
let b = 2; // Global scope

function showText() {
  var a = 10; // Local scope (function-scoped)
  let b = 20; // Local scope (block-scoped)
  console.log(`Function - From Local ${a}`); // 10
  console.log(`Function - From Local ${b}`); // 20
}

console.log(`From Global ${a}`); // 1
console.log(`From Global ${b}`); // 2

showText();
```

#### What Happens:
- **Global Variables**:
  - `var a = 1` is globally scoped.
  - `let b = 2` is globally scoped but block-scoped by nature (no block here, so global access).
  - `console.log(`From Global ${a}`)` prints `1`.
  - `console.log(`From Global ${b}`)` prints `2`.

- **Local Variables**:
  - Inside `showText()`, `var a = 10` creates a new local `a`, shadowing the global `a`.
  - `let b = 20` creates a new local `b`, shadowing the global `b`.
  - `console.log(`Function - From Local ${a}`)` prints `10`.
  - `console.log(`Function - From Local ${b}`)` prints `20`.

- **Output**:
  ```
  From Global 1
  From Global 2
  Function - From Local 10
  Function - From Local 20
  ```

---

The difference (var vs let):
```javascript
function show() {
  var x = 10; // function scoped
  if (true) {
    let y = 20; // block scoped
    var z = 30; // still function scoped
  }
  console.log(x); // ✅ 10
  console.log(z); // ✅ 30 (because var ignores blocks)
  console.log(y); // ❌ Error (because let works only inside that block)
}
```

---


- **Scope Choice**: Use `let` or `const` for block control; `var` for legacy or function-wide variables.
- **Avoid Global**: Minimize global variables to prevent conflicts.
- **Debug**: Use `console.log` to trace which scope a variable comes from.
- **Block Scope**: Add `{}` to test `let`’s block behavior (e.g., `if (true) { let b = 3; }`—`b` is inaccessible outside).
