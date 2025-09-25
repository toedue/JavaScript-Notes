## Arrays Methods [Sort]

### 1. sort(Function [Opt])
- What it does: Sorts the array in place (changes the original). By default, it converts everything to strings and sorts alphabetically or numerically based on Unicode.
- Optional Function: You can pass a compare function `(a, b) => a - b` for custom sorting (e.g., numbers).
- Catch: Mixed types (numbers and strings) can get messy—it treats them as strings!

#### Example:
```javascript
/*
  sort Example
  - Sorting a mixed array (numbers and strings).
*/

let myFriends = [10, "Sayed", "Mohamed", "90", 9000, 100, 20, "10", -20, -10]
console.log(myFriends) // [10, "Sayed", "Mohamed", "90", 9000, 100, 20, "10", -20, -10]

console.log(myFriends.sort()) // [-10, -20, 10, "10", 100, 20, "90", 9000, "Mohamed", "Sayed"]
```
#### JavaScript will:
Convert everything to strings.
Sort by Unicode order (character by character).

```javascript
["10", "Sayed", "Mohamed", "90", "9000", "100", "20", "10", "-20", "-10"]
```

Why this order?

-10 then -20

Compare as strings: "-10" vs "-20" → "1" < "2" → so -10 comes before -20.

10 and "10" stay next to each other

Number 10 vs string "10" → both compared as "10" → equal in sorting → order between them depends on implementation (stable sort in modern JS keeps original order).

100, 20, "90", 9000

"100" < "20" because "1" < "2".

"20" < "90" because "2" < "9".

"90" < "9000" because shorter string with same start comes first.

Strings last: "Mohamed", "Sayed"

"M" (77) < "S" (83).

#### final result
```javascript
[-10, -20, 10, "10", 100, 20, "90", 9000, "Mohamed", "Sayed"]
```

---

### 2. reverse()
- What it does: Reverses the array in place (flips the order of elements).
- Use it: After `sort()` to get descending order.

#### Example:
```javascript
/*
  reverse Example
  - Reversing the sorted array.
*/

console.log(myFriends.sort().reverse()) // ["90", "Sayed", "Mohamed", 9000, 20, 100, 10, -20, -10, "10"]
// Reverses the string-based sort result
```

---


- **String Sorting**: Default `sort()` treats all elements as strings, so `100` comes before `20` (because "1" < "2")—not numeric order!
- **Fix Numbers**: Use a compare function like `.sort((a, b) => a - b)` for true numeric sorting.
- **In Place**: Both `sort()` and `reverse()` modify the original array—make a copy with `[...myFriends]` if you need to preserve it.
- **Mixed Types**: Be cautious with strings and numbers together—it’ll coerce and might not do what you expect.
