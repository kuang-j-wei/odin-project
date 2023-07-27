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
### Declare without `let` or `var`
* We can assign a value without using the `let` or `var` operands
* We must assign a value immediately, i.e. `x = 4`
* But the variable then becomes a global variable - even if initially declared inside a function it will be globally visible

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

### Variables Tasks
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

## Numbers
* JavaScript only has one type of `Number` - 64-bit floating point
  * Integers are accurate up to 15 digits
  * Floats are accurate up to 17th decimals
* If we add number and a string with the operand `+`, the result will be a string concatenation
  * Numbers will be calculated according to the arithmetic rule
* But for other operands like `/`, JavaScript will try to convert strings into numbers then perform the operation
* But trying to do things like `let x = 100 / "Apple"` will result in `NaN`
  * The global function `isNaN()` can check whether a variable is `NaN`
* `NaN` can also be concatenated, i.e. `NaN + "5"` gives you `"NaN5"`
    * But `NaN - 0` gives you `0`
* `Infinity` is a reserved name that represents a number outside the largest possible number
  * It's of type `number`
* Anything preceded by `0x` is interpreted as hexadecimal numeric constant
* We can convert number representations with `toString()` like so
```
let myNumber = 32;
myNumber.toString(32); // w
myNumber.toString(16); // 10
myNumber.toString(12); // 28
myNumber.toString(10); // 32
myNumber.toString(8); // 40
myNumber.toString(2); // 100000
```
* Numbers are typically primitive values like `let x = 123;`, but we can also defind them as objects with the keyword `new`, `let y = new Number(123)`
  * Then `x == y` but `x === y` is not true
  * Two objects always return `false` when using the `===` operand

### Useful Number Methods
* We can round `Number` instances with the method `toFixed()`

### Converting to number data types
* `Number(String)` to turn a string into a `number`
* `null` gets converted to 0
* `undefined` gets converted to `NaN`

### Increment and decrement operators
* When we do `variable++`, the interpreter returns the current value, _then_ increments the variable
* If you instead like to increment, then return we do `++variable`

### Comparison operators
* `===` - strict equality
  * Test whether the left and right values are identical
  * If the two objects are not the same object, it will return `false`
  * `5 === 3+2` will return `true`
  * `let z = 5, z1 = 3+2`, and `z === z1` will be true because primitive number values are assigned. They are not considered new objects
* `!==` - strict non-equality

## Operators
### Numeric conversion
* `+` as an unary operator can turn variables into `number`. i.e. `+""` becomes 0 and `+true` becomes 1
### Operator precedence
* Unary operators take precedence over binary operators
* Here is the full [prescedence table](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)
### Assignment operator `=`
* All operators in JS **returns** a value, and `=` does too
* This allows for chaining assignment `let x = y = c = 2+2`, as each `=` returns a value
* Note that the modify inplace operators like `*=` has the same precedence as assignment, so it gets run last
### Comma operator `,`
* All expressions before `,` are evaluated but only the last one is returned
* `,` has the lowest precedence lower than `=` so `()` is very important to make sure the right thing gets done

## Knowledge Check
> Name the three ways to declare a variable
1. `let`
2. `var`
3. `const`

> Which of the three variable declarations should you avoid and why?
* `var` sometimes doesn't give expected results

> What rules should you follow when naming variables?
* First character must not be a digit
* Name must contain only letters, digits, or the symbols `$` and `_`
* Not one of the reserved names like `let`
* Sensible
* Meaningful
* Use camel case

> What happens when you add numbers and strings together?
* It's executed as concatenation
> How does the Modulo (%), or Remainder, operator work?
* It divides the former with latter, then returns the remainder
> Explain the difference between == and ===.
* `==` only compares values, and will do type coercion
* `===` is a strict equal. It will not correct types
* In general in JS, comparing two objects will always return false
> When would you receive a NaN result?
* Doing arithmetic with non-numeric strings

> How do you increment and decrement a number?
* `++` and `--` operators
> Explain the difference between prefixing and postfixing increment/decrement operators.
* prefixing: returns the value _before_ the increment. i.e. `let a = 1; ++a returns 2 (but a is now 2)`
* postfixing: returns the value _after_ the increment i.e. `let a = 1; a++ returns 2 (and a is now 2)`
> What is operator precedence and how is it handled in JS?
* It determines which operation gets run first
* It's determined by predefined rules
> How do you access developer tools and the console?
* `Right click` -> `Inspect` -> `Console`
> How do you log information to the console?
* `console.log()`
> What does unary plus operator do to string representations of integers? eg. +”10”
* It turns them into `number` type i.e. this gets turned into `10`
