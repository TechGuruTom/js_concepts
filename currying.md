# Currying	


Currying is a functional programming technique in JavaScript that involves transforming a function that takes multiple arguments into a sequence of functions, each taking a single argument. The curried function returns a new function for each argument until all the arguments are provided, and then the final result is returned.

In other words, currying allows you to break down a function with multiple arguments into a series of single-argument functions, making it easier to compose and reuse functions.

Here's an example of currying in JavaScript:

```javascript
// Non-curried function
function add(a, b, c) {
  return a + b + c;
}

console.log(add(1, 2, 3)); // Output: 6

// Curried version of the same function
function curryAdd(a) {
  return function(b) {
    return function(c) {
      return a + b + c;
    };
  };
}

const addCurried = curryAdd(1);
const add5 = addCurried(2);
const result = add5(3);

console.log(result); // Output: 6
```

In the example above, we have a simple function `add` that takes three arguments and returns their sum. We then create a curried version of the same function called `curryAdd`.

The `curryAdd` function is designed to take the first argument (`a`) and return a new function that takes the second argument (`b`). This new function, in turn, returns another function that takes the third argument (`c`) and computes the final result by adding `a`, `b`, and `c` together.

By calling `curryAdd(1)`, we get a function that takes `b`, which we store in the `addCurried` variable. When we call `addCurried(2)`, we get a new function that takes `c`, and we store this in the `add5` variable. Finally, we call `add5(3)` to get the result, which is 6.

Currying allows for more flexibility and composability in your code. It lets you partially apply arguments to functions, which can be useful in scenarios where you have functions with repetitive patterns of similar arguments or when building complex functional pipelines. Curried functions can also help with creating reusable higher-order functions and are a powerful technique in functional programming.
