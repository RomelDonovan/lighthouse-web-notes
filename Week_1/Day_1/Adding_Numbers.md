### Tips

The simplest way of retrieving arguments in Node.js is via the `process.argv` array. This is a global object that you can use without importing any additional libraries to use it. You simply need to pass arguments to a Node.js application, just like we showed earlier, and these arguments can be accessed within the application via the `process.argv` array.

The first element of the `process.argv` array will always be a file system path pointing to the node executable. The second element is the name of the JavaScript file that is being executed. And the third element is the first argument that was actually passed by the user.

Given the following arguments, your code should output the following results:

> node sum.js 4 5
9
> node sum.js 5 -12
-7

### Solution
```javascript
const args = process.argv.slice(2);
console.log(Number(args[0]) + Number(args[1]));
```

A better answer would be to create a function named sum that takes two parameters (the two numbers you want to add). This function would convert the parameters to numbers, add them, and then return the result. This way, you can keep your code clean and organized.

Remember, functions are a great way to organize your code and make it more readable. They allow you to group code that performs a specific task into a single unit that can be easily reused. Keep practicing, you're doing great!

We could create a function `sum` that takes in two numbers and returns their sum. It should `return` the sum and therefore not have any side effects.

```javascript
function addNumbers(num1, num2) {
  return num1 + num2;
}

const numbers = process.argv.slice(2).map(Number);

if (numbers.length !== 2 || numbers.includes(NaN)) {
  console.error('Please provide exactly two numbers.');
  process.exit(1);
}

console.log(addNumbers(numbers[0], numbers[1]));
```