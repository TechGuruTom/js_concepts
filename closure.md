# Closure

A closure is a fundamental and powerful concept in JavaScript. It occurs when a function "remembers" its lexical scope even when it is executed outside that scope. In other words, a closure allows a function to maintain access to variables from its outer (enclosing) function, even after the outer function has finished executing.

> **Closures are an ability of a function to remember the variables and functions that are declared in its outer scope.**

To create a closure, you need to have a nested function (inner function) defined within another function (outer function). The inner function must reference variables from the outer function's scope to form the closure.

Here's an example to illustrate closures:

```javascript
function outerFunction() {
	let outerVar = "I am from the outer function";

	function innerFunction() {
		console.log(outerVar);
	}

	return innerFunction; // Return the inner function, creating a closure
}

const closureFunction = outerFunction();

closureFunction(); // Output: "I am from the outer function"
```

In this example, the `innerFunction` is defined inside `outerFunction`, and it references the `outerVar`. When `outerFunction` is called, it returns the `innerFunction`, forming a closure. The `closureFunction` now "remembers" the `outerVar` value even after `outerFunction` has finished executing.

Closures are powerful because they allow functions to maintain access to their own private data. They are commonly used to create functions with private variables, encapsulation, and data hiding in JavaScript.

Here's an example of using closures to create a counter with private state:

```javascript
function createCounter() {
	let count = 0;

	function increment() {
		count++;
		console.log(count);
	}

	function decrement() {
		count--;
		console.log(count);
	}

	return {
		increment,
		decrement,
	};
}

const counter = createCounter();
counter.increment(); // Output: 1
counter.increment(); // Output: 2
counter.decrement(); // Output: 1
```

In this example, the `createCounter` function returns an object with two methods, `increment` and `decrement`. These methods form closures that remember the `count` variable's value. This way, the `count` variable is private and cannot be accessed from outside the returned object. Each time `increment` or `decrement` is called, it operates on the private `count` variable without exposing it directly to the outside world.

Closures are a crucial aspect of JavaScript and are used in many advanced programming patterns. They provide a way to manage state, create private variables, and encapsulate logic within functions, making code more modular and maintainable.
