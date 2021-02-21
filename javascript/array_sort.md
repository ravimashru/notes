# The Array `sort()` method

- Array is sorted in place, and sorted array is returned.
- Default sort is in ascending order by converting each element to string.
- Custom sort order can be specified using a callback function `compareFunction(a, b)`
  - When function returns < 0, `a` appears before `b` in sorted array.
  - When function return 0, `a` and `b` remain unchanged with respect to each other.
  - When function returns > 0, `b` appears before `a` in sorted array.
