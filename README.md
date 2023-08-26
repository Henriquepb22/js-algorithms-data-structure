# Javascript Algorithms and Data Structures

This repository is a developer diary that I will use as I'm reading the [Grokking Algorithms: An Illustrated Guide for Programmers and Other Curious People](https://www.amazon.com/Grokking-Algorithms-illustrated-programmers-curious/dp/1617292230) book, I will add examples for each part of it with javascript examples

1. [Big O (WIP)](#big-o)
2. Bubble Sort (TO DO)
3. Selection Sort (TO DO)
4. Insertion Sort (TO DO)
5. Merge Sort (TO DO)
6. Quick Sort (TO DO)
7. Radix Sort (TO DO)
8. Linked List (TO DO)
9. Stack & Queue (TO DO)
10. Binary Tree (TO DO)
11. Binary Heap (TO DO)
12. Hash Table (TO DO)
13. Graph (TO DO)

## Big O

### Motivation

We needed a way of measuring our algorithms complexity, if we have multiple solutions for the same problem which one
is the best? (run faster or with less computational impact)

### Classifications

### Time complexity

The time complexity is how the runtime of a algorithm will change if the input size increase/decrease, to classify a algorithm we count the `inputs X operations` changes to check if it grows **constant, linear, exponential or logarithmic**.

#### Constant - O(1)

Changing the input won't change the numbers of operations

*example:*
```javascript
function isEven(n) {
  return n % 2 === 0;
};
```
>Every time we change `n` the number of operations still the same (the remainer(%) and the indentity(===) are the operations)

#### Linear - O(n)

Changing the input the number of operations grows equality to it

*example:*
```javascript
function countUntil(n) {
  for(let i = 0; i <= n; i++) {
    console.log(n);
  };
}
```

>Every time we change `n` the number of operations grows equal to it, here we have 3 operations the asignment(i = 0) the less equal then(i <= n) and the increment(i++) so if `n` is 1 we have 3 operations but if `n` is 5 we have 11(1+5x2) operations because the less equal then and the increment will run N times

#### Exponential - O(n²)

Changing the input the number of operations grows exponential to it

*example:*
```javascript
function printPairs(n) {
  for(let i = 0; i <= n; i++) {
    for(let y = n; y > i; y--) {
      console.log(i, y);
    };
  };
}
```

>Here every time we change `n` the number of operations grow exponential to it, we got 6 operations (i = 0, i <= n, i++, y = n, y > i and y--) but for every `i` we got `n` times of `y` operations so if `n` is 1 we have 6 operations, but if `n` is 5 we got 111(1+5x2(1+5x2)) operations

#### Classification Shorthands

1. Arithmetic operations are constants
2. Variable assignment is constant
3. Acessing elements in a array by index or object is constant
4. In a loop the complexity is the length of the loop times the complexity of what is inside it

### Space Complexity

The space complexity is how the memory allocation of a algorithm will change if the input changes, to classify a algorithm we count the `inputs X assignments/memory` allocation changes to check if it grows **constant, linear, exponential or logarithmic**.

#### Constant - O(1)

Changing the input won't change the numbers of memory allocation

*example:*
```javascript
function isEven(n) {
  const isEven = n % 2 === 0;
  return isEven;
};
```
>Every time we change `n` the number of assignments still the same (the const isEven = n % 2 === 0)

#### Linear - O(n)

Changing the input the number of assignments grows equality to it

*example:*
```javascript
function populateArrayWith(n) {
  const arr = [];
  for(let i = 0; i <= n; i++) {
    arr.push(i);
  };
  console.log(arr);
}
```

>Every time we change `n` the length of the array grows equal to it, here for every for loop we push a new element `i` to the array

#### Exponential O(n²)

Changing the input the length of the matrix grows exponential to it

*example:*
```javascript
function createMatrix(n) {
  const matrix = [];
  for (let i = 0; i < n; i++) {
    const row = [];
    for (let j = 0; j < n; j++) {
      row.push(i + j);
    }
    matrix.push(row);
  }
  return matrix;
}
```

>Here every time we change `n` the memory allocation grow exponential to it, in the first for loop for every `i` we create a matrix row and inside it we have another for loop for every `j` we push `i+j` to the row and after that push the row to the matrix

#### Classification Shorthands

1. Primitives values (boolean, number, undefined, null) are constant space
2. Strings require O(n) space where n is the string length
3. Arrays and Object require O(n) space where n is the size of the array or the number of keys in the object