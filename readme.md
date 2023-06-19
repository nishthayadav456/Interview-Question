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

const Too=function(){ \
    console.log("hello world")\
}\
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