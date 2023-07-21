# Scope

In JavaScript, there are three main types of scopes:

1. **Global Scope:**
   The global scope is the outermost scope in a JavaScript program. Variables and functions declared in the global scope are accessible throughout the entire program, including within other scopes. Global variables and functions are attached to the global object (in browsers, it's the `window` object) and can be accessed using the object's property notation.

Example of a global variable and function:

```javascript
const globalVar = 10;

function globalFunction() {
	// Function code here
}

console.log(globalVar); // Accessible here
globalFunction(); // Accessible here
```

2. **Local Scope (Function Scope):**
   A local scope is created when you define a function. Variables declared within a function are accessible only within that function's scope and any nested inner scopes (e.g., functions declared inside the function). They are not visible or accessible outside of the function.

Example of local scope within a function:

```javascript
function localFunction() {
	const localVar = 20; // localVar is in the local scope of localFunction
	console.log(localVar); // Accessible here
}

console.log(localVar); // Not accessible here (results in an error)
```

3. **Block Scope (Introduced with let and const in ES6):**
   Block scope refers to the scope defined by curly braces `{}` in JavaScript. Variables declared using `let` and `const` within blocks (e.g., if statements, for loops) are accessible only within that block and any nested inner blocks. Before ES6, variables declared with `var` had function scope, but with the introduction of `let` and `const`, JavaScript gained block-scoped variables.

Example of block scope using `let`:

```javascript
function blockScopeExample() {
	if (true) {
		let blockVar = 30; // blockVar is in the block scope of the if statement
		console.log(blockVar); // Accessible here
	}

	console.log(blockVar); // Not accessible here (results in an error)
}
```

It's important to note that variables declared with `var` have function scope, which means they are accessible throughout the entire function in which they are declared (including any nested blocks). However, it's generally recommended to use `let` and `const` for variable declarations to avoid issues with variable hoisting and to adopt block scoping, which can lead to cleaner and safer code.

In summary, JavaScript has three types of scopes: global scope, function scope (local scope), and block scope (introduced with `let` and `const`). Understanding scopes is essential for managing variable lifetimes, avoiding variable collisions, and writing maintainable code.
