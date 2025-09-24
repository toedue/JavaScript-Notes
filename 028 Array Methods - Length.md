
## Array Methods - Length

### What It Is
- **Length**: A property that tells you how many elements are in the array (or sets it if you assign a value).
- **Index Note**: Arrays start at index 0, so a length of 5 means indices 0 to 4.
- **Behavior**: If you set `length` to a smaller number, it truncates the array; if larger, it adds `undefined` slots.

#### Example:
```javascript
/*
  Length Property Example
  - Setting length to truncate the array.
*/

let myFriends = ["Ahmed", "Mohamed", "Sayed", "Alaa"]

myFriends.length = 2 // Truncates to first 2 elements

console.log(myFriends) // ["Ahmed", "Mohamed"]
```

#### What Happens:
- Original array: `["Ahmed", "Mohamed", "Sayed", "Alaa"]` (length 4).
- Setting `length = 2` removes "Sayed" and "Alaa" (indices 2 and 3).
- Result: `["Ahmed", "Mohamed"]`.

---


- **Truncation**: Reducing `length` deletes elements from the end—be careful, it’s permanent!
- **Expansion**: Increasing `length` adds `undefined` to the end (e.g., `myFriends.length = 5` adds two `undefined`s).
- **Check First**: Use `console.log(myFriends.length)` to see the current size before changing.
- **Index Limit**: The last valid index is always `length - 1`.

