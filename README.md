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
  return arr.reduce((accumulator, item) => {return accumulator + item}, 0);
};
```

### addList

_Prompt:_

- Write a function called addList that accepts any quantity of numbers as arguments, 
  adds them together and returns the resulting sum.
- Assume all parameters will be numbers.
- If called with no arguments, return 0 (zero).

_My solution:_

```
function addList(...num) {
 return num.reduce((accumulator, item) => {return accumulator + item}, 0);
};
```

### computeRemainder

_Prompt:_

- Write a function named computeRemainder that accepts two numeric arguments and returns the remainder of the division of those two numbers.
- The first argument should be the dividend and the second argument should be the divisor.
- If a 0 is passed in as the second argument you should return JavaScript's special numeric value: Infinity.
- For extra fun, complete this challenge without using the modulus (%) operator.

_My solution:_

```
function computeRemainder(num1, num2) {
  if (num2 === 0) return Infinity;
  let division = Math.abs(num1/num2);
  let decimal = division - Math.floor(division);
  return parseFloat((decimal * num2).toFixed(5));
};
```

### range

_Prompt:_

- Write a function called range that accepts two integers as arguments and returns an array of integers starting with the first argument up to one less than the second argument.
- The range function must be called with the first argument less than or equal to the second argument, otherwise return the string "First argument must be less than second".

_My solution:_

```
function range(a, b) {
 if (int1 > int2) return "First argument must be less than second";
  else {
    let arr = [];
    for (i=int1; i<int2; i++) {
      arr.push(i)
    }
    return arr;
  }
};
```

### reverseUpcaseString

_Prompt:_

- Write a function called reverseUpcaseString that accepts a single string argument, then returns the string with its characters in reverse order and converts all characters to uppercase.

_My solution:_

```
function reverseUpcaseString(str) {
  return str.split("").reverse().join("").toUpperCase();
};
```

### charCount

_Prompt:_

- Write a function named charCount that accepts a single string argument and returns an object that represents the count of each character in the string.
- The returned object should have keys that represent the character with its value set to the how many times the character appears in the string argument.
- Upper and lower case characters should be counted separately.
- Space characters should be counted too.

_My solution:_

```
function charCount(str) {
  let countObj = {};
  for (letter of str) {
    if (!countObj[letter]) countObj[letter] = 1;
    else countObj[letter]++;
  }
  return countObj;
};
```

### removeEnds

_Prompt:_

- Write a function called removeEnds that accepts a single string argument, then returns the a string with the first and last characters removed.
- If the length of the string argument is less than 3, return an empty string.

_My solution:_

```
function removeEnds(str) {
  return str.slice(1, -1);
}
```

### formatWithPadding

_Prompt:_

- Write a function called removeEnds that accepts a single string argument, then returns the a string with the first and last characters removed.
- If the length of the string argument is less than 3, return an empty string.

_My solution:_

```
function removeEnds(str) {
  return str.slice(1, -1);
}
```_Prompt:_

- Write a function called formatWithPadding that accepts three arguments:
  - A numeric argument (an integer) representing the number to format.
  - A string argument (a single character) representing the character used to "pad" the returned string to a minimum length.
  - Another numeric argument (an integer) representing the length to "pad" the returned string to.
- The function should return the integer as a string, "left padded" to the length of the 3rd arg using the character provided in the 2nd arg.
- If the length of the integer converted to a string is equal or greater than the 3rd argument, no padding is needed - just return the integer as a string.

_My solution:_

```
function formatWithPadding(formatNum, char, padLength) {
  formatNum = formatNum + "";
  while (formatNum.length < padLength) {
    formatNum = char + formatNum;
  }
  return formatNum;
}
```

## Difficulty: Intermediate

### isPalindrome

_Prompt:_

- Write a function called isPalindrome that accepts a single string argument, then returns true or false depending upon whether or not the string is a palindrome.
- A palindrome is a word or phrase that are the same forward or backward.
- Casing and spaces are not included when considering whether or not a string is a palindrome.
- If the length of the string is 0 or 1, return true.

_My solution:_

```
function isPalindrome(str) {
  if (str.length === 0 || str.length === 1) return true;
  str = str.replace(/\s/g, "").toLowerCase();
  if (str === str.split("").reverse().join("")) return true;
  else return false;
}
```

### hammingDistance

_Prompt:_

- Write a function named hammingDistance that accepts two arguments which are both strings of equal length.
- The function should return the count of the symbols (characters, numbers, etc.) at the same position within each string that are different.
- If the strings are not of the same length, the function should return NaN.

_My solution:_

```
function hammingDistance(str1, str2) {
  if (str1.length !== str2.length) return parseInt("a");
  let count = 0;
  arr1 = str1.split("");
  arr2 = str2.split("");
  arr3 = arr1.filter((char1, idx) => arr2[idx] !== char1);
  return arr3.length;
}
```


### mumble

_Prompt:_

- Write a function called mumble that accepts a single string argument.
- The function should return a string that has each character repeated the number of times according to its position within the string arg.  In addition, each repeated section of characters should be separated by a hyphen (-).

_My solution:_

```
function mumble(str) {
  arr = str.split("");
  mumbledArr = arr.map((char, idx) => {
    let repeat = 0;
    let mumbledChar = "";
    while (repeat <= idx) {
      mumbledChar += char;
      repeat++;
    }
    return mumbledChar;
  });
  let mumbledStr = mumbledArr.join("-");
  return mumbledStr;
}
```

### fromPairs

_Prompt:_

- Write a function named fromPairs that creates an object from an array containing nested arrays.
- Each nested array will have two elements representing key/value pairs used to create key/value pairs in an object to be returned by the function.
- If a key appears in multiple pairs, the rightmost pair should overwrite previous the previous entry in the object.

_My solution:_

```
function fromPairs(arr) {
  let obj = {};
  for (nestedArr of arr) {
    let key = nestedArr[0];
    let value = nestedArr[1];
    obj[`${key}`] = value;
  }
  return obj;
}
```

### mergeObjects

_Prompt:_

- Write a function named mergeObjects that accepts at least two objects as arguments, merges the properties of the second through n objects into the first object, then finally returns the first object.
- If any objects have the same property key, values from the object(s) later in the arguments list should overwrite earlier values.

_My solution:_

```
function mergeObjects(...objects) {
  let finalObj = objects[0];
  for (obj of objects) {
    for (const [key, value] of Object.entries(obj)) {
      finalObj[key] = value;
    }
  }
  return finalObj;
}
```

### findHighestPriced

_Prompt:_

function mergeObjects(...objects) {
  let finalObj = objects[0];
  for (obj of objects) {
    for (const [key, value] of Object.entries(obj)) {
      finalObj[key] = value;
    }
  }
  return finalObj;
}

_My solution:_

```
function findHighestPriced(arr) {
  idxOfHighest = 0;
  highestPrice = 0;
  for (i = 0; i < arr.length; i++) {
    if (arr[i].price > highestPrice) {
      highestPrice = arr[i].price;
      idxOfHighest = i;
    }
  }
  return arr[idxOfHighest];
}
```


### mapArray

_Prompt:_

The goal is of this challenge is to write a function that performs the functionality of JavaScript's Array.prototype.map method.

- Write a function named mapArray that accepts two arguments: a single array and a callback function.
- The mapArray function should return a new array of the same length as the array argument.
- The mapArray function should iterate over each element in the array (first arg).  For each iteration, invoke the callback function (2nd arg), passing to it as arguments, the current element and its index.  Whatever is returned by the callback function should be included in the new array at the index of the current iteration.

_My solution:_

```
function mapArray(arr, fn) {
  let mappedArray = [];
  for (i = 0; i < arr.length; i++) {
    mappedArray.push(fn(arr[i], i));
  }
  return mappedArray;
}
```

### reduceArray

_Prompt:_

The goal is of this challenge is to write a function that performs the functionality of JavaScript's Array.prototype.reduce method.

- Write a function named reduceArray that accepts three arguments: (1) an array; (2) a callback function; and (3) a value used as the initial value of the "accumulator".
- The reduceArray function should return whatever is returned by the callback function on the last iteration.
- The reduceArray function should iterate over each element in the array (first arg).  For each iteration, invoke the callback function (2nd arg), passing to it three arguments: (1) the "accumulator", which is the value returned by the callback during the previous iteration; (2) the  current element; and (3) the index of the current iteration.
- On the first iteration, provide the third argument provided to reduceArray as the first argument when invoking the callback, then for subsequent iterations, provide the value returned by the callback during the previous iteration.

_My solution:_

```
function reduceArray(arr, fn, acc) {
  for (i = 0; i < arr.length; i++) {
    acc = fn(acc, arr[i], i);
  }
  return acc;
}
```







