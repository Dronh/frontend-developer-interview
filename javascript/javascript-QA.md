# Javascript quations and answers


1. What is Javascript
    - JavaScript is a text-based programming language used both on the client-side and server-side that allows you to make web pages interactive. Where HTML and CSS are languages that give structure and style to web pages, JavaScript gives web pages interactive elements that engage a user.

2. What is Type in jS
    - a type helps group similar values on which common operations can be performed.
    - JavaScript has seven built-in types: null , undefined , boolean , number , string , object , and symbol.

3. Kinds of Loops in JS?
    - for - loops through a block of code a number of times
    - for/in - loops through the properties of an object
    - for/of - loops through the values of an iterable object
    - while - loops through a block of code while a specified condition is true
    - do/while - also loops through a block of code while a specified condition is true

4. what is Hoisting in JS?
    - Hoisting is JavaScript's default behavior of moving all declarations to the top of the current scope (to the top of the current script or the current function).
    ```
    - A Var variable can be declared after it has been used.
    - Variables defined with let and const are hoisted to the top of the block, but not initialized.
    - Using a let variable before it is declared will result in a ReferenceError.
    - Using a const variable before it is declared, is a syntax errror, so the code will simply not run.
    - JavaScript only hoists declarations, not initializations.
    - To avoid bugs, always declare all variables at the beginning of every scope.
    - JavaScript in strict mode does not allow variables to be used if they are not declared.

    var x = 5;  // Initialize x

    elem = document.getElementById("demo");      // Find an element 
    elem.innerHTML = "x is " + x + " and y is " + y;  // O/p x is 5 and y is undefined

    var y = 7;  // Initialize y

    ```
