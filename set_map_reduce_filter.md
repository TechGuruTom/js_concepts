# Set, Map, Reduce, Filter

In JavaScript, `Set`, `Map`, `reduce`, and `filter` are powerful built-in features that make it easier to work with data structures and arrays. Let's explore each of them:

**1. Set:**
The `Set` is a collection that allows you to store unique values. It automatically removes duplicate entries, ensuring that each value is unique within the set.

Example of using a `Set`:

```javascript
const uniqueNumbers = new Set();
uniqueNumbers.add(1);
uniqueNumbers.add(2);
uniqueNumbers.add(3);
uniqueNumbers.add(1); // Ignored, as it's a duplicate

console.log(uniqueNumbers); // Output: Set { 1, 2, 3 }
```

The `Set` provides methods like `add`, `has`, `delete`, and `clear` to manipulate the collection.

**2. Map:**
The `Map` is a data structure that allows you to store key-value pairs. Unlike objects, keys in a `Map` can be of any data type, and the order of insertion is preserved.

Example of using a `Map`:

```javascript
const userMap = new Map();
userMap.set("name", "John");
userMap.set("age", 30);
userMap.set("city", "New York");

console.log(userMap.get("name")); // Output: John
console.log(userMap.get("age")); // Output: 30
console.log(userMap.get("city")); // Output: New York
```

The `Map` provides methods like `set`, `get`, `has`, `delete`, and `clear` to manage the key-value pairs.

**3. reduce:**
The `reduce` method is available on arrays and is used to transform an array into a single value. It applies a reducer function to each element of the array, accumulating the result as it processes the elements.

Syntax of `reduce`:

```javascript
array.reduce((accumulator, currentValue) => {
	// reducer function code
	return updatedAccumulator;
}, initialValue);
```

Example using `reduce` to calculate the sum of an array:

```javascript
const numbers = [1, 2, 3, 4, 5];
const sum = numbers.reduce((acc, num) => acc + num, 0);

console.log(sum); // Output: 15
```

**4. filter:**
The `filter` method is available on arrays and is used to create a new array with elements that pass a certain condition defined in a callback function.

Syntax of `filter`:

```javascript
array.filter((element) => {
	// condition to filter elements
	return trueOrFalse;
});
```

Example using `filter` to get even numbers from an array:

```javascript
const numbers = [1, 2, 3, 4, 5, 6];
const evenNumbers = numbers.filter((num) => num % 2 === 0);

console.log(evenNumbers); // Output: [2, 4, 6]
```

`filter` returns a new array containing only the elements that satisfy the condition specified in the callback function.

In summary, `Set` and `Map` are powerful data structures for storing unique values and key-value pairs, respectively. The `reduce` method helps aggregate values in an array, and the `filter` method allows you to create a new array with elements that meet a specific condition. All these features are useful for performing various operations on collections and arrays in JavaScript.
