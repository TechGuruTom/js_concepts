# IIFE

IIFE stands for "Immediately Invoked Function Expression." It is a JavaScript function that is defined and executed immediately after its creation. The primary purpose of using IIFE is to create a private scope for variables and functions, preventing them from polluting the global scope.

An IIFE is typically used to encapsulate code and avoid conflicts with other scripts or libraries that might be running on the same page.

Here's the basic syntax of an IIFE:

```javascript
(function() {
  // IIFE code goes here
})();
```

The function is defined within parentheses to create an expression and then immediately invoked by appending `()` at the end. This way, the function is executed right after it's defined.

Example of using IIFE:

```javascript
(function() {
  const message = "Hello from IIFE!";
  console.log(message); // Output: "Hello from IIFE!"
})();

// Trying to access 'message' outside the IIFE will result in an error
// console.log(message); // Error: message is not defined
```

In this example, we define an IIFE that declares a variable `message` and logs it to the console. The variable `message` is confined within the IIFE's scope and not accessible outside of it. If we try to access `message` outside the IIFE, we'll get a ReferenceError because it's not defined in the global scope.

IIFEs are commonly used to avoid variable name collisions and maintain a clean and isolated scope. They are especially prevalent in older JavaScript code before the introduction of block-scoped variables (`let` and `const`) in ECMAScript 6 (ES6).

With the introduction of ES6 and the widespread use of modern JavaScript module systems, IIFEs are not as commonly used today. Instead, developers often prefer to use modules to achieve similar encapsulation and privacy. However, understanding IIFEs is still valuable, especially when working with legacy codebases or in situations where modules are not available or not suitable.
