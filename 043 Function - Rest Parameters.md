## Function - Rest Parameters

### 1. Rest Parameters
- What it is: Allows a function to accept an indefinite number of arguments as an array, using the `...` syntax.
- Use it: Perfect for functions that need to process multiple inputs (e.g., summing numbers).

### 2. Only One Allowed
- Rule: You can only have one rest parameter in a function, and it collects all remaining arguments into an array.

### 3. Must Be Last Element
- Rule: The rest parameter must be the last parameter in the function definition—nothing can follow it.

#### Example:
- We’ll create a function to calculate the sum of any number of values using rest parameters.

#### Code:
```javascript
/*
  Rest Parameters Example
  - Summing multiple numbers with rest params.
*/

function calc(...numbers) {
  // console.log(Array.isArray(numbers)); // true (confirms it's an array)
  let result = 0
  for (let i = 0; i < numbers.length; i++) {
    result += numbers[i] // result = result + numbers[i]
  }
  return `Final Result Is ${result}`
}

console.log(calc(10, 20, 10, 30, 50, 30)) // "Final Result Is 150"
```

#### What Happens:
- **Rest Parameter**: `...numbers` collects all arguments (`10, 20, 10, 30, 50, 30`) into an array `numbers = [10, 20, 10, 30, 50, 30]`.
- **Loop**: Iterates over the array, adding each number to `result` (0 + 10 + 20 + 10 + 30 + 50 + 30 = 150).
- **Return**: Returns the string `"Final Result Is 150"`.
- **Output**: `console.log` prints the result.

---

### Testing Variations:
```javascript
console.log(calc(5)) // "Final Result Is 5"
console.log(calc(1, 2, 3)) // "Final Result Is 6"
console.log(calc()) // "Final Result Is 0" (empty array, result stays 0)
```

---


- **Array Access**: Treat `numbers` like any array—use `for`, `map`, or other array methods.
- **Single Use**: Only one `...` per function—e.g., `function calc(a, ...b)` is fine, but `function calc(...a, b)` is invalid.
- **Last Position**: `...numbers` must come after any regular parameters (e.g., `function calc(prefix, ...numbers)`).
- **Default**: Combine with default params like `function calc(...numbers = [])` to handle empty calls.
