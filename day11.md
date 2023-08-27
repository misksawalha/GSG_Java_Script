
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