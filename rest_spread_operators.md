# Rest and Spread operator

In JavaScript, the rest and spread operators are two useful features introduced in ECMAScript 6 (ES6) that facilitate working with arrays and function arguments more conveniently. Let's explore each of them:

**1. Rest Operator (...):**
The rest operator, represented by three dots (`...`), is used in function parameter lists to capture multiple function arguments into a single array. It allows you to handle a variable number of arguments more easily.

Example using the rest operator in a function:

```javascript
function sum(...numbers) {
	let total = 0;
	for (const num of numbers) {
		total += num;
	}
	return total;
}

console.log(sum(1, 2, 3, 4)); // Output: 10
console.log(sum(10, 20, 30)); // Output: 60
```

In this example, the `sum` function takes multiple arguments and collects them into the `numbers` array using the rest operator. The function can now handle any number of arguments and calculate their sum.

**2. Spread Operator (...):**
The spread operator, also represented by three dots (`...`), is used to split an array or object into individual elements. It can be used in various scenarios to create a copy of an array, merge arrays, pass array elements as function arguments, and more.

Example using the spread operator to merge arrays:

```javascript
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const mergedArray = [...arr1, ...arr2];

console.log(mergedArray); // Output: [1, 2, 3, 4, 5, 6]
```

Example using the spread operator to copy an array:

```javascript
const originalArray = [1, 2, 3];
const copiedArray = [...originalArray];

console.log(copiedArray); // Output: [1, 2, 3]
```

Example using the spread operator with function arguments:

```javascript
function displayNames(name1, name2, name3) {
	console.log(name1, name2, name3);
}

const names = ["Alice", "Bob", "Charlie"];
displayNames(...names); // Output: Alice Bob Charlie
```

In this last example, the spread operator is used to pass the elements of the `names` array as individual arguments to the `displayNames` function. Without the spread operator, passing the array directly would result in `name1` being assigned the entire array, which is not the desired behavior.

The rest and spread operators are powerful tools that enhance the flexibility and expressiveness of JavaScript code. They are widely used in modern JavaScript development, especially in scenarios that involve manipulating arrays and working with functions that take a variable number of arguments.
