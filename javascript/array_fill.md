# Array Fill

Use `fill` method to create a new array and fill it with a default value.

Example:

```javascript
const a = new Array(3).fill(-1);

// Result: a = [-1, -1, -1]
```

The `fill` method can be called on an existing array as well to fill it with the defined value.

Creating a two-dimensional array with an initial value (e.g. 3x5 matrix):

```javascript
const a = [...Array(3)].map(e => Array(5).fill(0))
```
