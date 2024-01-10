# Differences between Map and WeakMap

## Map

- In a normal `Object`, the keys of key-value pairs can only be strings.

- In a `Map`, the keys can be of any type.

- Actually, a `Map` is an array, and each of its elements is also an array. The structure is as follows:

  ```js
  const map = [
       ["name","张三"],
       ["age",18],
  ]
  ```

- If the key of a `Map` is a primitive data type, as long as two keys are strictly the same, they are considered to be the same key.

## WeakMap

WeakMap object is also a set of key-value sets, where keys are weakly referenced. **The key must be an object** , the original data type cannot be used as a key value, but the value can be arbitrary. 

The purpose of `WeakMap` is to allow us to store some data on an object, which typically creates a strong reference to that object. In `WeakMap`, the references to objects as keys are weak, meaning that if there are no other references to the object, it can be automatically collected by the garbage collection mechanism, thereby freeing up memory. This avoids memory leaks that can occur due to additional references.



