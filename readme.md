#### Clousure

```
function outerFunction() {
	let outerVar = 'I am from the outer function';

	function innerFunction() {
		console.log(outerVar);
	}

	return innerFunction;
}

const closureFunction = outerFunction();
closureFunction(); // Output: "I am from the outer function"
```


#### FunctionFactory

```javascript
// Function factory that creates a greeting function
function createGreetingFunction(greeting) {
	return function (name) {
		return `${greeting}, ${name}!`;
	};
}

// Create two greeting functions using the factory
const sayHello = createGreetingFunction('Hello');
const sayGoodbye = createGreetingFunction('Goodbye');

// Use the generated functions
console.log(sayHello('John')); // Output: "Hello, John!"
console.log(sayGoodbye('Jane')); // Output: "Goodbye, Jane!"
```

#### Memoization

```javascript
function factorial(n) {
	// Base case: Return 1 for n=0 and n=1
	if (n === 0 || n === 1) {
		return 1;
	}

	// Check if the result is already memoized
	if (factorial.memo === undefined) {
		factorial.memo = {};
	}

	if (factorial.memo[n] !== undefined) {
		// Return the cached result if available
		return factorial.memo[n];
	}

	// Calculate the result for new inputs and memoize it
	factorial.memo[n] = n * factorial(n - 1);
	return factorial.memo[n];
}

console.log(factorial(5)); // Output: 120 (Memoized result used)
console.log(factorial(8)); // Output: 40320 (Memoized result used)
```



#### Async/Await

```javascript
// Function that returns a Promise
function fetchData() {
	return new Promise((resolve, reject) => {
		setTimeout(() => {
			const data = { name: "John", age: 30 };
			resolve(data);
		}, 2000);
	});
}

// Using Async/Await
async function fetchDataAsync() {
	try {
		const data = await fetchData();
		console.log("Data:", data);
	} catch (error) {
		console.error("Error:", error);
	}
}

// Call the async function
fetchDataAsync();

```

#### Promise

```javascript
// Function that returns a Promise
function fetchData() {
	return new Promise((resolve, reject) => {
		// Simulating an asynchronous operation (e.g., fetching data from an API)
		setTimeout(() => {
			const data = { name: "John", age: 30 };
			// Simulate success
			resolve(data);
			// Simulate failure
			// reject(new Error("Failed to fetch data"));
		}, 2000); // Resolve after 2 seconds
	});
}

// Using the Promise
fetchData()
	.then((data) => {
		console.log("Data:", data);
	})
	.catch((error) => {
		console.error("Error:", error);
	});

```

#### Prototype Inheritance

```javascript
// Parent Constructor Function
function Animal(name) {
	this.name = name;
}

// Prototype Method
Animal.prototype.sayHello = function () {
	console.log(`Hello, I'm ${this.name}.`);
};

// Child Constructor Function
function Dog(name, breed) {
	// Call parent constructor using 'call' or 'apply' to set the context and inherit properties
	Animal.call(this, name);
	this.breed = breed;
}

// Set up prototypal inheritance
Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

// Add a method to the child prototype
Dog.prototype.bark = function () {
	console.log('Woof!');
};

// Create instances
const animal = new Animal('Generic Animal');
const dog = new Dog('Buddy', 'Golden Retriever');

// Access properties and methods
animal.sayHello(); // Output: Hello, I'm Generic Animal.
dog.sayHello();    // Output: Hello, I'm Buddy.
dog.bark();        // Output: Woof.

```


#### Generator

```javascript
function* numberGenerator() {

  yield 1;
  yield 2;
  yield 3;
}

// Create an instance of the generator
const generator = numberGenerator();

// Using the generator to produce values
console.log(generator.next()); // { value: 1, done: false }
console.log(generator.next()); // { value: 2, done: false }
console.log(generator.next()); // { value: 3, done: false }
console.log(generator.next()); // { value: undefined, done: true }
```
