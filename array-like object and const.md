## What is array-like object? How to convert an array-like object to an array.

- Array-like objects are similar to arrays but cannot call array methods. This is because while they may have indexed elements and a `length` property, they do not inherit from `Array.prototype`. 
- Common array-like objects include:
  - **Function's `arguments` Object**: Within a function body, `arguments` is an array-like object that contains all the arguments passed to the function.
  - **DOM Manipulation Return Objects**: For example, `document.getElementsByTagName()` returns an array-like object, not a real array.
  - **Strings (String)**: Strings are also array-like objects because you can access characters in a string using an index, and they have a `length` property.

* To convert an array-like object to an array, use `Array.from(arrayLike);`.

## Can a variable defined with `const` be mutable?

The `const` ensures the variable's reference to the object in the memory does not change.

**Primitive Types (e.g., Number, String, Boolean)**:

- When a `const` variable stores a primitive type, the value itself is immutable. This means once the value is set, you cannot change it. Primitive types in JavaScript are immutable by nature.

**Reference Types (e.g., Objects, Arrays)**:

- When a `const` variable stores a reference type, the variable holds a reference (or pointer) to the object in memory. The `const` ensures that this reference cannot be changed to point to a different object or array. However, the contents of the object or array can still be modified.