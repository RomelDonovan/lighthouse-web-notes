### Tips

Figure out how you're going to look at each item in numbers one at a time, then think about how you're going to find the minimum value as you iterate through the list.

you can use for and while loops to repeat certain lines of code. This is a really powerful tool that you can use to drastically reduce the amount of code you have to write.

```javascript
// Function definition
const min = function(numbers) {
  // Write code here that returns the smallest value in numbers
  let num = numbers[0];
  for (let number of numbers) {
    // Use console.log() to help see what is logged.
    if (num > number) {
      num = number;
    }
  }
  return num;
};
```