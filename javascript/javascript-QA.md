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
    - A Var variable can be declared after it has been used.
    - Variables defined with let and const are hoisted to the top of the block, but not initialized.
    - Using a let variable before it is declared will result in a ReferenceError.
    - Using a const variable before it is declared, is a syntax errror, so the code will simply not run.
    - JavaScript only hoists declarations, not initializations.
    - To avoid bugs, always declare all variables at the beginning of every scope.
    - JavaScript in strict mode does not allow variables to be used if they are not declared.

    ```
        var x = 5;  // Initialize x

        elem = document.getElementById("demo");      // Find an element 
        elem.innerHTML = "x is " + x + " and y is " + y;  // O/p x is 5 and y is undefined

        var y = 7;  // Initialize y

    ```

5. What is the closure in JavaScript?
    - A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). In other words, a closure gives you access to an outer function’s scope from an inner function.
    - Closure is useful in hiding implementation detail in JavaScript. In other words, it can be useful to create private variables or functions.

    ```
        function OuterFunction() {

        var outerVariable = 100;

        function InnerFunction() {
        alert(outerVariable);
        }

        return InnerFunction;
        }
        var innerFunc = OuterFunction();

        innerFunc(); // 100

        In the above example, return InnerFunction; returns InnerFunction from OuterFunction when you call OuterFunction(). A variable innerFunc reference the InnerFunction() only, not the OuterFunction(). So now, when you call innerFunc(), it can still access outerVariable which is declared in OuterFunction(). This is called Closure.

    ```

6. Var, Let, and Const – What's the Difference?
    - One of the features that came with ES6 is the addition of let and const, these can be used for variable declaration. 

    - Var
        var declarations are globally scoped or function/locally scoped.
        
    - Let
        Block scoped, A block is a chunk of code bounded by {}. 
        let can be updated but not re-declared.
        Just like  var, let declarations are hoisted to the top. Unlike var which is initialized as undefined, the let keyword is not initialized. So if you try to use a let variable before declaration, you'll get a Reference Error.
    
    - Const 
        Block scoped.
        const cannot be updated.

7. What is event bubling?
    - When an event happens on an element, it first runs the handlers on it, then on its parent, then all the way up on other ancestors.
    - event.target: The most deeply nested element that caused the event is called a target element, accessible as event.target.
    - Stopping bubbling: event.stopPropagation() stops the move upwards, but on the current element all other handlers will run.

    ```
        <form onclick="alert('form')">FORM
        <div onclick="alert('div')">DIV
        <p onclick="alert('p')">P</p>
        </div>
        </form>

        A click on the inner <p> first runs onclick:

        On that <p>.
        Then on the outer <div>.
        Then on the outer <form>.
        And so on upwards till the document object
        So if we click on <p>, then we’ll see 3 alerts: p → div → form.

    ```

8. What is Capturing? 
    - Event capturing is one of two ways to do event propagation in the HTML DOM. In event capturing, an event propagates from the outermost element to the target element. It is the opposite of event bubbling, where events propagate outwards from the target to the outer elements.
    - The standard DOM Events describes 3 phases of event propagation:
        1. Capturing phase – the event goes down to the element.
        2. Target phase – the event reached the target element.
        3. Bubbling phase – the event bubbles up from the element.
    - For event capturing, we set the handler capture option to true: elem.addEventListener(event, handler, true). By default, it is set to bubbling: false.

9. What is Web Worker? 
    - Web Workers are a simple means for web content to run scripts in background threads. The worker thread can perform tasks without interfering with the user interface.
    - Web workers let you do any time-consuming job in the background. The process is simple:
        1. You create a web worker.
        2. You tell the web worker what to do. The code that a worker runs is always stored in a separate JavaScript file
        3. You start the web worker.
        4. When the web worker is done, it tells you, and your code goes from there. (For example, show the results on your page.)

10. What is Service Worker? 
    - A service worker is a script that your browser runs in the background, separate from a web page, opening the door to features that don't need a web page or user interaction. Today, they already include features like push notifications and background sync.

11. Difference between Web Worker and Service Workers? 
    - Web workers are general-purpose scripts that enable us to offload processor-intensive work from the main thread.
    - Service workers are a proxy between the browser and the network. By intercepting requests made by the document, service workers can redirect requests to a cache, enabling offline access.

    ```
                       | Web Workers  | Service Workers  |
        |--------------|--------------|------------------|
        | Instances    | Many per tab | One for all tabs |
        | Lifespan     | Same as tab  | Independent      |
        | Intended use | Parallelism  | Offline support  |


    ```

12. Types of javascript function
    - Basic function
        ```
        function validFunctionName(parameter) {
            return statement;
        }
        ```
    - Anonymous function
        A Function Expressions defines a named or anonymous function. An anonymous function is a function that has no name.
        ```
            var fullName = function(firstName, lastName) {
                return `${firstName} ${lastName}`;
            }
            fullName("Jamal", "Uddin"); // Jamal Uddin
        ```
    - Arrow Function
        An Arrow Function Expression is a shorter syntax for writing function expressions. Arrow functions do not create their own value.
        ```
            const double = (value) => {
                return value * 2
            }
            double(10); // 20
        ```

13. Javascript: call(), apply() and bind()
    - Call invokes the function and allows you to pass in arguments one by one.
    - Apply invokes the function and allows you to pass in arguments as an array.
    - Bind returns a new function, allowing you to pass in a this array and any number of arguments.

    ```
        1. Call

        var person1 = {firstName: 'Jon', lastName: 'Kuperman'};
        var person2 = {firstName: 'Kelly', lastName: 'King'};

        function say(greeting) {
            console.log(greeting + ' ' + this.firstName + ' ' + this.lastName);
        }

        say.call(person1, 'Hello'); // Hello Jon Kuperman
        say.call(person2, 'Hello'); // Hello Kelly King

        2. Apply

        var person1 = {firstName: 'Jon', lastName: 'Kuperman'};
        var person2 = {firstName: 'Kelly', lastName: 'King'};

        function say(greeting) {
        console.log(greeting + ' ' + this.firstName + ' ' + this.lastName);
        }

        say.apply(person1, ['Hello']); // Hello Jon Kuperman
        say.apply(person2, ['Hello']); // Hello Kelly King
        
        3. Bind

        var person1 = {firstName: 'Jon', lastName: 'Kuperman'};
        var person2 = {firstName: 'Kelly', lastName: 'King'};

        function say() {
        console.log('Hello ' + this.firstName + ' ' + this.lastName);
        }

        var sayHelloJon = say.bind(person1);
        var sayHelloKelly = say.bind(person2);

        sayHelloJon(); // Hello Jon Kuperman
        sayHelloKelly(); // Hello Kelly King
    ```