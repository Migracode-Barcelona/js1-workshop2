# 2 - Expressions and loops

> ⚠️ **If your assignment has been given to you through GitHub Classroom, this repository *does not need to be forked*: open the created repository using CodeSpaces OR clone the created repository!**

> 💡 Inside a CodeSpace or VS Code, you can also use the shortcut: Control+Alt+N (or ⌃ Control+⌥ Option+N on macOS), or press F1 and then select/type Run Code, the code will run and the output will be shown in the Output window.

## Learning Objectives

By the end of this class, you should be able to:

* What are expressions and statements (and what's the difference)?
* Define what expressions and statements are and describe the difference
* Define what was a conditional is
* Define what `for` and `while` loops are and define the difference
* Write an if statement using a conditional
* Define comparator operators and list the different types
* Use comparator operators in an `if` statement
* Define what a logical operator is and give examples
* Describe what an array is and write code that interacts with them

## Expressions

In JavaScript, there are **expressions** and **statements**. We will use these words frequently to describe code.

#### Expression <a href="#expression" id="expression"></a>

An expression returns a value. Sometimes we will say that an expression _evaluates to_ a value.

The following are all examples of expressions:

```
1 + 1; // returns 2
("hello"); // returns "hello"
2 * 4; // returns 8
"Hello" + "World"; // returns "HelloWorld"
```

We can take the value produced by an expression and assign it to a variable. That line of code would be called a statement.

Expressions can also contain variables.

```
function greetingPlanet() {
  const planet = "Earth";
  return `Hello ${planet}`; // returns Hello Earth
}
```

You can also use expressions inside a string interpolation or as a `return` value.

```
console.log(`2 + 4 is ${2 + 4}`); // 2 + 4 is 6

function double(num) {
  return num * 2; // expression being returned
}
```

#### Statement <a href="#statement" id="statement"></a>

A statement is some code that performs an action. Here are some examples:

```
const sum = 1 + 1; // action: assigns result of `1 + 1` to variable `sum`
const greeting = "hello"; // action: assigns result of the expression "hello" to variable `greeting`
console.log(2 * 4); // action: logs the result of `2 * 4` to the console
sayGreeting(greeting); // action: calls the function `sayGreeting` with the parameter `greeting`
```

There are some other different types of statements that we will learn in the coming weeks.

You can run `node` by itself, which will open a _node console_, also called a [Read–Eval–Print Loop (REPL)](https://www.tutorialspoint.com/nodejs/nodejs\_repl\_terminal.htm).

This console allows you to run expressions in the console line by line and is a great way of testing bits of code before writing it in a script.

#### Exercise A (5 mins) <a href="#exercise-a-5-mins" id="exercise-a-5-mins"></a>

In your VS Code terminal, run the command `node` and run the following expressions. What are their outputs? Is there anything you didn't expect? (To exit the node REPL, you have to click Ctrl+d or Cmd+D on Mac)

* `1 + 2`
* `"hello"`
* `let favouriteColour = "purple"`
* `favouriteColour`
* `console.log(favouriteColour)`

### Booleans <a href="#booleans" id="booleans"></a>

There is another _primitive type_ in JavaScript known as a **boolean** value. A boolean is either `true` or `false`, and it should be written without quotes.

```
let codeYourFutureIsGreat = true;
let thisIsATerribleClass = false;
```

#### Exercise B (10 mins) <a href="#exercise-b-10-mins" id="exercise-b-10-mins"></a>

1. In a node REPL, what is the `typeof` a `true` or `false`?
2. Pair up and correct the following function so that the output returns `"You've given me a bool, thanks!"`

```
function boolChecker(bool) {
  if (typeof bool === ) {
    return "You've given me a bool, thanks!";
  }

  return "No bool, not cool.";
}

boolChecker(true);
```

1. As a class, can you step through the function and explain what each line does?

### Comparison Operators <a href="#comparison-operators" id="comparison-operators"></a>

In the previous exercise, you used an **expression** that returns a `boolean` value. This was possible because of the **comparison operator** `===`. Using a comparison operator will always return a `boolean` value.

Comparison operators are used in logical statements to determine equality or difference between variables or values.

Given that `x = 5`, the table below explains the comparison operators:

| Operator | Description                       | Comparing | Returns |
| -------- | --------------------------------- | --------- | ------- |
| ==       | equal to                          | x == 8    | false   |
|          |                                   | x == 5    | true    |
|          |                                   | x == "5"  | true    |
| ===      | equal value and equal type        | x === 5   | true    |
|          |                                   | x === "5" | false   |
| !=       | not equal                         | x != 8    | true    |
| !==      | not equal value or not equal type | x !== 5   | false   |
|          |                                   | x !== "5" | true    |
|          |                                   | x !== 8   | true    |
| >        | greater than                      | x > 8     | false   |
| <        | less than                         | x < 8     | true    |
| >=       | greater than or equal to          | x >= 8    | false   |
| <=       | less than or equal to             | x <= 8    | true    |

### Conditionals <a href="#conditionals" id="conditionals"></a>

Like humans, computer programs make decisions based on the information given to them. **Conditionals** are a way of representing these decisions in code (remember, you saw this in a previous exercise!)

For example:

* In a game, if the player has 0 lives, then the game is over
* In a weather app, if rain is forecast, a picture of rain clouds is shown

The most common type of conditional is the **if statement**.

An if statement runs some code if a condition is met. If the condition is not met, then the code will be skipped.

```
let isHappy = true;

if (isHappy) {
  console.log("I am happy");
}
```

The code in parentheses - e.g. `(isHappy)` - is the condition. The condition can be _any_ expression. The following are all valid conditions:

```
// boolean value
if (true) {
  // do something
}

// variable assigned to boolean value
let isHappy = true;
if (isHappy) {
  // do something
}

// equality operator returns a boolean value
if (1 + 1 === 2) {
  // do something
}

// comparison operator returns a boolean value
if (10 > 5) {
  // do something
}

// function call returns boolean value
if (greaterThan10(5)) {
  // do something
}
```

An `if` statement runs code when a condition is met. What if the condition is not met? Sometimes you want to run an alternative bit of code.

An **if...else statement** also runs code when the condition is _not_ met.

```
let isHappy = true;

if (isHappy) {
  console.log("I am happy 😄");
} else {
  console.log("I am not happy 😢");
}
```

You can use **else if** to handle multiple conditions.

```
const age = 24;
if (age >= 65) {
    console.log("John is an old guy.")
} else if (age < 18) {
    console.log("John is a young boy."); 
} else {
    console.log("John is an adult."); 
}
```

#### Exercise C (5 mins) <a href="#exercise-c-5-mins" id="exercise-c-5-mins"></a>

Can you explain what this function does line by line? What happens when you pass in a string?

```
function numberChecker(num) {
  if (num > 20) {
    return `${num} is greater than 20`;
  } else if (num === 20) {
    return `${num} is equal to 20`;
  } else if (num < 20) {
    return `${num} is less than 20`;
  } else {
    return `${num} isn't even a number :(`;
  }
}
```

#### Exercise D (10 mins) <a href="#exercise-d-10-mins" id="exercise-d-10-mins"></a>

Create a function that gives you a message depending on your mood! It should:

* take one input
* return "Good job, you're doing great!" if you pass in "happy"
* return "Every cloud has a silver lining" if you pass in "sad"
* return "Beep beep boop" if you pass in a number
* return "I'm sorry, I'm still learning about feelings!" if you pass in anything else

### Logical Operators <a href="#logical-operators" id="logical-operators"></a>

Logical operators are used to determine the logic between variables or values.

There are three logical operators in JavaScript: `||` (OR), `&&` (AND), `!` (NOT).

They let you write expressions that evaluate to a boolean value.

Given that `x = 6` and `y = 3`, the table below explains the logical operators:

| Operator | Description | Example                       |
| -------- | ----------- | ----------------------------- |
| &&       | and         | (x < 10 && y > 1) is true     |
| \|\|     | or          | (x == 5 \|\| y == 5) is false |
| !        | not         | !(x == y) is true             |

Suppose you want to test if a number is bigger than 3 and smaller than 10. We can write this, using different logical operators.

```
let num = 10;

function satisfiesRequirements(num) {
  if (num > 3 && num < 10) {
    return true;
  }

  return false;
}
```

We can test expressions with logical operators in a node console too.

#### Exercise E (5 mins) <a href="#exercise-e-5-mins" id="exercise-e-5-mins"></a>

Type the following expressions into your node REPL and note the output. Anything you didn't expect?

* `let num = 10`
* `num > 5 && num < 15`
* `num < 10 || num === 10`
* `false || true`
* `!true`
* `let greaterThan5 = num > 5`
* `!greaterThan5`
* `!(num === 10)`

#### Exercise F (15 mins) <a href="#exercise-f-15-mins" id="exercise-f-15-mins"></a>

In pairs, write a function that checks a username is of an acceptable format for a user type. The function must:

* take two parameters: one for the username and one for the user type
* if the username starts with a capital letter _and_ has length between 5 and 10 characters long, it must return `"Username valid"`; otherwise, it must return `"Username invalid"`
* if the user type is an `admin` _or_ a `manager`, all usernames must return `"Username valid"`

## Loops

When we're writing programs, we often find that we want to repeat a bit of code over and over, or repeat it but change something about it each time. To save ourselves from writing all that code, we can use a **loop**. JavaScript has two kinds of loops, a `while` loop and a `for` loop.

#### while loop <a href="#while-loop" id="while-loop"></a>

Programs are very efficient when executing recurring tasks, but now imagine you are asked to log numbers from 1 to 100:

```
console.log("The count is 1");
console.log("The count is 2");
console.log("The count is 3");
console.log("The count is 4");
console.log("The count is 5");
// ...
console.log("The count is 100");
```

Although this would work you would need to write 100 lines of code to achieve the desired output. A better solution for this problem would require that we could execute a block of code multiple times. This form of control is what we call a loop.

There are many ways to create a loop in a program, the first we will study is the `while` loop:

#### `while ( ) { //... }` <a href="#while" id="while"></a>

```
let count = 1;
while (count <= 100) {
  console.log("The count is: " + count);
  count += 1;
}
```

The `while` statement creates a loop. The syntax is somehow similar to the `if` statement, it evaluates a condition inside the parentheses `(true|false)` and then it executes the code inside the `{ }` block only if that condition evaluates to `true`.

#### Exercise G (10 mins) <a href="#exercise-g-10-mins" id="exercise-g-10-mins"></a>

Log the Apollo 11 countdown, use the message provided as the last output. It starts from 8 till 0!

```
const apolloCountdownMessage = "all engine running... LIFT-OFF!";
let countdown = 8;

console.log(apolloCountdownMessage);
```

Expected output

```
8
7
6
5
4
3
2
1
0
all engine running... LIFT-OFF!
```

#### for loop <a href="#for-loop" id="for-loop"></a>

The `for` loop is similar to a while loop, but with a more specialized syntax. Programmers invented the for loop when they realized they were always doing the same three things: creating loop counter variables (like `i` above), incrementing them by some amount, and checking that they're less than a value.

The `for` loop syntax has special places for each of those three things. Here's the same loop as the first while loop above, as a for loop:

#### `for (initialization; condition; final-expression) { //... }` <a href="#for-initialization-condition-final-expression" id="for-initialization-condition-final-expression"></a>

![For loop](https://user-images.githubusercontent.com/31692/75388870-9213a880-58dd-11ea-90e6-4e67eabf390b.png)

```
for (let i = 0; i < 100; i++) {
  console.log("The count is: " + counter);
}
```

The initialization is `let i = 0`, the condition is `i < 100` and the final-expression is `i++`. Those blocks can be seen inside the parentheses after the `for` keyword and separated by semicolons `;`, in the following order `(initialization; condition; final-expression)`.

Notice the line **i++** - this is the same as saying **i = i + 1** It does exactly the same thing but it is just more convenient to write.

#### Exercise H (10 mins) <a href="#exercise-h-10-mins" id="exercise-h-10-mins"></a>

Calculate the exponential of the even numbers from 5 to 20 Using a for loop and the helper functions provided.

```
function exponential(number) {
  return number * number;
}

function isEven(number) {
  return number % 2 === 0;
}
```

Expected output

```
The exponential of 6 is 36
The exponential of 8 is 64
The exponential of 10 is 100
The exponential of 12 is 144
The exponential of 14 is 196
The exponential of 16 is 256
The exponential of 18 is 324
```

## Arrays

If you ever find yourself writing code like this...

```
const mentor1 = "Daniel";
const mentor2 = "Irina";
const mentor3 = "Rares";
```

...then it's probably time to use an **array**!

Arrays are data structures that hold a list of values. We call these values the **elements** of the array.

```
const mentors = ["Daniel", "Irina", "Rares"];
```

Arrays can hold any type of value (although almost always you only have one data type per array).

```
const testScores = [16, 49, 85];
const grades = ["F", "D", "A"];
const greetings = ["Hello, how are you?", "Hi! Nice to meet you!"];
```

You can access elements in an array using the **index** of an element with **bracket notation**

**🔔 Remember:** All arrays start at position 0! To access the first element in an array, you need to access index `0`, the second element at `1`, the fifth at `4` and so forth. This is called zero-based indexed arrays. There are some [very intense reasons for this](http://www.cs.utexas.edu/users/EWD/transcriptions/EWD08xx/EWD831.html), but most people just accept it and move on.

```
const students = ["Ahmed", "Maria", "Atanas", "Nahidul", "Jack"];

students[0]; // "Ahmed"
students[3]; // "Nahidul"
```

You can also _assign_ new values to parts of an array:

```
const students = ["Ahmed", "Maria", "Atanas", "Nahidul", "Jack"];

students[2] = "Bianca";

console.log(students); // ["Ahmed", "Maria", "Bianca", "Nahidul", "Jack"]
```

#### Exercise I (5 mins) <a href="#exercise-i-5-mins" id="exercise-i-5-mins"></a>

In the node REPL, enter the following array:

```
> const fruits = ['banana', 'apple', 'strawberry', 'kiwi', 'fig', 'orange'];
```

Now, using the correct indexes, get the following values from the array:

* strawberry
* kiwi
* orange
* banana

Then, replace 'apple' with 'raspberry', and replace 'fig' with 'pineapple'.

#### Exercise J (5 mins) <a href="#exercise-j-5-mins" id="exercise-j-5-mins"></a>

Complete this function so that, if the second index in the array contains the name "Amy", it returns `"Second index matched!"`

```
function secondMatchesAmy(array) {
  if ( ) {
    return "Second index matched!";
  }
  return "Second index not matched";
}
```

#### Using for loops with arrays <a href="#using-for-loops-with-arrays" id="using-for-loops-with-arrays"></a>

We can use the power of loops to run some code for each element in our array.

When we do this say we **iterate** over an array.

```
const daysOfWeek = [
  "Monday",
  "Tuesday",
  "Wednesday",
  "Thursday",
  "Friday",
  "Saturday",
  "Sunday",
];

for (let i = 0; i < daysOfWeek.length; i++) {
  const dayMessage = "day is: " + daysOfWeek[i];
  const indexMessage = "index is: " + i;
  console.log(indexMessage, dayMessage);
}
```

#### Exercise K (10 mins) <a href="#exercise-k-10-mins" id="exercise-k-10-mins"></a>

Write a function which takes your **students** array as an input. In the function, use a for loop to **iterate** over the array and print the name of each student to the console.

### Glossary <a href="#glossary" id="glossary"></a>

* Duplicate: exact copies of something (e.g. two or more files, numbers, directory can be exactly the same)
* Index: numbers that let you know an item's position inside an array
* Element: another name for an item in an array
* Iterate: to repeat some code multiple times, as we do when we use a loop
* REPL: (Read-Eval-Print-Loop) an interactive way to execute code you write inside the console
* Zero-based Index: an `array` starting at `0` and not at `1`

For words like **Terminal**, **Primitive Types** please see [Glossary: JavaScript Core I - 2](https://migracode-barcelona.github.io/syllabus/js-core/week-1/lesson.md#Glossary)

## References <a href="#references" id="references"></a>

* [Comparisons in JS (javascript.info)](https://javascript.info/comparison)
* [Logical operators in JS (javascript.info)](https://javascript.info/logical-operators)
* [More on operators (javascript.info)](https://javascript.info/operators)
* [`while` loops (developer.mozilla.org)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while)
* [`for` loops (developer.mozilla.org)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
* [Loops in JS (javascript.info)](https://javascript.info/while-for)
* [Switch statements (javascript.info)](https://javascript.info/switch)
* [Arrays (developer.mozilla.org)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array)
* [What are algorithms](https://www.khanacademy.org/computing/computer-science/algorithms/intro-to-algorithms/v/what-are-algorithms)
* [Bubble sort](https://humanwhocodes.com/blog/2009/05/26/computer-science-in-javascript-bubble-sort/)

