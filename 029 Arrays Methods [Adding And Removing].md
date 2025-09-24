## Arrays Methods [Adding And Removing]

### 1. unshift("", "") - Add Element To The First
- What it does: Adds one or more elements to the start of the array and shifts existing ones up.
- Returns: The new length of the array.

#### Example:
```javascript
/*
  unshift Example
  - Adding elements to the beginning.
*/

let myFriends = ["Ahmed", "Mohamed", "Sayed", "Alaa"]
console.log(myFriends) // ["Ahmed", "Mohamed", "Sayed", "Alaa"]

myFriends.unshift("Osama", "Nabil")
console.log(myFriends) // ["Osama", "Nabil", "Ahmed", "Mohamed", "Sayed", "Alaa"]
```

---

### 2. push("", "") - Add Element To The End
- What it does: Adds one or more elements to the end of the array.
- Returns: The new length of the array.

#### Example:
```javascript
/*
  push Example
  - Adding elements to the end.
*/

myFriends.push("Samah", "Eman")
console.log(myFriends) // ["Osama", "Nabil", "Ahmed", "Mohamed", "Sayed", "Alaa", "Samah", "Eman"]
```

---

### 3. shift() - Remove First Element From Array
- What it does: Removes the first element and shifts everything else down.
- Returns: The removed element.

#### Example:
```javascript
/*
  shift Example
  - Removing the first element.
*/

let first = myFriends.shift()
console.log(myFriends) // ["Nabil", "Ahmed", "Mohamed", "Sayed", "Alaa", "Samah", "Eman"]
console.log(`First Name Is ${first}`) // "First Name Is Osama"
```

---

### 4. pop() - Remove Last Element From Array
- What it does: Removes the last element from the array.
- Returns: The removed element.

#### Example:
```javascript
/*
  pop Example
  - Removing the last element.
*/

let last = myFriends.pop()
console.log(myFriends) // ["Nabil", "Ahmed", "Mohamed", "Sayed", "Alaa", "Samah"]
console.log(`Last Name Is ${last}`) // "Last Name Is Eman"
```

---


- **Order**: `unshift()` and `shift()` mess with the start, `push()` and `pop()` with the end—think of it like a stack or queue.
- **Return Values**: Save `shift()` or `pop()` to a variable to keep the removed item.
- **Performance**: Adding/removing from the end (`push`/`pop`) is faster than the start (`unshift`/`shift`) because it doesn’t shift indices.
- **Check Length**: Use `myFriends.length` after to see the new size.
