# Adding Big Numbers

## Problem Description

Write a function that when given two numbers as strings, adds them together and returns the result as a string.

- The input numbers are big.
- The input is a string of only digits.
- The numbers are positive.

```
input: "123", "456"
output: "579"
```

```
input: "123", "75"
output: "198"
```

## Solution Approach

1. Pad the shorter string with zeros to make both strings the same length.
2. Add the two strings together, digit by digit, starting from the rightmost digit.
3. If the sum of two digits plus the carry is greater than 9, then the carry is 1 and the result is the sum modulo 10.
4. If the sum of two digits plus the carry is less than 10, then the carry is 0 and the result is the sum.
5. If there is a carry left at the end, add it to the result.

## Code Implementation

```js
function add(a, b) {
  const maxLength = Math.max(a.length, b.length);
  a = a.padStart(maxLength, '0');
  b = b.padStart(maxLength, '0');

  let carry = 0;
  let result = '';

  for (let i = maxLength - 1; i >= 0; i--) {
    const sum = parseInt(a[i]) + parseInt(b[i]) + carry;
    result = (sum % 10) + result;
    carry = Math.floor(sum / 10);
  }

  if (carry > 0) {
    result = carry + result;
  }

  return result;
}
```

## Test Cases

```js
console.log(add('123', '456')); // "579"
console.log(add('123', '75')); // "198"
```
