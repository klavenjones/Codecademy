# JavaScript

What is JavaScript?

Javascript is a dynamic computer programming language. It is lightweight and most commonly used as a part of web pages, whose implementations allow client-side script to interact with the user and make dynamic pages. It is an *interpreted programming *language with* object-oriented* capabilities.


**Client-side JavaScript** extends the core language by supplying objects to control a browser and its *Document Object Model (DOM)*. For example, *client-side* extensions allow an application to place elements on an HTML form and respond to user events such as mouse clicks, form input, and page navigation.

**Server-side JavaScript** extends the core language by supplying objects relevant to running JavaScript on a server. For example, *server-side* extensions allow an application to communicate with a database, provide continuity of information from one invocation to another of the application, or perform file manipulations on a server.

**Advantages**

**Javascript is executed on the client side**
This means that the code is executed on the user's processor instead of the web server thus saving bandwidth and strain on the web server.

**Javascript is a relatively easy language**
The Javascript language is relatively easy to learn and comprises of syntax that is close to English. It uses the DOM model that provides plenty of prewritten functionality to the various objects on pages making it a breeze to develop a script to solve a custom purpose.

**Javascript is relatively fast to the end user**
As the code is executed on the user's computer, results and processing is completed almost instantly depending on the task (tasks in javascript on web pages are usually simple so as to prevent being a memory hog) as it does not need to be processed in the site's web server and sent back to the user consuming local as well as server bandwidth. 

**Extended functionality to web pages**
Third party add-ons like Greasemonkey enable Javascript developers to write snippets of Javascript which can execute on desired web pages to extend its functionality. If you use a website and require a certain feature to be included, you can write it yourself and use an add-on like Greasemonkey to implement it on the web page. 

Disadvantages

**Security Issues**
Javascript snippets, once appended onto web pages execute on client servers immediately and therefore can also be used to exploit the user's system. While a certain restriction is set by modern web standards on browsers, malicious code can still be executed complying with the restrictions set.

**Javascript rendering varies**
Different layout engines may render Javascript differently resulting in inconsistency in terms of functionality and interface. While the latest versions of javascript and rendering have been geared towards a universal standard, certain variations still exist. Website Usability Consultants all over the world make a living on these differences, but it enrages thousands of developers on a daily basis.



## Basics of JavaScript

### **Variables**

Variables are "containers" that you can store *values* in. You start by *declaring* a variable with the var keyword, followed by any name you want to call it:

```javascript
var myVariable;
```

Once *declared* you can *assign* it a *value.  *When you initially assign a value to your variable (assigning  for the first time) you are *initializing* the variable. 

```javascript
myVariable = "Initialize me!";
```

There are *data types* in which you can assign to variables. 

### **Primitave data types:**

**Boolean **- Boolean represents a logical entity and can have two values: true, and false.

**null **-** **The Null type has exactly one value: [null](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null). 

**undefined **- A variable that has not been assigned a value has the value [undefined](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined). 

**Number **- e.g. 42 or 3.14159.

**String  - **JavaScript's* [String*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) type is used to represent textual data.  JavaScript Strings are immutable, meaning they cannot be changed.  e.g  "Howdy"

**Symbol** - [*Symbols *](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol)are new to JavaScript in ECMAScript Edition 6. A Symbol is a unique and immutable primitive value and may be used as the key of an Object property

### **Non-Primitave datatype:**

**Object **- In computer science, an object is a value in memory which is possibly referenced by an* [identifier*](https://developer.mozilla.org/en-US/docs/Glossary/Identifier).

For more details of what objects are go [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures). 



## **Scope**

### What is scope?

Scope is the *accessibility of variables*, functions, and objects in some particular part of your code during runtime. In other words, scope determines the visibility of variables and other resources in areas of your code.

### Scope in JavaScript

In javascript, there are two kinds of scope: *local scope* and *global scope*

Variables *defined* inside a *function* are in *local scope* while variables defined outside of a function are in the *global scope*. Each function when invoked creates a new scope.

### Global Scope
When you start writing JavaScript in a document, *you are already in *the Global scope. *There is only one Global scope* throughout a JavaScript document. A variable is in the Global scope if it's defined outside of a function.

```javascript
//Scope by default is global scope
//Any variable defined in the global scope can be accessed by any function.
console.log(myName); // logs 'Klay'

function logName() {
    console.log(myName); // 'myName' is accessible here and everywhere else
}

  logName(); // logs 'Klay'   
```

### Local Scope
Variables defined *inside a function* are in the local scope. And they have a *different scope for every call* of that function. This means that variables having the same name can be used in different functions. This is because those variables are bound to their respective functions, each having different scopes, and are not accessible in other functions.

```javascript
// Global Scope
function someFunction() {
    // Local Scope #1
    function someOtherFunction() {
       //Local Scope #2
    }
}
// Global Scope
function anotherFunction() {
    // Local Scope #3
}

```
 
##  Block Level Scope
 
Block statements like` if `and `switch` conditions or `for` and `while` loops, unlike functions, don't create a new scope. Variables defined inside of a *block statement will remain in the scope they were already in*. 

```javascript
if (true) {
    // this 'if' conditional block doesn't create a new scope
    var myName = 'Klay'; // name is still in the global scope
}

console.log(myName); // logs 'Klay'
```


## Keywords let, var and const
 
ECMAScript 6 introduced the `let` and `const` keywords. These keywords can be used in place of the `var` keyword.
 
Contrary to the `var` keyword, the `let` and `const` keywords support the declaration of          *local scope inside block statements*.
 
```javascript
if (true) {
    // this 'if' conditional block doesn't create a scope
    
    // name is in the global scope because of the 'var' keyword
    var myName = 'Klay';
    // likes is in the local scope because of the 'let' keyword
    let likes = 'Coding';
    // skills is in the local scope because of the 'const' keyword
    const skills = 'JavaScript and PHP';
}

console.log(myName); // logs 'Klay'
console.log(likes); // Uncaught ReferenceError: likes is not defined
console.log(skills); // Uncaught ReferenceError: skills is not defined

```
 
>  Global scope lives as long as your application lives. Local Scope lives as long as your         functions are called and executed.
 
 
#  Functions
Generally speaking, a function is a "subprogram" that can be *called* by code external (or internal in the case of recursion) to the function. Like the program itself, a function is composed of a sequence of statements called the *function body*. Values can be *passed* to a function, and the function will *return* a value.

Laymans Terms

A function is a block of code designed to perform a task.

Functions are like recipes. They accept data ( Parameters ) , perform actions on that data (Statements ran within the function), and return a result. The beauty of functions is that they allow us to write a block of code once, then we can reuse it over and over without rewriting the same code ( used when* called *internally* *or* *externally*)*.


Lets take a look at a Function:

```javascript
let calculatorIsOn = false;

//  We created a function named pressPowerButton.
//  const pressPowerButton creates a variable with a given name written in camelCase  
// The variable is then set equal = to a set of parentheses followed by an arrow token () =>, 
// indicating the variable stores a function. This syntax is known as arrow function syntax. 

const pressPowerButton = () => {

 // In between {} is the function body, or the JavaScript statements that 
// define the function. In JavaScript, any code between curly 
 //braces is also known as a block. 

  if (calculatorIsOn) {
    console.log('Calculator turning off.');
    calculatorIsOn = false;
  } else {
    console.log('Calculator turning on.');
    calculatorIsOn = true;
  }
  
 }; // This is followed by a semi-colon;. 


 /* On the last few lines, we call or invoke the function by writing its name followed by a        semi-colon pressPowerButton();  This executes the function, running all code within the function body. */

pressPowerButton();
// Output: Calculator turning on.

pressPowerButton();
// Output: Calculator turning off.
```


## Parameters

*Default function* parameters allow formal parameters to be* initialized *with default values if no value or undefined is *passed*. For more on default paremeters click [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters)

*The Rest *parameter syntax allows to represent an indefinite number of arguments as an array. For more details click [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters)

### Functions and Parameters

```javascript
//inputNumber represents the parameter  
const multiplyByThirteen = (inputNumber) => {
   
  console.log(inputNumber * 13);
};

/* We can set as many parameters as we'd like by adding them when we declare the function,           separated by commas, like this: */
const multiplyByaPairOfNumbers = (num1, num2) => {
        console.log(num1 * num2);
}

/* 9 represents the argument. Arguments are provided when you call a function and parameters       receive arguments as their value. When we set the value 9 as the argument we pass a value to the function. */
multiplyByThirteen(9);
// Output: 117

/* In this case this function recieves two arguments. We are passing 1 and 2 into the function,     num1 will recieve the first argument, whereas num2 will recieve the second argument. */
multiplyByaPairOfNumbers(1, 2);
```


## Function Declarations

Functions in JavaScript are generally declared as either a *function declaration* or a *function expression*.

A f*unction declaration* is a function that is bound to an identifier or name:
```javascript
function square (number) {
  return number * number; 
}

console.log(square(5));
// Output: 25.
```

A *function expression* is similar to *function declaration*, with the exception that *identifier can be omitted*, *creating an anonymous function*. Function expressions are often stored in a variable. You can identify a function expression by the absence of a function name immediately trailing the function keyword.

```javascript
const square = function (number) {
  return number * number;
};

console.log(square(5));
// Output: 25.
```

*Arrow function* syntax is a shorter syntax for a *function expression*. You can identify arrow functions through the use of parentheses and the arrow token () =>:

```javascript
const square = ( number ) => {
    return number * number;
 };
 
 console.log(square(5)); 
 // Output: 25
   
     
```

>  Please note that function expressions require a semi-colon at the end of them.

With Arrow functions we can declare a function using a technique called the *concise body, *which is the most condensed form of a function.  As long as functions meet this criteria:

1. Functions that take a single parameter should not use parentheses. The code will still work, but it's better practice to omit the parentheses around single parameters. However, if a function takes zero or multiple parameters, parentheses are required. 

2. A function composed of a sole single-line block is automatically returned. The contents of the block should immediately follow the arrow => and the return keyword can be removed. This is referred to as *implicit return.*

3. A function composed of a sole single-line block does not need brackets.


Let's *refactor* the code above using the concise body protocol: 

```javascript
// The parentheses around number have been removed, since it is a single parameter.
// The return keyword has been removed since the function consists of a single-line block.
// The {} have been removed, again, since the function consists of a single-line block.

const square = number => number * number; 

 console.log(square(5)); 
 // Output: 25

```

> This is the basics of functions, we will get into the weird parts of javascript in more depth when we discuss closures, this keyword, and the arguments object

# Arrays

An array is a special variable, which can hold more than one value or *element* at a time.

Arrays are JavaScript's way of making lists. These lists can store any data types (including strings, numbers, and booleans) and they are ordered, meaning each item has a numbered position.


### Declaring an Array
```javascript
//Array Literal method, most easiest and common way of creating an array. 
let newYearsResolution = []; //Empty Array

//You can initialize the array when you declare it.
//You can place elements of any data type in an array, including other arrays. 
let newYearsResolution  = [ "Leave TSA", "Graduate", "Work in tech"]; // Array with 3 elements

//Creating an array with the new keyword. Or using the constructor method.                       //(An array is an object.)
let newYearsResolution = new Array(); //Empty Array
let newYearsResolution = new Array("Leave TSA", "Graduate", "Work in tech"); // Array of 3 element


//You can also place elements in the array by referencing an index you want 
newYearsResolution[3] = "Get in shape"; 
// This will add this element into the end of the array, making it four elements in length

console.log(newYearsResolution); 
//Output: [Leave TSA, Graduate, Work in tech, Get in shape] 
```

### Accessing Array Elements

Each item in an array has a numbered position. We can access individual items using their numbers, just like we would in an ordinary list.

Something important to note is that JavaScript starts counting from 0 rather than 1, so the first item in an array will be at position 0. This is because JavaScript is *zero-indexed*.

We can select the first item in an array like this:
```javascript
let newYearsResolutions = ['Rappel into a cave', 'Take a falconry class', 'Learn to juggle'];

console.log(newYearsResolutions[0]);
// Output: 'Rappel into a cave'
```

You can also access individual characters in a string. For instance, you can write:
```javascript
let hello = 'Hello World';
console.log(hello[6]);
// Output: W
```

JavaScript also has properties and methods that make arrays an even more powerful tool to use. Properties that allow you to determine the size of the array (.length), and methods that allow you to add, subtract, and even sort the array. For more info go here for [reference.](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array#Methods)


# Loops
Loops offer a quick and easy way to do something repeatedly. It will allow you to run a block of code over and over.

### For statement

A `for` loop repeats until a specified condition evaluates to false. The JavaScript `for` loop is similar to the Java and C for loop. A for statement looks as follows:

```javascript
for (statement 1 - Initial Expression; statement 2 - condition; statement 3- increment expression {
    code block to be executed
}

//Statement 1 is executed before the loop (the code block) starts.
/* The initializing expression initialExpression, if any, is executed.                              This expression usually initializes one or more loop counters, but the syntax allows an           expression of any degree of complexity. This expression can also declare variables.               initializerExpression can also be known as the iterator value*/

//Statement 2 defines the condition for running the loop (the code block).
/* The condition expression is evaluated. If the value of condition is true, the loop statements   execute. If the value of condition is false, the for loop terminates. If the condition expression is omitted entirely, the condition is assumed to be true. */

//Statement 3 is executed each time after the loop (the code block) has been executed.
//If present, the update expression incrementExpression is executed. Once incremented the second
//step of checking statement is repeated

```


### For....In Loop

The JavaScript `for/in` statement loops through the properties of an object:

```javascript
/*The for...in statement iterates a specified variable over all the enumerable properties of an    object. For each distinct property, JavaScript executes the specified statements.*/

var person = {fname:"John", lname:"Doe", age:25}; 

var text = "";
var x;

// A for... in statement looks as follows: */
for (x in person) {
    text += person[x];
}
```


### For...of
The for...of statement creates a loop *iterating over iterable objects (including Array, Map, Set, String, TypedArray, arguments object and so on)*, invoking a custom iteration hook with statements to be executed for the value of each distinct property.

```javascript
let iterable = [10, 20, 30];

for (let value of iterable) {
  value += 1;
  console.log(value);
}
```


### While
A while statement executes its statements as long as a specified condition evaluates to true. A while statement looks as follows:

```javascript
var n = 0;
var x = 0;
while (n < 3) {
  n++;
  x += n;
}


//With each iteration, the loop increments n and adds that value to x. Therefore, x and n take on the following values:

// After the first pass: n = 1 and x = 1
// After the second pass: n = 2 and x = 3
// After the third pass: n = 3 and x = 6

//After completing the third pass, the condition n < 3 is no longer true, so the loop terminates.
```
### 
### 
### Do/While
The do/while loop is a variant of the while loop. This loop will execute the code block once, before checking if the condition is true, then it will repeat the loop as long as the condition is true.

```javascript
var i = 0;
do {
  i += 1;
  console.log(i);
} while (i < 5);

/* statement in the code block will execute once before the condition is checked. To execute       multiple statements, use a block statement ({ ... }) to group those statements. If condition is  true, the statement executes again. At the end of every execution, the condition is checked. When the condition is false, execution stops and control passes to the statement following do...while.*/



```

> What kind of loop should I use? If you know how the number of times you need to run a block of code, then the for loop is your best bet. Otherwise, if the number is unknown then your best bet is a while loop. 


## Iterator methods

An object is an *iterator* when it knows how to *access items from a collection one at a time*, while keeping track of its current position within that sequence.* In JavaScript an iterator is an object that provides a next() method *which *returns* the next item in the sequence. This method returns an object with two properties: done and value.


## .forEach()

 Aptly named, the `.forEach()` method will execute the same code on each element of an array.  For more detail on this method go [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach).

```javascript

//1. first line is an array of grocery items.
let groceries = ['whole wheat flour', 'brown sugar', 'salt', 'cranberries', 'walnuts']; 


//2. groceries.forEach calls the .forEach() method on the groceries array.
/* 3. (function(groceryItem) { creates a function that takes a single parameter, groceryItem and    opens the block of code for that function. Because .forEach() is an iterator method, every       element in the groceries array will be passed to this function as an argument in place of groceryItem. Syntactically, the name of the parameter does not matter. However, it is a best practice to give parameters descriptive names so that other developers who read your code can easily understand what it does. */

groceries.forEach(function(groceryItem) {

/* 4. console.log(' - ' + groceryItem); is the code we wish to execute upon each element in the     array. Logging the item to the console with a - in front of it makes the elements look like a     list as they're printed out. 
    console.log(' - ' + groceryItem);

}); // 5. }); closes the function code block and .forEach() method in that order.


//We can simplify this code using the arrow function
groceries.forEach(groceryItem => console.log(' - ' + groceryItem));

//Both of these examples execute precisely the same process.

```


There are three important things to know about the `.forEach()` method.

1. It is an* array *method. *It must be called upon an array*.
1. Any changes to the* iterated array* value ***won't*** be updated in the *original array*.
1. The return value is undefined.



## .Map()

The `map()` method creates *a new array with the results* of calling a function for every array element. The `map()` method calls the provided function once for each element in an array, in order.   For more detail on this method go [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map).


```javascript
let numbers = [1, 2, 3, 4, 5]; //1. The first line is an array of numbers.


/* 2. let bigNumbers = numbers.map creates a new array,  bigNumbers, in which the returned values of the .map() method will be saved and calls the .map()  method on the numbers array. 
/* 3. (function(number) { creates a function that takes a single parameter, number, and opens the  block of code for that function.
let bigNumbers = numbers.map(function(number){ //Steps 2 and 3
 
 /* 4. return number * 10; is the code we wish to execute upon each element in the array. This will save each value from the numbers array, multiplied by 10, to the bigNumbers array.
 return number * 10; //Step 4
}); // step 5.  }); closes the function code block and .map() method in that order.



//Simplified arrowfunction version
let bigNumbers = numbers.map(number => number * 10);


```

> The syntax for` .map()` is almost the same as the syntax for `.forEach()`, with one important change. Notice that directly before the function call, the code reads,
>  `let bigNumbers =` This is because` .map()` *returns a new array with elements that have been modified by the code in its block*. `bigNumbers*` is the new array in which the method will save the values.*



## *.*filter()

`.filter()` returns certain elements from the original array that evaluate to truthy based on conditions written in the block of the method. For more detail on this method go [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter).

```javascript
let words = ['chair', 'music', 'pillow', 'brick', 'pen', 'door']; //Array is created.

 /* 2. let shortWords = declares a new array that    will contain the returned elements of the .filter() method. */
/* 3. words.filter(function(word) { calls the .filter() method on the words array and creates a     function that will take a single parameter, word. Each element in the words array will be passed to this function as an argument. */
/* 4. return word.length < 6; is the condition to filter for all elements in the words array that have fewer than 6 characters will be added to the shortWords array.*/
/* 5. }); closes the code block and .filter() method in that order. */

let shortWords = words.filter(function(word) { // Step 2 and 3
  return word.length < 6; // Step 4 
}); // Step 5

//Concise Arrow Function version.
let shortWords = words.filter(word => word.length < 6);


```


1. The filter() method creates an array filled with all array elements that pass a test (provided as a function).  
1. filter() does not execute the function for array elements without values. 
1. filter() does not change the original array.

### Iteration Documentation
There are many additional built-in array methods, a complete list of which is on the [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array).

1. A short definition
1. A block with the correct syntax for using the method
1. A list of parameters the method accepts or requires
1. The return value of the function
1. An extended description
1. Examples of the method's use
1. Polyfill, Specifications, Browser Compatibility

A list of iterator methods can be found [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array#Iteration_methods).



# Control Flow

The control flow is the order in which the computer executes statements in a script.

Code is run in order from the first line in the file to the last line, *unless the computer runs across the (extremely frequent) structures that change the control flow*, such as *conditionals and loops*. 

*Control flow statements* enable JavaScript programs* to make decisions *by executing code based on a condition. ***If a given condition is true**, we execute one block of code. **If the statement is false**, we execute another block of code*. 

For instance, if we were making a game in which the user had to choose which door to enter, we'd need a way for the program to know what to do once the user was in the next room.

## **Conditional Statements**


## if/else statements

The `if/else` statement executes a block of code if a specified condition is true. If the condition is false, another block of code can be executed.

The `if/else` statement is a part of JavaScript's "Conditional" Statements, which are used to perform different actions based on different conditions.

`if/else` statements are how programs can process yes/no questions programmatically.

```javascript
/* 1. Lines of code between curly braces are called blocks. if/else statements have two code      blocks. If the variable needsCoffee is true, the program will run the first block of code. Otherwise, it will run the other block of code. */

/* 2. needsCoffee is the condition we are checking inside the if's parentheses. Since it is equal to true, our program will run the code between the first opening curly brace { (line 2) and the first closing curly brace } (line 4). It will ignore the else { ... } part. In this case, we'd see Finding coffee log to the console. */

// 3. If needsCoffee were false, only the console.log() statement in the else block would be     // execute 

let needsCoffee = true;
if (needsCoffee === true) { // 1 and 2
    console.log('Finding coffee');
} else { //3
    console.log('Keep on keeping on!');
}

/* if/else if/ else */
/* 1. We created a variable named stopLight that is assigned to the string green. */

/*2. Then, there's an if/else statement with multiple conditions, using else if. else if allows us to check multiple values of the stopLight variable and output different things based on its color.*/
/* 3. The block ends with the singular else we have seen before. The else is a catch-all for any   other situation. For instance, if the stopLight was blinking blue, the last else would catch it and return a default message.*/
let stopLight = 'green'; // 1.

if (stopLight === 'red') { //2
  console.log('Stop');
} else if (stopLight === 'yellow') { //2
  console.log('Slow down');
} else if (stopLight === 'green') { // 2
  console.log('Go!');
} else { // 3
  console.log('Caution, unknown!');
}





```



###   Note about true and false statements:

All *variables that have been created and set are truthy* (and will *evaluate* to true if  they are the condition of a control flow statement) unless they contain one of the seven values listed below:

1. false
1. 0 and -0
1. "" and '' (empty strings)
1. null
1. undefined
1. NaN (Not a Number)
1. document.all (something you will rarely encounter)

Operators that are essential in programming conditional statements that help the program make decisions are called *comparison operators*. You can find a full list [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators).
     
 A full in depth list of other types of operators such as, logical operators can be found [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#Logical_operators).
 


## [Switch Statements](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch)

The switch statement is used to perform different actions based on different condition.

The switch statement evaluates an expression, matching the expression's value to a case clause, and executes statements associated with that case, as well as statements in cases that follow the matching case.

It's typically used in place of the else if statement *when there is alot of code* to read and write, because of readability.  It's concise and readable. 

```javascript
/* 1. The switch keyword initiates the statement and is followed by ( ... ), which contains the   condition that each case will compare to. In the example, the condition is groceryItem. */

/* 2. Inside the block, { ... }, there are cases. case is like the else if part of an             if/else if/else statement. The word following the first case is 'tomato'. If groceryItem equalled 'tomato', that case's console.log() would run. */

/* 3. groceryItem equals 'papaya', so the first and second case statements are skipped. The third case runs since the case is 'papaya', which matches groceryItem's value. This particular program will log Papayas are $1.29. */

/* 4. Then the program stops with the break keyword. This keyword will prevent the switch         statement from executing any more of its code. Without adding break at the end of each case, the program will execute the code for all matching cases and the default code as well. This behavior is different from if/else conditional statements which execute only one block of code.  */

/* 5. At the end of each switch statement, there is a default condition. If none of the cases are true, then this code will run. */


let groceryItem = 'papaya';

switch (groceryItem) { //1
  //2 - 4
  case 'tomato':
    console.log('Tomatoes are $0.49');
    break;
  case 'lime':
    console.log('Limes are $1.49');
    break;
  case 'papaya':
    console.log('Papayas are $1.29'); // Program will log this statment
    break;
  default: // 5
    console.log('Invalid item');
    break;
}
```


## Ternary operator

Ternary operator is a concise version of the if/else statement. 


The conditional (ternary) operator is the only JavaScript operator that takes three operands. This operator is frequently used as a shortcut for the if statement.


```javascript
let isNightTime = true;
//This statement is equivalent to the if/else statement below. This type of statement is called a ternary operator. 
isNightTime ? console.log('Turn on the lights!') : console.log('Turn off the lights!');

//  1. isNightTime ? — the conditional statement followed by a question mark. This checks if isNightTime is truthy.
// 2. console.log ('Turn on the lights!') — this code will be executed if the condition is truthy.
// 3. : — a colon separates the two different blocks of code that can be executed.
// 4. console.log('Turn off the lights!'); — this code will be executed if the condition is falsy

if (isNightTime) {
  console.log('Turn on the lights!');
} else {
  console.log('Turn off the lights!');
}




```



# JavaScript Objects

JavaScript is designed on a* simple object-based paradigm*. An ***object*** is a *collection of properties*, and a **property** is an *association *between a name* (or **key**) and a **value***. A property's value can be a function, in which case the property is known as a ***method***. In addition to objects that are predefined in the browser, you can define your own objects. 

JavaScript *objects* are *containers that can store data and functions*. The data we store in an object is not ordered — we can only access it by calling its associated *key*.



```javascript
//1. let restaurant creates a variable named restaurant that stores the object.  2. Then We create the object between curly braces: {}. */                                               
let restaurant  = { 
// 3. name, seatingCapacity, hasDineInSpecial, and entrees are all keys. 
// 4. We separate each key from its corresponding value by a colon (:).
// 5. The value is to the right of the colon. For example, seatingCapacity's value is 120.
// 6. Every key-value pair is separated by a comma ,.
  name: 'Italian Bistro',
  seatingCapacity: 120,
  hasDineInSpecial: true,
  entrees: ['Penne alla Bolognese', 'Chicken Cacciatore', 'Linguine Pesto']
};
```


## Accessing Object Properties 

Once we have data in an Object, we need a way to access the* properties *or *key values* in the object, there are several ways to do this. 

### **Dot Notation**

 The most common way to access a key's value is to use *dot notation*.

```javascript
// Look at how the entrees property is accessed from the restaurant object in last line of the example below:
let restaurant = {
  name: 'Italian Bistro',
  seatingCapacity: 120,
  hasDineInSpecial: true,
  entrees: ['Penne alla Bolognese', 'Chicken Cacciatore', 'Linguine pesto']
};
// To access the properties within an object, we connect the object variable name to the key name 
console.log(restaurant.entrees);
```


## **Bracket Notation**

Another way to access a key's value is with* bracket notation*.

```javascript
// Look at how the entrees property is accessed from the restaurant object in last line of the example below:
let restaurant = {
  name: 'Italian Bistro',
  seatingCapacity: 120,
  hasDineInSpecial: true,
  entrees: ['Penne alla Bolognese', 'Chicken Cacciatore', 'Linguine pesto']
};
//Just like with dot notation, we can use opening ([) and closing (]) brackets to access a key instead of the period
// One advantage that bracket notation has over dot notation is that you can use variables inside the brackets to select    the keys of an object.
console.log(restaurant['entrees']);
```






