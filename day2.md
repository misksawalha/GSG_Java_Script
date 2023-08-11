
## Values & Data Types:
values it is a chunks of information and the
data types in javascript are two kind Primitive or Non-Primitive

 ### 1.  primitive 
primitive data types are basic data types that represent single values such as :
- Number
- String
- Boolean

 ### 2.  Non-Primitive
referred to as reference types or objects such as :
 - Object
 - Array

### Undefine vs Null?
Undefine : accidental nothing
Null : deliberate nothing

## String:
string : is made up of zero or more character units 

##  Operators:
- Arithmetic Operators:
- Assignment Operators
- Comparison Operators
- Logical Operators
- Ternary Operator
- Unary Operators
- Type Operators



## Expressions:
is a combination of values, variables, operators, and functions that can be evaluated to produce a result

### **Expressions vs Statments**
Expression: questions to aske javascript , what is the value?
Statments : is something we tell javascript to do



## Tasks:

### Q1:
Consider the following JavaScript code:

```
let a = 0;
let b = "0";
let c = false;
let d = "false";

console.log(a == b); //true :== compare the value without type
console.log(b === c); //false :=== compare the value without type
console.log(!!d);     //true  :When we use the double exclamation mark !! in JavaScript, it converts the value to a boolean type and then gives the opposite boolean value

```

### Q2:
Consider the following JavaScript expression:

```
console.log(4 + 5 * "7");//39

The multiplication operation attempts to convert the string '7' into a number and then multiplies it by 5. This gives us the value 35. When we add 4 to this value, the result is 39, which is the output
```

### Q3:
Evaluate the following expression:

```
let result = 5 + 2 * 3 - 1;//10
The reason is that the multiplication operation 2 * 3 evaluates first, resulting in 6. Then, adding 5 to 6 gives us 11, and finally, subtracting 1 from 11 yields the correct value of 10
```
### Q4:
Consider the following code:
```
let x = 10;
let y = '10';
console.log(x == y); //true
console.log(x === y); //false
because the == does not compare the type but === compare the type and we have interger and string so the answer was false 
```
### Q5:
Given the code below:
```
let num = "15";
let isPositive = true;
let result = (num > 10 && isPositive) || num < 0;
console.log(result); //true

The first expression, num > 10 && isPositive, evaluates to true because num is equal to 15, which is greater than 10, and isPositive is equal to true.

The second expression, num < 0, evaluates to false because num is not less than 0.

The || operator (or) returns the first expression if it is truthy, and the second expression if it is truthy. In this case, the first expression is truthy, so the value of result is true.

```
