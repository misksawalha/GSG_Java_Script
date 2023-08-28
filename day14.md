
## Scope: 

#### lexical scope: 
Lexical scope, or static scope, is a fundamental concept in programming languages, including JavaScript. It defines how the scope of variables is determined based on the physical structure of the code, specifically how functions are nested within each other. In lexical scoping, the scope of a variable is determined by its position within the source code at the time of its declaration.
#### dynamic scope :
Dynamic scoping involves determining variable scope based on the call stack at runtime. When a function is called, the variables from the calling context become part of the function's scope, allowing it to access those variables.

#### Function scope:
Function scope in JavaScript refers to the concept that variables declared inside a function are only accessible within that function and not outside of it

#### IIFE Pattern : 
 stands for "Immediately Invoked Function Expression." It's a common pattern in JavaScript where a function is defined and then immediately executed right after its creation. This pattern is often used to create a new scope for variables and to encapsulate code, preventing variable names from polluting the global scop

### Hoisting :
behavior where variable and function declarations are moved to the top of their containing scope during the compilation phase, before the code is actually executed. This means that you can use variables and functions before they are declared in the code.
### Tasks :

QUESTION #1
Given the following code snippet and explain what's happening.
```
for (var i = 0; i < 5; i++) {
    setTimeout(function() {
      console.log("value of [i] is: ", i);
    }, 100);
}
```
The current output is: "value of [i] is: 5" five times.
The output should be:
"value of [i] is: ", 0 "value of [i] is: ", 1 "value of [i] is: ", 2 "value of [i] is: ", 3 "value of [i] is: ", 4
Without changing anything in the for loop's code itself, provide a solution to fix it.
```
for (var i = 0; i < 5; i++) {
  (function (index) {
    setTimeout(function () {
      console.log("value of [i] is: ", index);
    }, 100);
  })(i);
}
```
QUESTION #2
Given the following code snippet and explain what's happening.
```
for (let i = 0; i < 5; i++) {
   let array = [];
   array.push(i);
   console.log("Current array is: ", array)
}
```
The current output is:

"Current array is: [ 0 ]" "Current array is: [ 1 ]" "Current array is: [ 2 ]" "Current array is: [ 3 ]" "Current array is: [ 4 ]".

The output should be: "Current array is: [0, 1, 2, 3, 4]".

Provide a solution to fix it.
```
let array = []; 

for (let i = 0; i < 5; i++) {
  array.push(i);
  console.log("Current array is: ", array);
}
```


QUESTION #3
Given the following code snippet and explain what's happening.
```
let functions = [];

for (var i = 0; i < 5; i++) {
  functions.push(() => {
    console.log("Current value of i is:", i);
  });
}

functions.forEach((func) => func());
```
The current output is:

"Current value of i is: 5" "Current value of i is: 5" "Current value of i is: 5" "Current value of i is: 5" "Current value of i is: 5"

The output should be:

"Current value of i is: 0" "Current value of i is: 1" "Current value of i is: 2" "Current value of i is: 3" "Current value of i is: 4"

Provide a solution to fix it.
```
let functions = [];

for (let i = 0; i < 5; i++) {
  functions.push(() => {
    console.log("Current value of i is:", i);
  });
}

functions.forEach((func) => func());
```
