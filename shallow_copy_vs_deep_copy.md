# Shallow Copy Vs Deep Copy

Shallow copy and deep copy are two different approaches to copying objects or arrays in JavaScript. The key difference lies in how they handle nested objects or arrays within the original object or array.

1. Shallow Copy:
   A shallow copy creates a new object or array and copies the top-level structure of the original object or array. However, the nested objects or arrays within the original object or array are still referenced and not duplicated. Any changes made to the nested objects or arrays in the shallow copy will affect the original object, and vice versa.

Here's an example of shallow copying an object:

```javascript
// Original object
const originalObject = {
  name: 'John',
  age: 30,
  address: {
    city: 'New York',
    country: 'USA'
  }
};

// Shallow copy using Object.assign()
const shallowCopyObject = Object.assign({}, originalObject);

// Modifying the shallow copy
shallowCopyObject.age = 31;
shallowCopyObject.address.city = 'San Francisco';

console.log(originalObject);
console.log(shallowCopyObject);
```

Output:

```
Original Object:
{
  name: 'John',
  age: 31,
  address: {
    city: 'San Francisco',
    country: 'USA'
  }
}

Shallow Copy Object:
{
  name: 'John',
  age: 31,
  address: {
    city: 'San Francisco',
    country: 'USA'
  }
}
```

As you can see, changing the `age` property in the shallow copy affected the original object as well. Moreover, modifying the `address.city` property in the shallow copy also modified the original object.

2. Deep Copy:
   A deep copy creates a completely independent copy of the original object or array, including all nested objects and arrays. Changes made to the deep copy will not affect the original object, and vice versa.

Here's an example of deep copying an object using `JSON.parse()` and `JSON.stringify()`:

```javascript
// Original object
const originalObject = {
  name: 'John',
  age: 30,
  address: {
    city: 'New York',
    country: 'USA'
  }
};

// Deep copy using JSON.parse() and JSON.stringify()
const deepCopyObject = JSON.parse(JSON.stringify(originalObject));

// Modifying the deep copy
deepCopyObject.age = 31;
deepCopyObject.address.city = 'San Francisco';

console.log(originalObject);
console.log(deepCopyObject);
```

Output:

```
Original Object:
{
  name: 'John',
  age: 30,
  address: {
    city: 'New York',
    country: 'USA'
  }
}

Deep Copy Object:
{
  name: 'John',
  age: 31,
  address: {
    city: 'San Francisco',
    country: 'USA'
  }
}
```

As you can see, changing the `age` property in the deep copy did not affect the original object. Additionally, modifying the `address.city` property in the deep copy also did not modify the original object.

Keep in mind that using `JSON.parse()` and `JSON.stringify()` for deep copying has some limitations. It may not work correctly with certain data types like functions or symbols. In such cases, you can use libraries like Lodash's `cloneDeep()` function to achieve a proper deep copy.
