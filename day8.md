##### Callback hell:
Also known as the "pyramid of doom," refers to a situation in JavaScript where multiple nested callbacks are used to handle asynchronous operations. This can lead to code that is difficult to read, understand, and maintain due to the deep nesting of functions. Asynchronous operations executed within callbacks can quickly become challenging to manage, making the code more error-prone and harder to debug.


## Tasks:

### Q1:
Write a closure named createCounter that takes an initial value start and returns a function. 
The returned function, when invoked, should increment the counter by 1 and return the updated value.

```
function createCounter(start){
     let counter = start;
      let increment = () =>{
       return counter++
      }
      return increment
}
```

### Q2:
Write a closure named calculateAverage that takes an array of numbers, nums, and returns a function. 
The returned function, 
when invoked, should calculate and return the average of the numbers in the array.
```
function calculateAverage(nums) {
    let sum = 0;
    let length = nums.length;
    if (length === 0) {
        return 0;
    } else {
        nums.forEach((item) => {
            sum += item;
        });
    }
    let avg = () => {
        return sum / length;
    };
    return avg;
}
```

### Q3:
Write a closure named powerOf that takes a base number base and returns a function. 
The returned function, when invoked with an exponent exp, should calculate and return the result of base raised to the power of exp.


```
function powerOf(base) {
    let pow = (exp)=>{
        return Math.pow(base, exp);
    }
    return pow
}
```
### Q4:
Write a closure named compose that takes multiple functions as arguments and returns a new function. 
The returned function should apply the provided functions in reverse order, passing the result of each function as an argument to the next function.
```
function compose(fun1,fun2){
      let out = (input) =>{
        return fun1(fun2(input))
      }
      return out;
}
function double(x) {
    return x * 2;
}
function square(x) {
    return x * x;
}
```
