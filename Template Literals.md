# Template Literals

Template literals are a way to create strings that allow for embedded expressions, making it easier to work with dynamic content

## Backticks (`)

Template literals are enclosed by backticks (`) instead of single or double quotes. This allows for multi-line strings and embedded expressions.

## Dollar Sign and Curly Braces (${})

The `${}` syntax is used to embed expressions within the template literal. The expressions inside the curly braces are evaluated, and their results are included in the string.

```javascript
const name = 'Alice';
const age = 30;

const greeting = `Hello, my name is ${name} and I am ${age} years old.`;
console.log(greeting); // Outputs: Hello, my name is Alice and I am 30 years old.
```

## Benefits of Template Literals

- **Multi-line Strings**: You can create strings that span multiple lines without needing concatenation or escape characters.
- **Embedded Expressions**: Easily embed variables and expressions within strings.
- **Dynamic content**: Template literals provide a more readable and convenient way to work with strings, especially when dealing with dynamic content.
