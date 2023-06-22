# Q1.Difference between “ == “ and “ === “ operators.
### Ans- '=='
### Double equals used as Type converting the conversion.
### Double equals first convert the operands into the same type and then compare i.e comparison would perform once both the operands are of the same type. This is also known as type coercion comparison.
### '==='
### Triple equals used as Strict conversion without performing any conversion in operands.
### Triple equals do not perform any type of conversion before comparison and return true only if type and value of both operands are exactly the same.
### Example-
### let a="Mayank";
### let b="vipul";
### console.log(a==b);
### console.log(a===b);

# Q2.What are the differences between var, let and const?
### var-
 1-Redeclare and Reinitialized.\
 2-Global scope and function scope.\
 3-Hoisting\
 4-Used before introduce ES6.
### let-
1-Not Redeclare and Reinitialized.\
2-No Hoisting.\
3-TDZ(temporal dead zone)\
4-Block scope, global scope.\
5-Introduce in ES6.
### const-
1-Not Redeclare and Reinitialized.\
2-No Hoisting.\
3-Block scope, global scope.\
4-TDZ(temporal dead zone)\
5-Introduce in ES6.
### var x=10;
 ### var x=20; (Redeclare)
 #### x=10;  (Reinitialized)

# Q3.What is Hoisting?
### Hoisting is the JS mechanism where var and function decleration are moved to the top of their scope before code execution.
### Hoisting is a concept that enables us to extract values of variables and functions even before initializing/assigning value without getting errors and this happens during the 1st phase (memory creation phase) of the Execution Context.
### 1-function Hoisting-Hoisted functions can be used before their declaration. 
### 2-variable Hoisting-Variables are not hoisted as they cannot be used before their declaration. 

# Q4.What is a Temporal Dead Zone?
### - When trying to access a variable before it's decleration with let and const keyword.
### - Introduce to improve the code quality by detecting and preventing to use variable.
### -Temporal Dead Zone starts when the code execution enters the block which contains the let or const declaration and continues until the declaration has executed.

# Q5.What is meant by first class functions?
### Assign a function to a variable is known as first class function.
### function which gets treated as an variable .It can be passed as an argument to other functions ,can be assigned as a value to a variable.
 ## Example-
const Too=function(){   
    console.log("hello world")  
}  
Too();

# Q6.What are pure functions?
### A pure function in javascript is a function that returns the same result if the same arguments (input) are passed in the function.
### Pure Function is a function (a block of code ) that always returns the same result if the samenarguments are passed. It does not depend on any state, or data change during a program’sexecution rather it only depends on its input arguments.

# DAY 2-


# Q7. What is Execution Context?

    - This is for Synchronous JavaScript
    1. Global Execution Context
    2. Function Execution context
    3. Memory Allocation
    4. Code Execution 
    5. Call Stack
    - Asynchronous JavaScript
    1. Event Loop
    2. Callback queue
    3. Call Stack
### The browser's JavaScript engine then creates a special environment to handle the transformation and execution of this JavaScript code. This environment is known as the Execution Context.The Execution Context contains the code that's currently running, and everything that aids in its execution.
## There are two phases of JavaScript execution context-
### 1-Creation phase: In this phase, the JavaScript engine creates the execution context and sets up the script's environment. It determines the values of variables and functions and sets up the scope chain for the execution context.
### 2-Execution phase: In this phase, the JavaScript engine executes the code in the execution context. It processes any statements or expressions in the script and evaluates any function calls.
# Q8- What is an event loop and call stack?
## Event loop-
###  The event loop is a constantly running process that monitors both the callback queue and thecall stack. All the web apis functions like setTimeout, setInterval, fetch calls etc. will not be directly executed inside the execution context, firstly they will be moved to callback queue andthen the moment call stack gets empty these functions will be pushed to call stack from callback queue by event loop.
## Call stack-
### A call stack is a mechanism for an interpreter (like the JavaScript interpreter in a web browser)to keep track of its place in a script that calls multiple functions — what function is currently being run and what functions are called from within that function, etc. or we can say that it stores global execution context and function execution context.
# Q9-What is the spread operator?
### The JavaScript spread operator (...) allows us to destructure the non-primitive data types like arrays and objects to access the elements individually.
### - Spread operator allows us to destructure the non-primitive datatype like object and array to access elemnets individually.
### - The spread operator is a feature in JavaScript that allows an iterable (such as an array or a string) to be expanded into individual elements. The spread operator is denoted by three dots (...).
### - The JavaScript spread operator ( ... ) allows us to quickly copy all or part of an existing array or object into another array or object.
## Example-
const arr = [2,3,4,5,6,7,8,9];    
 for(let i = 0 ; i < arr.length ; i++){      
         console.log(arr[i]);    
 }  
    
    console.log(...arr);    
    console.log(arr);   
    const arr2 = [...arr, ...arr1]  
    console.log(arr2); 
     
    
 ## Spread Operator - Function

const arr1 = [1,11, 12, 10]       

function Sum(a, b, c){      
     console.log(a, b, c);       
     return a + b + c;         
 }

 console.log(Sum(...arr1));   

 ##  Spread Operator - Object

 const Obj1 = {       
     name : "Nishtha",     
     Age : 22               
      }

 const Obj2 = {     
    Course : "MERN",         
     ...Obj1     
 }

 console.log(Obj1);    
 console.log(Obj2);

# Q10-What is the use of setTimeout?
### The setTimeout() is a method inside the window object, it calls the specified function or evaluates a JavaScript expression provided as a string after a given time period for only once.
### We all have used alarms or reminders several times, this setTimeout() method also has the same purpose in web applications. We use this to delay some kind of executions.
## Example-

function Display(){
let time = new Date();

let hr = time.toLocaleTimeString();

console.log(hr);  
 }

 setInterval(() => {  
     Display();  
}, 2000); 

 setTimeout(() => { 
    
 }, 1000);

 Display();

 # Q11-What is setInterval?
 ### The setInterval() method calls a function at specified intervals (in milliseconds).
 ### The setInterval() method continues calling the function until clearInterval() is called, or the window is closed.

 # Q12-What are callbacks?
  - A function that can pass inside another function as an argument.
- A callback is a function that passed as an argument to another function as an argument which is then invoked inside the outer function to complete an action.

## Example-    
function greet(name, func){  
 console.log(`Hi ${name}`); 

console.log(func());  
 }   

 function Sum(){   
     console.log("Hey....");   
 }   
 greet('EA23', Sum)   
 # Q13- What is callback hell?
 ### Callback Hell is a pattern with multiple nested callbacks which makes code hard to read and debug when dealing with asynchronous logic. The callback hell looks like a pyramid structure.
 ## Example-  
 function divide(x,y){  
    return x/y  
}  

function multiply(x,y){  
    return x*y  
}  

function add(x,y){  
    return x+y  
}  

function calculate(callBack, x, y){  
    return callBack(x,y)  
}  

console.log(calculate(divide, 10, 5))    
console.log(calculate(multiply, 10, 5))  
console.log(calculate(add,10,5)) 

# Q14-Difference between undefined vs not defined vs NaN?
### 1-undefined-undefined means a variable has been declared but has not yet been assigned a value.
### 2- Not Defined-The value of "not defined" is similar to "undefined", in that it indicates that a variable does not exist. 

### 3-Null- null is an assignment value. It can be assigned to a variable as a representation of no value.
 
 # DAY 3-
# Q15-What are promises and why do we need them?
### Promise are use to handle async operation in JS. easy to handle callback hell, also use to handle the error.
### Promises are used to handle asynchronous operations in JavaScript. They are easy to manage when dealing with multiple asynchronous operations where callbacks can create callback hell leading to unmanageable code.
### Multiple callback functions would create callback hell that leads to unmanageable code. Also it is not easy for any user to handle multiple callbacks at the same time.
## A Promise is in one of these states:
### pending- initial state, neither fulfilled nor rejected.
### fulfilled- meaning that the operation was completed successfully.
### Rejected- meaning that the operation failed.
 
 # Q16-What is promise chaining?
 ### The process of executing a sequence of asynchronous tasks one after another using promises is known as Promise chaining.
 ### It is  a technique to chain multiple asynchronous operation together using promises.
 ## Example-

 new Promise(function(resolve, reject) {   
setTimeout(() => resolve(1), 1000);    
}).then(function(result) {    
console.log(result); // 1    
return result * 2;    
}).then(function(result) {     
console.log(result); // 2    
return result * 3;     
}).then(function(result) {      
console.log(result); // 6      
return result * 4;      
})         

# Q17-What is the DOM?
### The Document Object Model (DOM) is the data representation of the objects that comprise the structure and content of a document on the web.
### The Document Object Model (DOM) is a programming interface for web documents. It represents the page so that programs can change the document structure, style, and content.The DOM represents the document as nodes and objects; that way, programming languages can interact with the page.

# Q18-What are closures? Give an example of closure.
### A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). In other words, a closure gives you access to an outer functions  scope from an inner function.
## Example-
function outerFunc() {  
var outerVar = 100;   
function innerFunc() {   
console.log(outerVar);   
}   
return innerFunc;   
}  
var value=outerFunc();  
value();  

# Q19-How many operators do we have in JS ?
##  1. Arithemic operator -
   Add(+), Sub(-), Multi(*), Div(/), Module (%), Expontial (**),   increment ++, decrement--    
##  2. Assignment Operator-
  Assign (=), Add Assign (+=), Sub Assign (-=), (*=), (/=), (%=)
## 3. Bitwise Operator-  
 Bitwise OR (|), Bitwise AND (&), Bitwise NOT (~), Left shift (<<), right shift(>>)
##  4. Comparision Operator-
 equal (==), strict equal (===), Not equal (!=), Strict Not equal     (!==), greate than, less than, greate than equal, less  than equal 
##   5. Logical Operator
       1. AND (&&)
       2. OR (||)
       3. Not (!)
## 6. Ternary Operator-
       1. (Condition) ? "Execute True Condition" : "Execute False Condition"
 ##  7. Type of Operator-
       1. return datatype

# Q20-What are objects in javascript?
### An object is an unordered collection of key-value pairs. Each key-value pair is called a property.
### The key of a property can be a string. And the value of a property can be any value, e.g., a string, a number, an array, and even a function.
-Non-premitive data type.

-store date in the form of Key-Value pair saparated by colon.
# Day 4-
# Q21-What are function constructors?
### A constructor is a special function that creates and initializes an object instance of a class. In JS, a constructor gets called when an object is created using the new keyword. 
- A function constructor is a way to create a object using a function as a blue print or template.
- It allow you to define a reusable structure for creating multiple object with similar properties and method.
## Example-
function User (name, age) {  
this.name = name;   
this.age = age;   
}   
var user1 = new User('shubhi', 25);   
var user2 = new User('Anjali', 27)  
  # Q22-Explain call(), apply() and, bind() methods. Give an example of call(), apply(), bind().
  ###  - These all three methods are used to invoke a function where we are supposed to pass an object as first argument and at the time of definition we don't have mention this object as a parameter and we can access the values of object by using this keyword in function definition.
- Call - The call method is used to invoked a function with a specific 'this' value, and arguments provide individuly.
- The call() method invokes a function in which first argument will be the object and rest of the arguments required by function will be provided as an individual arguments.
 - Apply - Apply is similar with call, but take argument as an array.
 -  The apply() method invokes a function in which first argument will be the object and rest of the arguments will be passed as an array of elements.
 - Bind - Bind is a function that helps you create another function that you can execute later with the new context of this that is provided.
- The bind() method returns a new function and this function will be having the reference of the object passed, now whenever you want to use this returned function in the code you can use it by passing rest of the arguments.
## Example-
     const Person1 = {   
     name: "EA23",   
     course : "MERN",  
     age: 24   
      }  

     function Display(greet, greet1){
     console.log(`${this.name} : ${this.age} : ${this.course} : ${greet} : ${greet1}`);
     }
     Display.call(Person, "Hi", "Good Evening...")  
    Display.call(Person1, "Call", "Good Evening...")   
    Display.apply(Person1, ["Apply", "Good Evening..."]);  
    let result = Display.bind(Person1, "Bind", "Good Evening...");   
     result();   
 # Q23-What is the purpose of async/await keywords?
 ### An async function is a function declared with the async keyword, and the await keyword is permitted within it. The async and await keywords enable asynchronous, promise-based behavior to be written in a cleaner style, avoiding the need promise chains.
     async function too() {

     let promise = new Promise((resolve, reject) => {
      setTimeout(() => resolve("done!"), 1000)
     });

     let result = await promise; // wait until the promise resolves 
      return result; 
     }

too();

 # Q24-Explain prototypes?
 ### Prototypes are the mechanism by which JavaScript objects inherit features from one another.Every object in JavaScript has a built-in property, which is called its prototype.The prototype is itself an object, so the prototype will have its own prototype, making what'scalled a prototype chain.The chain ends when we reach a prototype that has null for its own prototype.
 ## Example-
     function Student() {
    this.name = 'Ram';
    this.gender = 'M';
    }

    Student.prototype.age = 15;

     var studObj1 = new Student();
     console.log(studObj1.age); 

     var studObj2 = new Student();
     console.log (studObj2.age); 

 # Q25-What is prototype chain?
 ### Prototype chaining is used to build new types of objects based on existing ones. It is similar to inheritance in a class based language. The prototype on object instance is available through Object.getPrototypeOf(object) or proto property whereas prototype on constructors function is available through Object.prototype.
 ## Example-
 
    function Person() {
    this.name = 'Riya'
     }
     Person.prototype.age = 20;
    const person1 = new Person();

     console.log(person1.age); 
    Person.prototype = { age: 50 }
    const person3 = new Person();
    console.log(person3.age); 
    console.log(person1.age); 





