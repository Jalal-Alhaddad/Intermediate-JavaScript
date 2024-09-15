# join Method

The `join()` method in JavaScript is used to create a string by concatenating all the elements of an array, separated by a specified separator string. If no separator is provided, the elements are separated by commas by default.

```javascript
array.join(separator);
```

`separator` (optional): A string that separates each pair of adjacent elements of the array. If omitted, the array elements are separated by a comma `,`

## Examples

Example 1: Using join() with the Default Separator

```javascript
const fruits = ["apple", "banana", "cherry"];

const fruitString = fruits.join();

console.log(fruitString); // Output: "apple,banana,cherry"
```

Example 2: Using join() with a Custom Separator

```javascript
const fruits = ["apple", "banana", "cherry"];

const fruitString = fruits.join(" - ");

console.log(fruitString); // Output: "apple - banana - cherry"
```

Example 3: Joining Elements Without Any Separator

```javascript
const numbers = [1, 2, 3, 4, 5];

const numberString = numbers.join("");

console.log(numberString); // Output: "12345"
```
