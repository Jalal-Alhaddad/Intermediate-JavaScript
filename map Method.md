# map Method

In JavaScript, the map() method is used to create a new array by applying a provided function to every element in the original array. It does not modify the original array but instead returns a new array containing the results of the function applied to each element.

```javascript
const newArray = array.map(callbackFunction);
```

`callbackFunction`: A function that is called for each element in the array. It takes three arguments:

- `currentValue`: The current element being processed in the array.
- `index` (optional): The index of the current element being processed.
- `array` (optional): The array map was called upon.

Code with External Function Declaration

```javascript
const numbers = [10, 20, 30, 40, 50];

// External function declaration
function annotateElement(currentValue, index, array) {
  return `Element at index ${index} is ${currentValue} (Array length: ${array.length})`;
}

// Use the function in map
const annotatedArray = numbers.map(annotateElement);

console.log(annotatedArray);

```

Code with Arrow Function

```javascript
const numbers = [10, 20, 30, 40, 50];

const annotatedArray = numbers.map((currentValue, index, array) => {
  return `Element at index ${index} is ${currentValue} (Array length: ${array.length})`;
});

console.log(annotatedArray);

```

how you can use the map() method in a browser environment to populate an array of person objects into an HTML list

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Person List</title>
</head>
<body>
    <ul id="personList"></ul>

    <script>
        // Array of person objects
        const people = [
            { name: "Alice", age: 25 },
            { name: "Bob", age: 30 },
            { name: "Charlie", age: 35 }
        ];

        // Function to generate HTML list item
        function generateListItem(person) {
            return `<li>${person.name} - Age: ${person.age}</li>`;
        }

        // Use map to create an array of HTML strings
        const personListItems = people.map(generateListItem);

        // Join the array into a single string and insert into the HTML
        document.getElementById("personList").innerHTML = personListItems.join('');
    </script>
</body>
</html>

```

## Summary

- The `map()` method is powerful for transforming arrays.
- It returns a new array without modifying the original.
- The callback function can access the element, its index, and the entire array.
- `map()` is often used when you need to apply a transformation to each element in an array.
