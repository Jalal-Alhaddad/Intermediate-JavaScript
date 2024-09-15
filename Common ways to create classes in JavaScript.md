# Common ways to create classes in JavaScript

## 1. Using the `class` Keyword

Introduced in ES6, the class keyword provides a more structured and cleaner way to define classes.

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }
}

const person1 = new Person('Alice', 30);
person1.greet(); // Outputs: Hello, my name is Alice and I am 30 years old.
```

## 2. Using `Object.create()`

This method allows you to create an object with a specified prototype, which can be used to simulate class-like behavior.

```javascript

// Define the Prototype Object
const personPrototype = {
  greet() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }
};

// Create a New Object:
const person1 = Object.create(personPrototype);

// Add Properties to the New Object
person1.name = 'Bob';
person1.age = 25;

// Use the New Object
person1.greet(); // Outputs: Hello, my name is Bob and I am 25 years old.
```

> The properties like **name** and **age** are not defined within the prototype object itself. Instead, they are added directly to the new object created from the prototype.

## 3. Using Constructor Functions

Before ES6, constructor functions were the primary way to create classes in JavaScript.

```javascript
function Person(name, age) {
  this.name = name;
  this.age = age;
}

Person.prototype.greet = function() {
  console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
};

const person1 = new Person('Charlie', 35);
person1.greet(); // Outputs: Hello, my name is Charlie and I am 35 years old.
```

Each of these methods has its own use cases and advantages. The class keyword is more modern and syntactically cleaner, while Object.create() and constructor functions offer more flexibility and compatibility with older JavaScript versions.

### The `new` keyword

The `new` keyword has been available in JavaScript since its early versions, long before the class keyword was introduced in ES6 (ECMAScript 2015).

The new keyword is used with constructor functions to create instances of objects.