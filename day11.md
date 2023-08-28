
## Types: 
- Primitive Types :basic building blocks of data that represent single values. They are immutable, meaning their values cannot be changed after they are created some Primitive types : undefined , string , number , boolean , objects , symbols and BigInt


### Undefined vs undeclared : 
- undefined : it is currently does not have a value 
- undeclared : it is never been created in any scope that we have access to 
- uninitialized (TDZ) : it is off limits , you are not allowed to touch it any way 

### Special values:
1. NAN : indicates an invalid number , and it is the only does not to it self 

2. Negative Zero . 

### Fundamental Objects : 
1. Built-In Objects
2. Native Functions

### Coercion (Type conversion):

#### ToPrimitive(hint) :
- When we use the ToPrimitive operation, if the returned result is not a primitive but instead another non-primitive, like another object, the operation will be invoked again repeatedly until an actual primitive value is obtained.
- ToString 
- ToNumber
- ToBoolean 

#### Boxing :
Refers to the process of automatically converting a primitive data type (like a number or a string) into its corresponding object wrapper (Number, String, Boolean) when a property or method that belongs to the object wrapper is accessed.

### Tasks :
Question 1:
Write a function called convertStringToNumber that converts a string to a number using the unary plus operator.

If the input is not a string, return an object of the input's value and type.
```
function convertStringToNumber(input) {
    if (typeof input === 'string') {
        return +input; 
    } else {
        return {
            value: input,
            type: typeof input
        };
    }
}
```
Question 2:
Write a function called checkNaN that takes a single argument and returns true if the argument is NaN and false otherwise.
```
const checkNaN = (value) => {
  return Number.isNaN(value);
}
```
Question 3:
Write a function called isEmptyValue that checks if a given input is an empty value (undefined, null, or empty string).
```
function isEmptyValue(value) {
  return value === undefined || value === null || value === "";
}
```
Question 4:
Write a function called compareObjects that takes 2 arguments of type "object" and compares them. If both arguments are equal, return true. If not, return false.
```
If either argument is not of type "object", the function should return an array of the arguments.

function compareObjects(obj1, obj2) {
  if (typeof obj1 !== 'object' || typeof obj2 !== 'object') {
    return [obj1, obj2];
  }
  
  const keys1 = Object.keys(obj1);
  const keys2 = Object.keys(obj2);
  
  if (keys1.length !== keys2.length) {
    return false;
  }
  
  for (const key of keys1) {
    if (obj1[key] !== obj2[key]) {
      return false;
    }
  }
  
  return true;
}
```
Question 5:
Write a function called complexCoercion that takes a single argument and checks if its type is primitive, and if so returns a coerced value according to the rules below.

coercion rules:

if input is primive and:
if input is a number, convert to string and then return a boolean.
if input is a string, return a boolean.
if input is null or undefined, return false.
If input is not a primitive type, return the argument.
```
function complexCoercion(input) {
    if (typeof input === 'number') {
        return Boolean(String(input));
    } else if (typeof input === 'string') {
        return Boolean(input);
    } else if (input === null || input === undefined) {
        return false;
    } else {
        return input;
    }
}
```
