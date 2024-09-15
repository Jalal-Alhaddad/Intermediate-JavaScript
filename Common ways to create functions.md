# Common ways to create functions

Function Declaration

```javascript
function greet(name) {
    return `Hello, ${name}!`;
}

```

Function Expression

```javascript
const greet = function(name) {
    return `Hello, ${name}!`;
};

```

Arrow Function

```javascript
const greet = (name) => `Hello, ${name}!`;

// const functionName = (parameters) => expression;

// const add = (a, b) => a + b;

const add = (a, b) => {
    const sum = a + b;
    return sum;
};

```

Immediately Invoked Function Expression (IIFE)

```javascript
(function() {
    console.log("This function runs immediately!");
})();
```

Function Constructor

```javascript
const greet = new Function('name', 'return `Hello, ${name}!`;');

```
