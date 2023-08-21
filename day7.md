
## JavaScript Principles
 

#### Thread of execution
JavaScript is a single-threaded programming language, which means it executes code sequentially, one instruction after another, in a single sequence or "thread of execution".

##### Functions :
- **Execution context** : refers to the environment in which a piece of code is executed. It consists of variables, functions, and other code-related constructs that determine the behavior of the code as it runs

### Call Stack : 
is a crucial concept related to how functions are executed and managed in a program. It's a data structure that keeps track of function calls during the execution of a script. When a function is called, a new entry is added to the top of the call stack. When a function completes its execution, its entry is removed from the top of the stack, allowing the control to return to the calling function.

## Tasks:

### Q1:
Use Higher-Order Functions map, filter, or reduce to Solve a Complex Problem
```
const squareList = arr => {
let output= arr.filter(item=>item>0&&Number.isInteger(item)).
 map(item=>item*item)
  return output;
  // Only change code above this line
};

const squaredIntegers = squareList([-3, 4.8, 5, 3, -3.2]);
console.log(squaredIntegers);
```

### Q2:
Apply Functional Programming to Convert Strings to URL Slugs

```
function urlSlug(title) {
  return title
    .split(" ") 
    .filter(word => word !== "") 
    .map(word => word.toLowerCase()) 
    .join("-"); 
}
// Only change code above this line
urlSlug("A Mind Needs Books Like A Sword Needs A Whetstone");
```

### Q3.1:
Implement a JavaScript function called mapAsync that takes an array and a callback function. The function should map each element of the array to a new value using the callback function asynchronously.

The final result should be returned as a Promise.


```
function mapAsync(array, callback) {
  return new Promise((resolve, reject) => {
    const result = [];

    function processElement(index) {
      if (index >= array.length) {
        resolve(result);
        return;
      }

      const element = array[index];
      const newValue = callback(element);

      result.push(newValue);

      setTimeout(() => {
        processElement(index + 1);
      }, 0);
    }

    processElement(0);
  });
}


```
### Q3.2:
Write a JavaScript function called sumRange that calculates the sum of all integers in a given range. The function should use recursion to handle the calculation and demonstrate understanding of the call stack.
```
function sumRange(start, end) {
  if (start === end) {
    return start;
  } else {
    return start + sumRange(start + 1, end);
  }
}

```
