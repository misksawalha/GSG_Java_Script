
## Conditional  :
Conditional statements in JavaScript are used to control the flow of execution of a program. They allow you to specify blocks of code that should only be executed if a certain condition is met.

### Three main types of conditional statements  : 
- If statements
- Else statements
- Else if statements

### Logical and ternary operations : 

Logical operators are used to combine multiple conditions into a single expression. The three main logical operators in JavaScript are:
- && (AND)
- || (OR)
- ! (NOT)

Ternary operators are used to assign a value to a variable based on a condition.The syntax for the ternary operator is as follows:

```
condition ? expression1 : expression2
```

## Loops 
used to execute a block of code repeatedly.

#### There are four main types of loops 
 ##### 1. For loop
 ##### 2. Do...while loop
 ##### 3. While loop


## Map & Filter:
 - **Map** : takes a function as an argument and applies that function to each element in the array

 - **Filter** :takes a function as an argument and returns a new array with the elements that satisfy the function


## Tasks:

### Q1:
Use Multiple Conditional (Ternary) Operators

```
function checkSign(num) {
 return (num == 0) ?"zero" : (num > 0)?"positive":"negative"
}

checkSign(10);
```

### Q2:
Use the map Method to Extract Data from an Array
```
const ratings = watchList.map(item => ({ title: item["Title"], rating: item["imdbRating"] }));
```

### Q3:
Use the filter Method to Extract Data from an Array
```
const filteredList = watchList.filter(item => parseFloat(item.imdbRating) > 8.0).map(item => ({ title: item.Title, rating: item.imdbRating }));

```
### Q4:
Golf Code
```
const names = ["Hole-in-one!", "Eagle", "Birdie", "Par", "Bogey", "Double Bogey", "Go Home!"];

function golfScore(par, strokes) {
   if (strokes === 1) {
    return names[0];
  } else if (strokes <= par - 2) {
    return names[1];
  } else if (strokes === par - 1) {
    return names[2];
  } else if (strokes === par) {
    return names[3];
  } else if (strokes === par + 1) {
    return names[4];
  } else if (strokes === par + 2) {
    return names[5];
  } else {
    return names[6];
  }

}

golfScore(5, 4);
```
