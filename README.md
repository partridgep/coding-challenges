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

## computeRemainder

_Prompt:_

- Write a function named computeRemainder that accepts two numeric arguments and returns the remainder of the division of those two numbers.
- The first argument should be the dividend and the second argument should be the divisor.
- If a 0 is passed in as the second argument you should return JavaScript's special numeric value: Infinity.
- For extra fun, complete this challenge without using the modulus (%) operator.

_My solution:_

```
function computeRemainder(a, b) {
  let result;
  if (b === 0) {
    return Infinity;
  } else {
    while (a >= b) {
      a = a - b;
    }
    return a;
  };
};
```

##range

_Prompt:_

- Write a function called range that accepts two integers as arguments and returns an array of integers starting with the first argument up to one less than the second argument.
- The range function must be called with the first argument less than or equal to the second argument, otherwise return the string "First argument must be less than second".

_My solution:_

```
function range(a, b) {
  let array = [];
  if (a > b) {
    return "First argument must be less than second.";
  } else {
    while (a < b) {
      array.push(a);
      a++;
    };
    return array;
  };
};
```

##reverseUpcaseString

_Prompt:_

- Write a function called reverseUpcaseString that accepts a single string argument, then returns the string with its characters in reverse order and converts all characters to uppercase.

_My solution:_

```
function reverseUpcaseString(str) {
  let convertedStr = "";
  for (i=str.length-1; i >= 0; i--) {
    convertedStr += str[i].toUpperCase();
  };
  return convertedStr;
};
```

##charCount

_Prompt:_

- Write a function named charCount that accepts a single string argument and returns an object that represents the count of each character in the string.
- The returned object should have keys that represent the character with its value set to the how many times the character appears in the string argument.
- Upper and lower case characters should be counted separately.
- Space characters should be counted too.

_My solution:_

```
function charCount(str) {
  let countObj = {};
  for (i=0; i<str.length; i++) {
    if (!countObj[str[i]]) countObj[str[i]] = 1;
    else countObj[str[i]] += 1
  };
  return countObj;
};
```





