## Binary Search

```javascript
function binarySearch(nums, target) {
  let low = 0; // high and low follow the part of the list we are searching
  let high = nums.length;

  while (low < high) { // while we don't find
      let mid = Math.floor((high - low) / 2); // check the central item
      let guess = nums[mid];
      if (guess === target) { // found the target
        return mid;
      }
      if (guess > target) { // the guess was too high
        high = mid - 1;
      } else { // the guess was too low
        low = mid + 1;
      }
  }

  return null; // target not found
};

const list = [3, 4, 7, 9, 13];

console.log(binarySearch(list, 9)); // prints 3
console.log(binarySearch(list, 50)); // prints null
```