# Hoisting

> Hoisting is the default behaviour of javascript where all the variable and function declarations are moved on top.
>
> This means that irrespective of where the variables and functions are declared, they are moved on top of the scope. The scope can be both local and global.



Hoisting in JavaScript can be understood by breaking it down into two main aspects: variable hoisting and function hoisting.

1. **Variable Hoisting**:
   Variable declarations are moved to the top of their containing scope during the compilation phase. However, only the declarations themselves are hoisted, not their initializations. The variable is initialized with the value `undefined` until its assignment statement is reached in the code.

Example:

```javascript
console.log(x); // Output: undefined
var x = 10;
console.log(x); // Output: 10
```

In this example, the variable `x` is hoisted to the top of the scope, but its value is `undefined` before the assignment statement `var x = 10;`. The first `console.log` outputs `undefined`, and the second one outputs `10`.

2. **Function Hoisting**:
   Function declarations are also hoisted to the top of their containing scope. Unlike variables, functions can be called before their declaration in the code, as they are fully hoisted.

Example:

```javascript
foo(); // Output: "Hello, I am foo."

function foo() {
	console.log("Hello, I am foo.");
}
```

In this example, the function `foo` is hoisted to the top of the scope, so it can be called before its actual declaration in the code. The output of the `foo()` call is `"Hello, I am foo."`.

It's important to note that hoisting works differently for function expressions. Function expressions (where a function is assigned to a variable) are hoisted as variables, not as functions.

Function expression example:

```javascript
bar(); // Output: Uncaught TypeError: bar is not a function

var bar = function () {
	console.log("Hello, I am bar.");
};
```

In this example, the variable `bar` is hoisted, but its value is `undefined`. The `bar()` call before the function expression assignment results in a `TypeError` since `bar` is not yet assigned a function.

To avoid confusion and potential issues related to hoisting, it is generally recommended to declare variables and functions before using them in your code. This improves code readability and ensures that your code behaves as expected.


> **Note - Variable initializations are not hoisted, only variable declarations are hoisted:**

```javascript
var x;
console.log(x); // Outputs "undefined" since the initialization of "x" is not hoisted
x = 23;
```


> **Note - To avoid hoisting, you can run javascript in strict mode by using “use strict” on top of the code:**

```javascript
"use strict";
x = 23; // Gives an error since 'x' is not declared
var x; 

```
