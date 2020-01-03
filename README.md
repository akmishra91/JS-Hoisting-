JS hoisting (from medium.com)

Javascript uses the concept of hoisting, which is a feature that moves declarations to the top of the scope (global or private).

Let us take a look at some simple example of how a normal program code runs when using functions with declarations.


let val = 15;   //variable is defined in the global scope.

function X() {
     console.log(val)
}
X();
 output : 15

 Let’s say we don’t declare a variable.

 function X() {
     console.log(val)
}
X();

output: Uncaught ReferenceError: val is not defined.

NB: It is thus important to always have declared variables in a program.

To further explain the behavior of hoisting, let us create a program where we write the functions before declaring the variables. Is that even possible?

function foo() {
     var g = val + 5 //here 'g' has been defined before printing to the console.
     console.log(g)
}
let val = 15;
foo();

(Javascript Engine) does during code execution is move the declarations to the top of the scope, loading them into memory. Once the declarations are in memory, it can then invoke functions and assign values to variables at runtime.
