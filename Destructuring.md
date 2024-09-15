# Destructuring

## Object Destructuring

Object destructuring allows you to extract properties from an object and assign them to variables in a concise way.

```javascript
const { property1, property2 } = object;
```

```javascript
const person = {
  name: 'Alice',
  age: 30,
  address: {
    street: '123 Main St',
    city: 'New York',
    zipCode: '10001'
  }
};

// Destructuring the object
const { name, age, address: { street, city, zipCode } } = person;

console.log(name);    // Output: Alice
console.log(age);     // Output: 30
console.log(street);  // Output: 123 Main St
console.log(city);    // Output: New York
console.log(zipCode); // Output: 10001
```

### Object Destructuring Usage

- Extract Multiple Properties: Extract several properties from an object in one statement.
- Nested Properties: Access nested properties directly within the destructuring pattern.
- Default Values: Assign default values if the properties are not present.

## Array Destructuring

Array destructuring allows you to extract elements from an array and assign them to variables.

```javascript
const [element1, element2] = array;
```

```javascript
const numbers = [1, 2, 3, 4, 5];

// Destructuring the array
const [first, second, third] = numbers;

console.log(first);  // Output: 1
console.log(second); // Output: 2
console.log(third); // Output: 3

```

### Array Destructuring Usage

- Extract Multiple Elements: Extract several elements from an array in one statement.
- Skipping Elements: Skip certain elements by leaving gaps in the destructuring pattern.

> Rest Elements: Use the rest parameter (...) to collect the remaining elements into a new array.

## Quick Summary

- Object Destructuring: Use {} to extract properties from an object.
- Array Destructuring: Use [] to extract elements from an array.
- Nested Destructuring: Access nested properties or elements directly.
- Default Values: Provide default values for missing properties or elements.
- Rest Elements: Collect remaining properties or elements into a new array.
