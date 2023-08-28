
## Equality: 
- Double equal : allows coercion (types different) , so we use with null or undefined
- Triple equal : disallows coercion (types same) , so we use it when types are the same
- The case for preferring Double equal : is about comparisons with known type(s), optionally
where conversions are helpful

### TypeScript : 
#### Benefits: 
-   Catch type-related mistakes
- Communicate type intent
-  Provide IDE feedback
 
#### Caveats: 
- Inferencing is best-guess, not a guarantee
- Annotations are optional
- Any part of the application that isn't typed introduces uncertainty


### Tasks :

QUESTION #2:
What will be the output of the following code snippet? Pick the right choice then justify your answer with an explanation.
```
function testScope1() {
  if (true) {
    var a = 1;
    let b = 2;
    const c = 3;
  }
  console.log(a);
  console.log(b);
  console.log(c);
}

testScope1();
```
Choices:

A) undefined, undefined, undefined
B) 1, undefined, ReferenceError
C) 1, ReferenceError, ReferenceError
D) 1, ReferenceError

The answer is "C"
1-Variable a is declared using var, which has function scope.
This means that it's accessible outside of the if block. So, the console.log(a); statement will output 1 since a was assigned the value 1 inside the if block.

2-Variable b is declared using let, which has block scope. It is only accessible within the if block. Therefore, the console.log(b); statement will result in a ReferenceError since b is not defined in the scope of the console.log.

3-Variable c is declared using const, which also has block scope. Like b, it's only accessible within the if block. Hence, the console.log(c); statement will also result in a ReferenceError since c is not defined in the scope of the console.log.

QUESTION #3:
What will be the output of the following code snippet? Pick the right choice then justify your answer with an explanation.
```
function testScope2() {
  console.log(a);
  console.log(b);
  console.log(c);
  if (true) {
    var a = 1;
    let b = 2;
    const c = 3;
  }
}

testScope2();
```
Choices:

A) undefined, ReferenceError
B) 1, undefined, ReferenceError
C)undefined, undefined, ReferenceError
D) 1, ReferenceError

The answer is "A"
1- The first console.log(a) encounters the declaration of variable a (due to hoisting), but since no value has been assigned yet, a is undefined.

2-The second console.log(b) encounters the declaration of variable b using let. Variables declared with let and const are not hoisted in the same way as var. They are in a "temporal dead zone" until they are actually declared. This is why trying to access b before its declaration leads to a ReferenceError.

3-The third console.log(c) encounters the declaration of variable c using const. Like let, variables declared with const are also not hoisted in the same way as var. Trying to access c before its declaration leads to a ReferenceError.

QUESTION #4:
What will be the output of the following code snippet? Pick the right choice then justify your answer with an explanation.
```
function testScope3() {
  var a = 36;
  let b = 100;
  const c = 45;

  console.log([a, b, c]);

  if (true) {
    var a = 1;
    let b = 2;
    const c = 3;

    console.log([a, b, c]);
  }

  console.log([a, b, c]);
}

testScope3();
```
choices:

A) [ 36, 100, 45 ] | [ 1, 2, 3 ] | [ 36, 2, 3 ]
B) [ 36, 100, 45 ] | [1, 2, 3 ] | [ 36, 100, 45 ]
C) [ 36, 100, 45 ] | [ 1, 2, 3 ] | [ 1,100, 45 ]
D) [ 36, 100, 45 ] | [ 1, 2, 3 ] | [ 1, 2, 3 ]

The answer is "C"

1. The if block, new declarations of variables a, b, and c are introduced using var, let, and const, respectively. 
These variables are shadowing (or hiding) the outer variables within the block.

2. The second console.log([a, b, c]) prints the values of the new variables a, b, and c inside the block, which are [1, 2, 3].

3. After the if block, the code continues executing outside the block. However, the outer variables a and c are modified within the block because of the var and const declarations respectively, so their values are updated. The variable b declared with let inside the block does not affect the outer variable b.

4. The third console.log([a, b, c]) prints the values of the modified variables a, b, and c outside the block, which are [1, 100, 45].



v
