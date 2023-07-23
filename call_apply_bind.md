# call, apply, cind


In JavaScript, `call`, `apply`, and `bind` are methods that are available on every function object. They are used to control the value of `this` and to invoke functions with a specific context. Each method has a different way of setting `this` and passing arguments to the function.

1. `call` method:
   The `call` method is used to call a function with a specific object as the first argument, which sets the value of `this` inside the function to that object. You can also pass additional arguments to the function using `call`.

> **call() method allows an object to use the method (function) of another object.**

Syntax:

```javascript
functionName.call(thisArg, arg1, arg2, ...);
```

Example:

```javascript
const person = {
  name: 'John',
  greet: function(message) {
    console.log(`${message}, my name is ${this.name}.`);
  }
};

const alice = {
  name: 'Alice'
};

person.greet.call(alice, 'Hello'); // Output: "Hello, my name is Alice."
```

In this example, we have two objects `person` and `alice`. The `greet` method of the `person` object uses `this.name` to access its own `name` property. By using `call`, we invoke the `greet` method with `alice` as the `thisArg`, effectively setting `this` inside the function to `alice`.

2. `apply` method:
   The `apply` method is similar to `call`,but call() method takes arguments separately whereas, apply() method takes arguments as an array.

Syntax:

```javascript
functionName.apply(thisArg, [arg1, arg2, ...]);
```

Example:

```javascript
const person = {
  name: 'John',
  greet: function(message) {
    console.log(`${message}, my name is ${this.name}.`);
  }
};

const alice = {
  name: 'Alice'
};

person.greet.apply(alice, ['Hello']); // Output: "Hello, my name is Alice."
```

In this example, we achieve the same result as the `call` example, but we pass the arguments in an array using `apply`.

3. `bind` method:
   The `bind` method is used to create a new function that is bound to a specific object (`thisArg`). The original function is not invoked immediately, but a new function is returned, which can be called later.

Syntax:

```javascript
const newFunction = functionName.bind(thisArg, arg1, arg2, ...);
```

Example:

```javascript
const person = {
  name: 'John',
  greet: function(message) {
    console.log(`${message}, my name is ${this.name}.`);
  }
};

const alice = {
  name: 'Alice'
};

const greetAlice = person.greet.bind(alice);
greetAlice('Hello'); // Output: "Hello, my name is Alice."
```

In this example, we create a new function `greetAlice` by using `bind` on the `person.greet` method with `alice` as the `thisArg`. Now, `greetAlice` is a new function that is permanently bound to `alice` as `this`, and we can call it later with the `message` argument.

In summary, `call` and `apply` are used to invoke functions with a specific context (`this`), while `bind` is used to create a new function with a fixed context (`this`) that can be invoked later. These methods are handy in various programming scenarios, especially when working with object-oriented programming and event handling.
