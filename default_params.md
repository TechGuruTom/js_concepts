# Default Parameters in function

Default parameters in JavaScript functions allow you to specify default values for function parameters if no argument or an undefined argument is passed during the function call. This feature was introduced in ECMAScript 6 (ES6) to provide a more concise and flexible way of handling missing or undefined arguments.

Here's the syntax to define default parameters in a function:

```javascript
function functionName(param1 = defaultValue1, param2 = defaultValue2, ...) {
  // Function body
}
```

When you define default parameters for a function, the default values will be used if the corresponding arguments are not provided or are explicitly set to `undefined`. If an argument is passed during the function call, the provided value will override the default value.

Example of a function with default parameters:

```javascript
function greet(name = "Guest", message = "Hello") {
	console.log(`${message}, ${name}!`);
}

greet(); // Output: Hello, Guest!
greet("John"); // Output: Hello, John!
greet("Alice", "Hi"); // Output: Hi, Alice!
greet(undefined, "Hey"); // Output: Hey, Guest!
```

In this example, the `greet` function has two parameters, `name` and `message`, with default values `'Guest'` and `'Hello'`, respectively. If the function is called without any arguments, it uses the default values. If arguments are provided during the function call, they will replace the default values for the respective parameters.

Default parameters are handy when you want to ensure that your function can work with missing or incomplete data without throwing errors. They also make function calls more concise by reducing the need for explicit checks for undefined arguments inside the function body.
