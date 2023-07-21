Clean Code Javascript

[toc]

## Line Length

Lines should be _no longer_ than **80 characters** . Lines which go over 80 char should be wrapped after an operator (e.g. comma). The **continuation** line should be _indented_ **two levels** (8 chars).

```javascript
// Good
registerNewUser(firstName, lastName, emailAddress, password, preferredLanguage);

// Bad: Continuation line only indented four spaces
registerNewUser(firstName, lastName, emailAddress, password, preferredLanguage);

registerNewUser(firstName, lastName, emailAddress, password, preferredLanguage);
```

## Primitive Literals

### Strings

Always use double quotes and span a single line.

```javascript
// Good
var message = "Welcome to JayessVille!";

// Bad: Single Quotes
var message = "single quotes confuse. avoid";
```

## Avoid Global Variables

Minimize the use of global variables.

This includes all data types, objects, and functions.

Global variables and functions can be overwritten by other scripts.

Use local variables instead, and learn how to use [closures]().

Avoid global variables, avoid `new`, avoid `==`, avoid `eval()`

## Always Declare Local Variables

All variables used in a function should be declared as **local** variables.

Local variables **must** be declared with the `var`, the `let`, or the `const` keyword, otherwise they will become global variables.

## Declarations on Top

It is a good coding practice to put all declarations at the top of each script or function.

This will:

- Give cleaner code
- Provide a single place to look for local variables
- Make it easier to avoid unwanted (implied) global variables
- Reduce the possibility of unwanted re-declarations

  ```javascript
  // Declare at the beginning
  let name, email, price, discount, fullPrice;

  // Use later
  mane = "Tom";
  age = 26;

  price = 19.9;
  discount = 0.1;

  fullPrice = price - discount;
  ```

## Initialize Variables

It is a good coding practice to initialize variables when you declare them.

This will:

- Give cleaner code
- Provide a single place to initialize variables
- Avoid undefined values

  ```javascript
  // Declare and initiate at the beginning
  let firstName = "";
  let lastName = "";
  let price = 0;
  let discount = 0;
  let fullPrice = 0,
  const myArray = [];
  const myObject = {};
  ```

## Declare Objects with **const**

Declaring objects with const will prevent any accidental change of type:

```javascript
let car = { type: "Fiat", model: "500", color: "white" };
car = "Fiat"; // Changes object to string
```

```javascript
const car = { type: "Fiat", model: "500", color: "white" };
car = "Fiat"; // Not possible
```

## Declare Arrays with **const**

Declaring arrays with const will prevent any accidential change of type:

```javascript
let cars = ["Saab", "Volvo", "BMW"];
cars = 3; // Changes array to number
```

```javascript
const cars = ["Saab", "Volvo", "BMW"];
cars = 3; // Not possible
```

## Don't Use new Object()

- Use `""` instead of `new String()`
- Use `0` instead of `new Number()`
- Use `false` instead of `new Boolean()`
- Use `{}` instead of `new Object()`
- Use `[]` instead of `new Array()`
- Use `/()/` instead of `new RegExp()`
- Use `function (){}` instead of `new Function()`

```javascript
let x1 = ""; // new primitive string
let x2 = 0; // new primitive number
let x3 = false; // new primitive boolean
const x4 = {}; // new object
const x5 = []; // new array object
const x6 = /()/; // new regexp object
const x7 = function () {}; // new function object
```

## Beware of Automatic Type Conversions

JavaScript is loosely typed.

A variable can contain all data types.

A variable can change its data type:

```javascript
let x = "Hello"; // typeof x is a string
x = 5; // changes typeof x to a number
```

Beware that numbers can accidentally be converted to strings or `NaN` (Not a Number).

When doing mathematical operations, JavaScript can convert numbers to strings:

```javascript
let x = 5 + 7; // x.valueOf() is 12,  typeof x is a number
let x = 5 + "7"; // x.valueOf() is 57,  typeof x is a string
let x = "5" + 7; // x.valueOf() is 57,  typeof x is a string
let x = 5 - 7; // x.valueOf() is -2,  typeof x is a number
let x = 5 - "7"; // x.valueOf() is -2,  typeof x is a number
let x = "5" - 7; // x.valueOf() is -2,  typeof x is a number
let x = 5 - "x"; // x.valueOf() is NaN, typeof x is a number
```

Subtracting a string from a string, does not generate an error but returns `NaN` (Not a Number):

```javascript
"Hello" - "Dolly"; // returns NaN
```

## Use === Comparison

The `==` comparison operator always converts (to matching types) before comparison.

The `===` operator forces comparison of values and type:

```javascript
0 == ""; // true
1 == "1"; // true
1 == true; // true

0 === ""; // false
1 === "1"; // false
1 === true; // false
```

## Use Parameter Defaults

If a function is called with a missing argument, the value of the missing argument is set to `undefined`.

Undefined values can break your code. It is a good habit to assign default values to arguments.

```javascript
function (a=1, b=1) { /*function code*/ }
```

## End Your Switches with Defaults

Always end your `switch` statements with a `default`. Even if you think there is no need for it.

```javascript
switch (new Date().getDay()) {
	case 0:
		day = "Sunday";
		break;
	case 1:
		day = "Monday";
		break;
	case 2:
		day = "Tuesday";
		break;
	case 3:
		day = "Wednesday";
		break;
	case 4:
		day = "Thursday";
		break;
	case 5:
		day = "Friday";
		break;
	case 6:
		day = "Saturday";
		break;
	default:
		day = "Unknown";
}
```

## Avoid Number, String, and Boolean as Objects

Always treat numbers, strings, or booleans as primitive values. Not as objects.

Declaring these types as objects, slows down execution speed, and produces nasty side effects:

```javascript
let x = "Tom";
let y = new String("Tom");
x === y; // is false because x is a string and y is an object.
```

```javascript
let x = new String("Tom");
let y = new String("Tom");
x == y; // is false because you cannot compare objects.
```

## Avoid Using eval()

The `eval()` function is used to run text as code. In almost all cases, it should not be necessary to use it.

Because it allows arbitrary code to be run, it also represents a security problem.

## Structure and Naming

Organize your files around product features / pages / components, not roles. Also, place your test files next to their implementation.

Bad

```
.
├── controllers
|   ├── product.js
|   └── user.js
├── models
|   ├── product.js
|   └── user.js
```

good

```javascript
├── product

|   ├── index.js
|   ├── product.js
|   └── product.test.js
├── user
|   ├── index.js
|   ├── user.js
|   └── user.test.js
```

_Why:_

> Instead of a long list of files, you will create small modules that encapsulate one responsibility including its test and so on. It gets much easier to navigate through and things can be found at a glance.

## Code style Guidelines

- Use [ESLint - Pluggable JavaScript linter](http://eslint.org/) to enforce code style.
- Use `.eslintignore` to exclude files or folders from code style checks.


## Use searchable names

We will read more code than we will ever write. It's important that the code we do write is readable and searchable. By *not* naming variables that end up being meaningful for understanding our program, we hurt our readers. Make your names searchable. Tools like [buddy.js](https://github.com/danielstjules/buddy.js) and [ESLint](https://github.com/eslint/eslint/blob/660e0918933e6e7fede26bc675a0763a6b357c94/docs/rules/no-magic-numbers.md) can help identify unnamed constants.

Bad

```
// What the heck is 86400000 for?
setTimeout(blastOff, 86400000);
```

Good

```
// Declare them as capitalized named constants.
const MILLISECONDS_PER_DAY = 60 * 60 * 24 * 1000; //86400000;

setTimeout(blastOff, MILLISECONDS_PER_DAY);
```
