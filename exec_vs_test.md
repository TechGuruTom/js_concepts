# exec() and test()


In javascript,

* **test ()** and **exec ()** are RegExp expression methods used in javascript.
* We'll use **exec ()** to search a string for a specific pattern, and if it finds it, it'll return the pattern directly; else, it'll return an 'empty' result.
* We will use a** test ()** to find a string for a specific pattern. It will return the Boolean value 'true' on finding the given text otherwise, it will return 'false'.

1. `exec()` method:
   The `exec()` method is a RegExp method that searches for a match in a given string. If a match is found, it returns an array containing the matched text along with additional information about the match. If no match is found, it returns `null`.

Syntax:

```javascript
regexp.exec(string)
```

Example:

```javascript
const regex = /apple/g;
const str = 'I have an apple and another apple';

let match;
while ((match = regex.exec(str)) !== null) {
  console.log(`Found '${match[0]}' at index ${match.index}`);
}
```

Output:

```
Found 'apple' at index 9
Found 'apple' at index 27
```

In this example, we create a regular expression `regex` to search for the word "apple" in a string `str`. We use a `while` loop with `exec()` to find all occurrences of "apple" in the string. The `exec()` method returns an array with the matched text (`match[0]`) and its index (`match.index`).

2. `test()` method:
   The `test()` method is another RegExp method that searches for a match in a given string. It returns a boolean value (`true` or `false`) indicating whether a match is found or not.

Syntax:

```javascript
regexp.test(string)
```

Example:

```javascript
const regex = /apple/g;
const str = 'I have an apple and another apple';

const hasMatch = regex.test(str);
console.log(hasMatch); // Output: true
```

In this example, we use the `test()` method to check if the word "apple" exists in the string `str`. Since "apple" is present twice in the string, the `test()` method returns `true`.

Differences between `exec()` and `test()`:

- `exec()` returns an array with details about the match, while `test()` returns a boolean value indicating whether a match is found or not.
- `exec()` is used when you need more information about the match, such as the index and other capture groups. It is more suitable for scenarios where you want to find multiple occurrences of the pattern.
- `test()` is simpler and returns `true` or `false` based on whether a match is found. It is often used for simple checks to see if a pattern exists in a string.

Both `exec()` and `test()` are useful when working with regular expressions to perform string matching and manipulation in JavaScript.
