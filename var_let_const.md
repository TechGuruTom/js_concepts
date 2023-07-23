# var let const


In JavaScript, `var`, `let`, and `const` are used to declare variables, but they have different scoping rules and behaviors:

1. `var`:

- `var` was the original way to declare variables in JavaScript.
- Variables declared with `var` have function scope or global scope, but not block scope. This means that a variable declared with `var` is accessible throughout the entire function where it was declared, or if declared outside any function, it becomes a global variable.
- Variables declared with `var` are hoisted, meaning the variable declaration is moved to the top of its scope during the compilation phase. However, the value assignment remains in its original position.

```javascript
function exampleVar() {
  if (true) {
    var x = 10;
  }
  console.log(x); // Output: 10 (because x is accessible here due to function scope)
}

exampleVar();
console.log(x); // Output: 10 (because x is a global variable)
```

2. `let`:

- `let` was introduced in ECMAScript 6 (ES6) and provides block-scoped variables.
- Variables declared with `let` are block-scoped, meaning they are only accessible within the block where they were declared (a block is defined by curly braces {}).
- Variables declared with `let` are not hoisted. If you try to access a `let` variable before its declaration, you'll get a ReferenceError.

```javascript
function exampleLet() {
  if (true) {
    let y = 20;
    console.log(y); // Output: 20 (y is accessible within this block)
  }
  // console.log(y); // Error: y is not defined (y is not accessible here)
}

exampleLet();
```

3. `const`:

- `const` was also introduced in ES6 and is used to declare constants, which are block-scoped variables whose value cannot be reassigned once initialized.
- Like `let`, variables declared with `const` are block-scoped and not hoisted.
- When using `const`, you must assign a value to the variable when declaring it. Once assigned, you cannot reassign a new value to a `const` variable.

```javascript
function exampleConst() {
  const z = 30;
  // z = 40; // Error: Assignment to constant variable.
  console.log(z); // Output: 30
}

exampleConst();
```

It's important to note that `const` creates an immutable binding, meaning you cannot change the reference of the variable. However, the value itself may be mutable, especially for objects and arrays. This means you can modify the properties of an object or the elements of an array declared with `const`, but you cannot reassign the variable to a completely new object or array.

```javascript
const person = {
  name: 'John',
  age: 30
};

person.age = 31; // Valid, modifying the 'age' property
// person = { name: 'Alice', age: 25 }; // Error, cannot reassign 'person'
console.log(person); // Output: { name: 'John', age: 31 }
```

In modern JavaScript, it is generally recommended to use `let` for variables that may change their value and `const` for variables that should remain constant. Using block-scoped variables (`let` and `const`) leads to more predictable and maintainable code compared to the older `var` with function scope.
