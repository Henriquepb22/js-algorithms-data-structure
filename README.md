# Javascript Algorithms and Data Structures

1. [Big O](#big-o)

## Big O

### Motivation

We needed a way of measuring our algorithms complexity, if we have multiple solutions for the same problem which one
is the best? (run faster or with less computational impact)

### Classifications

To classify a algorithm we count the inputs X operations changes to check if it grows **constant, linear, exponential, logaritm or X**

- Constant or O(1): changing the input won't change the numbers of operations

Example:
```javascript
function isEven(n) {
  return n % 2 === 0;
};
```
*every time we change `n` the number of operations still the same (the remainer(%) and the indentity(===) are the operations)*

- Linear O(n): changing the input the number of operations grows equality to it

Example:
```javascript
function countUntil(n) {
  for(let i = 0; i <= n; i++) {
    console.log(n);
  };
}
```

*every time we change `n` the number of operations grows equal to it, here we have 3 operations the asignment(i = 0) the less equal then(i <= n) and the increment(i++) so if `n` is 1 we have 3 operations but if `n` is 5 we have 11(1+5x2) operations because the less equal then and the increment will run N times*

- Exponential O(n²): changing the input the number of operations grows exponential to it

Example:
```javascript
function printPairs(n) {
  for(let i = 0; i <= n; i++) {
    for(let y = n; y > i; y--) {
      console.log(i, y);
    };
  };
}
```

*here every time we change `n` the number of operations grow exponential to it, we got 6 operations (i = 0, i <= n, i++, y = n, y > i and y--) but for every `i` we got `n` times of `y` operations so if `n` is 1 we have 6 operations, but if `n` is 5 we got 111(1+5x2(1+5x2)) operations*