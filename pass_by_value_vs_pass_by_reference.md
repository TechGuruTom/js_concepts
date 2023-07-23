# "Passed by value" and "passed by reference"

"Passed by value" and "passed by reference" are terms used to describe how data is transferred between variables or functions in programming languages. They refer to two different ways of handling data when it is used as an argument to a function or when it is assigned to another variable.

1. Passed by Value:
   In languages that use "passed by value," a copy of the data is created and passed to the function or assigned to another variable. Any changes made to the copied data within the function or the new variable do not affect the original data outside the function or the original variable.

Primitive data types, such as numbers, booleans, and strings, are typically passed by value in most programming languages.

Here's an example in JavaScript:

```javascript
function modifyNumber(num) {
  num = num * 2; // A copy of the number is created and modified
  return num;
}

let originalNumber = 5;
let modifiedNumber = modifyNumber(originalNumber);

console.log(originalNumber); // Output: 5 (originalNumber remains unchanged)
console.log(modifiedNumber); // Output: 10 (modifiedNumber holds the modified value)
```

2. Passed by Reference:
   In languages that use "passed by reference," a reference or memory address of the data is passed to the function or assigned to another variable. Any changes made to the data within the function or the new variable will directly affect the original data outside the function or the original variable.

Complex data types, such as objects and arrays, are often passed by reference in many programming languages.

Here's an example in JavaScript:

```javascript
function modifyArray(arr) {
  arr.push(4); // The original array is modified
  return arr;
}

let originalArray = [1, 2, 3];
let modifiedArray = modifyArray(originalArray);

console.log(originalArray); // Output: [1, 2, 3, 4] (originalArray is modified)
console.log(modifiedArray); // Output: [1, 2, 3, 4] (modifiedArray points to the same array)
```

In the example above, `originalArray` is modified directly inside the `modifyArray` function, and those changes are reflected in the `modifiedArray` as well since both variables point to the same array in memory.

It's essential to understand whether a language behaves as "passed by value" or "passed by reference" because it affects how you work with data inside functions and how you manage data mutation. In JavaScript, primitive data types are passed by value, while objects and arrays are passed by reference.
