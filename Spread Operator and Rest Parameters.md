# Spread Operator and Rest Parameters

## Spread Operator `...`

The spread operator allows you to spread elements of an array or properties of an object into another array or object. It is denoted by `...`

### Spread Operator Usage

- Array Manipulation: Combine arrays or clone arrays.
- Object Manipulation: Merge objects or clone objects.
- Function Arguments: Pass array elements as individual arguments.

```javascript
const newArray = [...existingArray];
```

```javascript
const newObject = { ...existingObject };
```

```javascript
const numbers = [1, 2, 3];
const moreNumbers = [4, 5, 6];

// Spread elements of `numbers` and `moreNumbers` into a new array
const allNumbers = [...numbers, ...moreNumbers];

console.log(allNumbers); // Output: [1, 2, 3, 4, 5, 6]
```

```javascript
const person = { name: 'Alice', age: 30 };
const job = { jobTitle: 'Engineer', company: 'Tech Corp' };

// Spread properties of `person` and `job` into a new object
const personWithJob = { ...person, ...job };

console.log(personWithJob); // Output: { name: 'Alice', age: 30, jobTitle: 'Engineer', company: 'Tech Corp' }
```

```javascript
const numbers = [1, 2, 3];
function add(a, b, c) {
  return a + b + c;
}

console.log(add(...numbers)); // Output: 6
```

## Rest Parameters

The rest parameter allows a function to accept an indefinite number of arguments as an array. It is denoted by `...` and used in function definitions.

### Rest Parameters Usage

- Variable Number of Arguments: Handle functions with a variable number of arguments.
- Array Operations: Collect multiple arguments into an array for processing.

```javascript
function functionName(...rest) {
  // `rest` is an array of arguments
}
```

```javascript
function sum(...numbers) {
  return numbers.reduce((acc, curr) => acc + curr, 0);
}

console.log(sum(1, 2, 3, 4)); // Output: 10
console.log(sum(5, 10));     // Output: 15
```

## Quick Summary

- Spread Operator (...):
  - Arrays: Spread elements of an array into another array or function arguments.
  - Objects: Spread properties of an object into another object.
  - Usage: Combine, clone, or manipulate arrays and objects.
- Rest Parameters (...):
  - Function Parameters: Collect multiple arguments into an array.
  - Usage: Handle functions with a variable number of arguments and destructure arrays.
