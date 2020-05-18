### Coding Challenges
A repository of various coding challenges I've solved (to be constantly updated.)

## Difficulty: Basic

### sumNumbers

_Prompt:_

- Write a function called sumNumbers that accepts a single array of numbers and returns the sum of the numbers in the array.
- If the array is empty, return 0 (zero).

_My solution:_

```
function sumNumbers(arr) {
  let sum = 0;
  for (num of arr) {
    sum += num;
  };
  return sum;
};
```

## addList

_Prompt:_

- Write a function called addList that accepts any quantity of numbers as arguments, 
  adds them together and returns the resulting sum.
- Assume all parameters will be numbers.
- If called with no arguments, return 0 (zero).

_My solution:_

```
function addList(...nums) {
 let sum = 0;
 for (num of nums) {
  sum = sum + num;
 };
 return sum;
};
```

