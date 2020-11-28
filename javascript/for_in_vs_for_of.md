# for-in vs for-of

```javascript
const arr = [1, 1, 2, 3, 5];

const obj = {
  foo: 'bar',
  foo2: ['b', 'ba', 'bar']
};
```

## for-in on arrays prints indices
```javascript
for (let i in arr) {
  console.log(i);
}
```

Output:
```
0
1
2
3
4
```

## for-of on arrays prints its elements
```javascript
for (let i of arr) {
  console.log(i);
}
```

Output:
```
1
1
2
3
5
```

## for-in on objects prints keys
```javascript
for (let i in obj) {
  console.log(i);
}
```

Output:
```
foo
foo2
```

## for-of on objects: EXCEPTION!
```javascript
for (let i of obj) {
  console.log(i);
}
```

Exception:
```
for (let i of obj) {
  ^

TypeError: obj is not iterable
```
