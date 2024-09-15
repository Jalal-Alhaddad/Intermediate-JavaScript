# Assignment 1 - Class and DOM Manipulation

>**Create Classes**:
>
>- Define an Address class with properties street, city, and zipCode.
>- Define a Person class with properties name, age, and an address object (instance of the Address class).
>
>**Create an Array of Person Objects**:
>
>- Create an array of 5-6 Person objects, each with their own Address object.
>- Destructure the Person objects and format their details into a string.
>
>**Manipulate Strings with split() and join()**:
>
>- Transform each string in the array of person details into an array of words.
>- Rejoin the array of words using a different separator (e.g., ' - ').
>
>**Transform Array into HTML-like String and Add to DOM**:
>
>- Convert the array of Person objects into a string of HTML-like tags.
>- Append the resulting HTML string to a div element with the ID personContainer in the DOM.

## Stage 1: Representing Data with Classes

- Create two classes:
  - Address class with properties like street, city, zipCode.
  - Person class with properties like name, age, and an address object (which will be an instance of the Address class).

```javascript
class Address {
  constructor(street, city, zipCode) {
    this.street = street;
    this.city = city;
    this.zipCode = zipCode;
  }
}

class Person {
  constructor(name, age, address) {
    this.name = name;
    this.age = age;
    this.address = address;
  }
}

// Example usage
const address1 = new Address('123 Main St', 'New York', '10001');
const person1 = new Person('Alice', 30, address1);
```

## Stage 2: Creating an Array of Person Objects and Destructuring

- Create an array of 5-6 Person objects and destructure them when manipulating the data.

```javascript
const persons = [
  new Person('Alice', 30, new Address('123 Main St', 'New York', '10001')),
  new Person('Bob', 25, new Address('456 Park Ave', 'Chicago', '60601')),
  new Person('Charlie', 35, new Address('789 Elm St', 'Los Angeles', '90001')),
];

const personDetails = persons.map(({ name, age, address: { street, city, zipCode } }) => {
  return `${name}, Age: ${age}, Address: ${street}, ${city}, ${zipCode}`;
});

console.log(personDetails);
```

## Stage 3: Manipulating Strings with split() and join()

- Introduce the split() and join() methods for string manipulation. Ask students to split each personDetails string into an array of words and then rejoin them using a different separator.

```javascript
const personDetailsWithDash = personDetails.map((detail) => {
  const wordsArray = detail.split(' '); // Split the string by spaces into an array of words
  return wordsArray.join(' - '); // Join the array of words with ' - ' as a separator
});

console.log(personDetailsWithDash);
```

## Stage 4: Transforming Array into HTML-like String and Adding to DOM

- Transform the array of Person objects into a string of HTML-like tags and append them to a div in the DOM.

```javascript
const personTags = persons
  .map(({ name, age, address: { street, city, zipCode } }) => {
    return `
    <div class="person">
      <h2>${name}</h2>
      <p>Age: ${age}</p>
      <p>Address: ${street}, ${city}, ${zipCode}</p>
    </div>
  `;
  })
  .join(''); // Join all the HTML strings into one

// Add the HTML string to the DOM
const personContainer = document.getElementById('personContainer');
personContainer.innerHTML = personTags;
```
