
## Object - Create Object With Assign Method

### What Is `Object.assign()`?
- **Definition**: A method that copies all enumerable own properties from one or more source objects to a target object, returning the target.
- **Syntax**: `Object.assign(target, ...sources)`
  - `target`: The object to copy properties into.
  - `...sources`: One or more objects to copy from.
- **Use It**: To combine objects or create a new one with merged properties.

#### Example:
- We’ll merge objects using `Object.assign()` and explore its behavior.

#### Code:
```javascript
/*
  Object.assign Example
  - Merging objects with target and new properties.
*/

let obj1 = {
  prop1: 1,
  meth1: function () {
    return this.prop1;
  },
};

let obj2 = {
  prop2: 2,
  meth2: function () {
    return this.prop2;
  },
};

let targetObject = {
  prop1: 100,
  prop3: 3,
};

let finalObject = Object.assign(targetObject, obj1, obj2);

finalObject.prop1 = 200; // Modifies targetObject since it's the same reference
finalObject.prop4 = 4;   // Adds new property

console.log(finalObject);

let newObject = Object.assign({}, obj1, { prop5: 5, prop6: 6 }); // Creates new object

console.log(newObject);
```

#### What Happens:
- **First Assignment (`finalObject`)**:
  - `targetObject` starts with `prop1: 100`, `prop3: 3`.
  - `Object.assign(targetObject, obj1, obj2)` merges:
    - `obj1`’s `prop1: 1` overwrites `targetObject.prop1` (last value wins).
    - `obj1.meth1` is added.
    - `obj2`’s `prop2: 2` and `meth2` are added.
  - Resulting `finalObject` (same as `targetObject`): `{ prop1: 1, prop3: 3, prop2: 2, meth1: [Function], meth2: [Function] }`.
  - `finalObject.prop1 = 200` updates `prop1` to 200.
  - `finalObject.prop4 = 4` adds a new property.
  - `console.log(finalObject)`: `{ prop1: 200, prop3: 3, prop2: 2, prop4: 4, meth1: [Function], meth2: [Function] }`.

- **Second Assignment (`newObject`)**:
  - `Object.assign({}, obj1, { prop5: 5, prop6: 6 })` creates a new object (`{}` as target).
  - Merges `obj1`’s `prop1: 1` and `meth1`, then adds `prop5: 5` and `prop6: 6`.
  - `console.log(newObject)`: `{ prop1: 1, meth1: [Function], prop5: 5, prop6: 6 }`.

#### Output (Approximate):
```
{ prop1: 200, prop3: 3, prop2: 2, prop4: 4, meth1: [Function: meth1], meth2: [Function: meth2] }
{ prop1: 1, meth1: [Function: meth1], prop5: 5, prop6: 6 }
```

---

### Key Points
- **Overwriting**: Properties from later sources overwrite earlier ones (e.g., `obj1.prop1` overwrites `targetObject.prop1`).
- **Reference**: `finalObject` is the same object as `targetObject`, so changes affect the original.
- **New Object**: Using `{}` as the target creates a fresh object, avoiding modification of sources.
- **Methods**: Functions like `meth1` and `meth2` are copied as properties, retaining their `this` context.

---


- **Shallow Copy**: `Object.assign()` only copies the first level—nested objects are referenced, not cloned.
- **Immutable Sources**: Use a new target (`{}`) to preserve original objects.
- **Order Matters**: Later sources override earlier ones.
- **Test Methods**: Call `finalObject.meth1()` or `newObject.meth1()` to see `this.prop1` in action.
