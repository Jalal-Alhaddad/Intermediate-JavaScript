# Assignments

## Q 1: Creating Objects the Old Way (Using Constructor Functions and Prototypes)

Instructions:

- Create a constructor function called `Person` that accepts two parameters: `name` and `age`.
- Add a method called `introduce` to `Person.prototype` that logs a message introducing the person (using `this` to access name and age).
- Create two objects using the `Person` constructor (person1, person2).
- Use the `setTimeout` function to delay calling the `introduce` method on one of the objects by 2 seconds. However, due to the behavior of `this`, the `introduce` method will lose context. Fix `this` issue using `bind()` to ensure this still refers to the correct object.
- Show the output with and without `bind()`.

```javascript
function Person(name, age) {
  this.name = name;
  this.age = age;
}

Person.prototype.introduce = function() {
  console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
};

const person1 = new Person("Alice", 30);
const person2 = new Person("Bob", 25);

// Without bind (will lose context)
setTimeout(person1.introduce, 2000); // Output: Hello, my name is undefined and I am undefined years old.

// With bind (fixed)
setTimeout(person1.introduce.bind(person1), 2000); // Output: Hello, my name is Alice and I am 30 years old.
```

## Q 2: Creating Objects Using ES6 Classes

Instructions:

- Create a class called `Car` that takes `brand` and `model` as parameters in the constructor.
- Add a method called `details` inside the class that logs a message using `this.brand` and `this.model`.
- Create two instances of the `Car` class.
- Use `setTimeout` to delay the calling of the `details` method, and fix any `this` context issue using `bind()`.
- Add an event handler to a button element in your HTML. When the button is clicked, the `details` method of one of the `Car` objects should be called. Ensure `this` points to the correct object inside the event handler using `bind()`.

```javascript
class Car {
  constructor(brand, model) {
    this.brand = brand;
    this.model = model;
  }

  details() {
    console.log(`This car is a ${this.brand} ${this.model}.`);
  }
}

const car1 = new Car("Toyota", "Camry");
const car2 = new Car("Honda", "Civic");

// Without bind (losing context)
setTimeout(car1.details, 2000); // Output: This car is a undefined undefined.

// With bind (fixed)
setTimeout(car1.details.bind(car1), 2000); // Output: This car is a Toyota Camry.

// Adding an event listener with bind to ensure correct `this` context
document.getElementById("showCarDetails").addEventListener("click", car2.details.bind(car2));
```

- An explanation of why this loses context in the setTimeout and event handler scenarios.
- A description of how bind() solves the issue and maintains the correct this context.

## Q3: Understanding this and Arrow Functions

>**Objective**: Learn how arrow functions can solve this context issues without the need for `bind()`.

Instructions:

- Create a class called Animal with the following:
  - A constructor that takes two parameters: species and sound.
  - A method called makeSound that logs a message using this.species and this.sound (e.g., "A dog says woof").
- Create two instances of the Animal class.
- Use setTimeout to delay the calling of the makeSound method for one of the animals, but instead of using bind(), solve the this issue using an arrow function inside the setTimeout.
- Simulate a user action (since there are no event listeners in Node.js) by calling the makeSound method of the second Animal after another delay using setTimeout. Ensure the correct this context is preserved using an arrow function.

```javascript
class Animal {
  constructor(species, sound) {
    this.species = species;
    this.sound = sound;
  }

  makeSound() {
    console.log(`A ${this.species} says ${this.sound}`);
  }
}

const animal1 = new Animal("Dog", "woof");
const animal2 = new Animal("Cat", "meow");

// Using arrow function in setTimeout (fixes `this` issue)
setTimeout(() => animal1.makeSound(), 2000); // Output after 2 seconds: A Dog says woof

// Simulating a user "event" by directly invoking a method
setTimeout(() => {
  console.log("Simulating an event for animal2...");
  animal2.makeSound();
}, 3000); // Output after 3 seconds: A Cat says meow
```
