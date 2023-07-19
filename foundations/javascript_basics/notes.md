# Fundamentals Part 1
## Variables
* Declare by either using the`let` or `var` operator
* Then assign value (content) to a variable (a box) by using the `=` operator
```
let message;
message = 'Hello';

let user = 'John', age = 25, message = 'Hello'

let user = 'John',
  age = 25,
  message = 'Hello';
```
* Declaring a variable twice will trigger an error
    * You can reassign a value to the variable, but you can't redeclare
    * Functional languages don't even let you reassign the variable value. i.e. Haskell
```
// ok
let message;
message = 'Hello';
message = 'World';

// NOT OK
let message = 'Hello';
let message = 'World';
```
### Naming Convention
* Variables are case sensitive
* Camel case is preferred
* We can technically create a variable with mere assignment, as long as `"use strict";` is not put in our script
```
num = 5;
alert(num);
```
### Constants
* We can declare an unchanging variable by using `const` instead of `let`
```
const myBirthday = '1993.08.24';

myBirthday = '2000.01.01'; // error, can't reassign constant
```
* Difficult to remembered values are often declared as uppercase constants
```
const COLOR_RED = "#F00";
const COLOR_GREEN = "#0F0";
const COLOR_BLUE = "#00F";

let color = COLOR_BLUE;
alert(color);  // #00F
```

## Tasks
1. Working with variables
```
let admin;
let name;  // or `let admin, name`

name = "John";

admin = name;

alert(admin);
```

2. Giving the right name
```
const ourPlanet = 'Earth'
let currentVisitor = "John";
```

3. Uppercase const
* It's indifferent whether we use upper case for birthday. It's a value that's known beforehand and thus could be hard coded.
* But it's not right to use upper case for age since it's not a hardcoded value