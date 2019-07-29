---
layout: post
title:      "Hoist the sails! There be pirates in scope!"
date:       2019-07-28 09:55:51 -0400
permalink:  hoist_the_sails_there_be_pirates_in_scope
---


Javascript is unique, there are peculiar conventions for how variables and functions can be used as well as where and how different variables can be used when placed in places in your code. These ideas are called *scope* and *hoisting*.

**Scope**

When we talk about scope, we are refering to where a variable is declared and where it can be used. In Javascript, there are two types of scoe: *global* and *local*. If a variable is declared outside of all functions, it is a global variable and can be accessable anywhere, in the global . 
For example:
```
globalVar = "I'm global"
var newVar = "I'm also global"

function () {
    var newVar = "I'm local"
    //variables outside of this function (like globalVar) are also in scope inside this function
}

```
This is because global variables and variables declared with var do not support block scoping. However, variables declared with var do support functional scope, so they can't be accessed outside of the function they are declared in. Variables declared with let and const do. This means that declarations made with var can be accessed from outside of their initial scope, whereas declarations made with let and const are not. So we get an error when we do the following:
```
function newFunc(){
    var varVari = "I used var"
    let letVari = "I used let"
		const constVari = "I used const"
}
console.log(varVari)    //Uncaught Reference error: varVari is not defined
console.log(letVari)    //Uncaught Reference error: letVari is not defined
console.log(constVari)    //Uncaught Reference error: constVari is not defined
```
Because we are outside the function block and try to call both variables, we get an error because both variables are not defined in the global scope.

**Hoisting**

When we talk about hoisting, you can imagine our pirate ship *hoisting* their flag up their flagpole. In javascript things are hoisted/lifted to the top of it's scope, as if you wrote it first. Let's start with a simple example:
```
console.log(x)
var x = "Hello"
// => undefined
```
We get back undefined and not an error, the above code is equivalent to:
```
var x    //declare the variable
console.log(x)
x = "Hello"
```
This means that our variable was declared, but it wasn't assigned a value until after we console.log-ed it, so we get back undefined. The takeaway so far is that the variable declaration is hoisted, but it's value isn't assigned until the actual like where you declare it. Let's look at another example:
```
function sayHi() {
  console.log( "Hi " + name)
}
sayHi()
var name = "person"
```
We expect that we get back "Hi *undefined*", the above code is equivalent to:
```
function sayHi() {
  console.log("Hi " + name)
}
var name
sayHi()
name = "person"
```
Functions are also hoisted to the top, so we are able to call on the function before it is even declared. For example:
```
sayHi() //returns "Hi"
function sayHi(){
    console.log("Hi")
}
```
But if we declare the function this way, we get a different result:
```
sayHi  //returns *undefined*
var sayHi = function (){
   console.log("Hi")
}
```
Why is that? Well consider how we are calling the function. *sayHi* is now a variable and it's value is a anonymous function so it behaves like a *var* and not as a declared function like the previous example. This means that if we try to do this instead:
```
sayHi() 
var sayHi = function (){
   console.log("Hi")
}
```
We get an error, because sayHi() the function doesn't exist! But *sayHi* the variable does!

The difference between var, let and const:
Var behaves in the way we just described. It can be declared in the whole scope in which it was declared despite when it was declared. So if it's declared on line 10, you can still call on it's initialization in it's scope on line 1 (given that they're both in the same scope.
Let/const however is different, unlike var, you can only declare a let/const variable after it has been declared and/or defined.

