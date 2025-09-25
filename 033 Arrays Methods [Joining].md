## Arrays Methods [Joining]

### 1. concat(array, array) => Return A New Array
- What it does: Merges two or more arrays (or values) into a new array, leaving the originals unchanged.
- Use it: Great for combining multiple lists into one.
- Accepts: Arrays, individual elements, or a mix.

#### Example:
```javascript
/*
  concat Example
  - Combining multiple arrays and elements.
*/

let myFriends = ["Ahmed", "Sayed", "Ali", "Osama", "Gamal", "Ameer"]
let myNewFriends = ["Samar", "Sameh"]
let schoolFriends = ["Haytham", "Shady"]

let allFriends = myFriends.concat(myNewFriends, schoolFriends, "Gameel", [1, 2])
console.log(allFriends) // ["Ahmed", "Sayed", "Ali", "Osama", "Gamal", "Ameer", "Samar", "Sameh", "Haytham", "Shady", "Gameel", 1, 2]
```

---

### 2. join(Separator)
- What it does: Turns an array into a string, joining all elements with a specified separator (default is a comma).
- Use it: Perfect for creating readable text from arrays.
- Options: Separator can be any string (e.g., space, `@`, `|`) or empty for no separation.

#### Examples:
```javascript
/*
  join Examples
  - Joining with different separators.
*/

console.log(allFriends.join()) // "Ahmed,Sayed,Ali,Osama,Gamal,Ameer,Samar,Sameh,Haytham,Shady,Gameel,1,2"
console.log(allFriends.join("")) // "AhmedSayedAliOsamaGamalAmeerSamarSamehHaythamShadyGameel12"
console.log(allFriends.join(" @ ")) // "Ahmed @ Sayed @ Ali @ Osama @ Gamal @ Ameer @ Samar @ Sameh @ Haytham @ Shady @ Gameel @ 1 @ 2"
console.log(allFriends.join("|")) // "Ahmed|Sayed|Ali|Osama|Gamal|Ameer|Samar|Sameh|Haytham|Shady|Gameel|1|2"
console.log(allFriends.join("|").toUpperCase()) // "AHMED|SADED|ALI|OSAMA|GAMAL|AMEER|SAMAR|SAMEH|HAYTHAM|SHADY|GAMEEL|1|2"
```

---


- **concat()**: Non-destructive—makes a new array, so your originals stay safe.
- **join()**: Returns a string, not an array—chain with methods like `toUpperCase()` for extra flair.
- **Separator**: Empty string (`""`) mashes everything together; use spaces or symbols for readability.
- **Mixing Types**: `concat()` handles numbers, strings, and arrays seamlessly—useful for diverse data.
