# Functional-programming 
is the process of building software by composing : 
## 1-  Pure Functions: (important in fp, concurrency, testable code,predictable code,...)
typically there are three purpose of writing functions: 
### 1- mapping input to output
mappiong means we take inputs(arguments) => function => output(retrurn value)
f(x)= 2x  ===>  f(2)= 4 
### 2- procedures: a list of instructions that computer follows and call again and again
### 3- I/O : Network request, user input, drawing to the screen,...
 - Is a function that for the same input gives the same output. 
- Has no side effects.
So what makes a function pure? 
 ## * Given the same input is always gonna return the output then a pure function produces no side effects. so to have a pure function we do the following things: 
1- avoid shared state
Impure functions: 
-Any thing that relies on the current time is not a pure function.(it doesn't have the same result during a day)
-Random numbers: if you try to generate a random number inside of your function the function is not pure. (to make it pure you can generate the random number outside of the function and then pass it into the function).
- Any thing that depends on I/O (user input, disk access, network access)

2- Function Composition:
is the process of combining two/ or more functions in order to produce a new fuction or perform some computation. 

2- Avoiding Shared State :
(for example : all the response handlers shouldn't write to that state, the one comes last will always win so the solution is : giving the responsibility to just one function to access to that state)
a shared state is a variable, object or memory space that exists in a shared scope, or as a property of an object that passes between scopes.
shared scope can be:  1- a global scope 2- or closure scopes
** Usually in OOP, objects are shared between scopes by adding properties to other objects**
const x = {
  val: 2
};
const x1 = () => x.val += 1;
const x2 = () => x.val *= 2;
x1();
x2();
console.log(x.val); // 6
// This example is exactly equivalent to the above, except...
const y = {
  val: 2
};
const y1 = () => y.val += 1;
const y2 = () => y.val *= 2;
// ...the order of the function calls is reversed...
y2();
y1();
// ... which changes the resulting value:
console.log(y.val); // 5
* as we can see in the above example, in shared state situatioin the output of a function depends on the timing and the order of the function calls  while in pure function given the same input gives the same output.* This can simplify changes in our code and refactoring.
3- Avoiding Mutable Data: 


4- Avoiding side-effects
