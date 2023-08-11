
## Functions  :
Block of code that is designed to perform a particular task. Functions are executed when they are called.

### Functions return value : 
Functions in JavaScript can return values. To return a value from a function, you use the return keyword. The value that you return can be a number, a string, an object, or even another function.

### Arrow Functions : 

Are a new feature in JavaScript that were introduced in ES6. They are a concise way of writing functions that are often easier to read and understand than regular functions.

Arrow functions are written using the following syntax:
```
const myFunction = (parameter1, parameter2) => expression;

```

## Scope 
scope refers to the area where a variable or function is visible and accessible to other code.

- **Global scope** : The global scope is the outermost scope in a JavaScript program. Variables and functions declared in the global scope are accessible from anywhere in the program

- **Function scope** : When a function is declared, it creates a new scope. Variables and functions declared inside a function are only accessible from within the function

## var vs let:
1. var keyword was introduced in ES5 and has the following properties:

- It is hoisted, This means that you can access a var variable before it is declared.
- It has function scope
- It can be redeclared, which means that you can declare a variable with the same name twice in the same scope.

2. let keyword was introduced in ES6 and has the following properties:

- It is not hoisted, This means that you cannot access a let variable before it is declared.
- It has block scope
- It cannot be redeclared, which means that you cannot declare a variable with the same name twice in the same scope.

## Tasks:

### Q1:
Global Scope and Functions

```
// Declare the myGlobal variable below this line
let myGlobal = 10
let oopsGlobal;
function fun1() {
  // Assign 5 to oopsGlobal here
   oopsGlobal = 5
}

// Only change code above this line

function fun2() {
  let output = "";
  if (typeof myGlobal != "undefined") {
    output += "myGlobal: " + myGlobal;
  }
  if (typeof oopsGlobal != "undefined") {
    output += " oopsGlobal: " + oopsGlobal;
  }
  console.log(output);
}
```

### Q2:
Local Scope and Functions
```
function myLocalScope() {
  let myVar= 5

  console.log('inside myLocalScope', myVar);
}
myLocalScope();

// Run and check the console
// myVar is not defined outside of myLocalScope
console.log('outside myLocalScope', myVar);
```

### Q3:
Global vs. Local Scope in Functions


```
// Setup
const outerWear = "T-Shirt";

function myOutfit() {
  let outerWear  = "sweater"
  // Only change code below this line

  // Only change code above this line
  return outerWear;
}

myOutfit();

```
### Q4:
Stand in Line
```

function nextInLine(arr, item) {
  if(arr.length == 0) {
    return item;
  } else {
    let out = arr[0]
    arr.shift();
    arr.push(item);
    return out;
  }
}

// Setup
let testArr = [1, 2, 3, 4, 5];

// Display code
console.log("Before: " + JSON.stringify(testArr));
console.log(nextInLine(testArr, 6));
console.log("After: " + JSON.stringify(testArr));
```
