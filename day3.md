
## Arrays :
Arrays can be used to store and manipulate collections of values. An array can be empty or hold a single item, and it can contain a mix of various types of items. Elements within an array are accessed using numerical indices

**Array methods**:

JavaScript has a number of built-in array methods that can be used to manipulate arrays. Here are some of the most common array methods:

- pop()
- push()
- slice()
- sort()
- indexOf()
- contact()
- map()
- filter()

 ## Mutability 
Ability to change the value of a variable after it has been created

## Mutable Vs Immutable:
- Immutable: meaning that their values cannot be changed after they have been created such as Primitive data types
- Mutable: non Primitive data types are mutable. This means that the values of reference data types can be changed after they have been created.

## Objects :
is a collection of related data and functionality. These usually consist of several variables and functions (properties and methods when they are inside objects).
## Tasks:

### Q1:
Copy Array Items Using slice():

```
function forecast(arr) {
  // Only change code below this line
  arr = arr.slice(2, 4);
  return arr;
}

// Only change code above this line
console.log(forecast(['cold', 'rainy', 'warm', 'sunny', 'cool', 'thunderstorms']));
```

### Q2:
Combine Arrays with the Spread Operator
```
function spreadOut() {
  let fragment = ["to", "code"];
  let sentence = ["learning", ...fragment, "is", "fun"]; // change this line
  return sentence;
}

// do not change code below this line
console.log(spreadOut());
```

### Q3:
EProfile Lookup

```
// Setup
const contacts = [
  {
    firstName: "Akira",
    lastName: "Laine",
    number: "0543236543",
    likes: ["Pizza", "Coding", "Brownie Points"],
  },
  {
    firstName: "Harry",
    lastName: "Potter",
    number: "0994372684",
    likes: ["Hogwarts", "Magic", "Hagrid"],
  },
  {
    firstName: "Sherlock",
    lastName: "Holmes",
    number: "0487345643",
    likes: ["Intriguing Cases", "Violin"],
  },
  {
    firstName: "Kristian",
    lastName: "Vos",
    number: "unknown",
    likes: ["JavaScript", "Gaming", "Foxes"],
  },
];

function lookUpProfile(name, prop) {
  for (const contact of contacts) {
    if (contact.firstName === name) {
      if (contact.hasOwnProperty(prop)) {
        return contact[prop];
      } else {
        return "No such property";
      }
    }
  }
  return "No such contact";
}


console.log(lookUpProfile("Kristian", "lastName")); 
console.log(lookUpProfile("Sherlock", "likes")); 
console.log(lookUpProfile("Harry", "likes")); 
console.log(lookUpProfile("Bob", "number")); 
console.log(lookUpProfile("Bob", "potato")); 
console.log(lookUpProfile("Akira", "address")); 

```
### Q4:
Write Reusable JavaScript with Functions:

```
function reusableFunction () {
  console.log("Hi World");
}
reusableFunction ()
```
### Q5:
Understanding Undefined Value returned from a Function

```
// Setup
let sum = 0;

function addThree() {
  sum = sum + 3;
}
function addFive() {
  sum = sum + 5;
}

// Only change code below this line


// Only change code above this line

addThree();
addFive();

```
### Q6:
Return a Value from a Function with Return
```
function timesFive(num) {
  return num*5;
}

console.log(timesFive(5)) ;
console.log(timesFive(2)) ;
console.log(timesFive(0)) ;
```
