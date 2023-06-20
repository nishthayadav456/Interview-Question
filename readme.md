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

### 3-Null- null is an assignment value. It can be assigned to a variable as a representation of no value:

