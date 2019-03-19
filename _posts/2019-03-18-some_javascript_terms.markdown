---
layout: post
title:      "some JavaScript terms"
date:       2019-03-18 21:05:10 -0400
permalink:  some_javascript_terms
---


review of hoisting, context, and closures.<br>

***what is hoisting?*** 
<br>
hoisting is a verb that means to "raise or haul up."<br>
when JavaScript compiles your code, all declarations (var, let, const, function, function*, class) are added to memory, allowing them to be accessible regardless of where the declaration is made.
<br><br>
when using `var`:<br>
if declared inside a function, it is hoisted (raised or hauled up) to the top of their local scope.<br>
if declared outside of a function, it is hoisted to the top of their global scope.
<br>
for example:
```
var greeting = "hello";
console.log(greeting);
// "hello"
```

```
greeting = "hello";
console.log(greeting);
var greeting
// "hello"
```
`var greeting` will be hoisted to the top, but the value will remain where it is. thus, although the code above will produce the intended value, the snippets below will not work because initializations are **not** hoisted:

```
console.log(greeting);
var greeting = "hello";`
// undefined
```

```
var greeting
console.log(greeting);
greeting = "hello";
// undefined
```

when using `let` and `const`:<br>
`let` is **not** initialized with `undefined` (unliked `var`) and will throw a Reference Error if called before a value is assigned and if it is called outside of the block, statement, or expression where it is used.<br>

the value of `const` cannot be re-assigned because it creates a read-only reference to a value so it must be initialized at the same time it is declared.
<br><br>
***what is context?***
<br>
context is the value of the keyword `this`. the value of `this` changes depending on how it is used. however, the method `bind( )`, `call( )`, or `apply( )` can be used to set the value of `this` regardless of how it is called.
<br>
1. by itself or in an unbound function, `this` refers to the global object.
```
method( )
// window
```

2. in a method, `this` refers to the owner object.
```
person.shakeHand( )
 // person
```

3. in a `strict` function, it is undefined
```
'use strict';
function method( ) { return this; }
// undefined
```

4. in an event, `this` refers to the HTML element that received the event.
```
$("div#firstElement").click(function( ) {
    alert("Hello!");
})
// div#firstElement
```

5. when using the methods `call( )` or `apply( )`, `this` can refer to any object passed in as the first parameter.<br>
`call(newObject, param1, ..., paramX)`
* takes inline arguments

```
.call( objectA )
// Object A
```
```
objectA.testContext.call( objectB )
// Object B
```

`apply(newObject, [param1, ..., paramX])`
* takes array of arguments

```
.apply( objectB )
// Object B
```
```
objectA.testContext.apply( window )
// window (global)
```
		
6. in arrow functions, `this` retains the value of its enclosing lexical context. in other words, it permanently binds to the `this` of its enclosing function because the arrow function does not have its own `this`.

```
function person( ){
  this.name = "Homer";

  setName( ( ) => {
    this.name = "Bart";
  } );
}
// this in the arrow function refers to person
```
<br>
***what is closure?***
<br>
a closure is created when an inner function has access to the parent scope, even after the parent function has closed. 
closures have 3 scope chains:
1. access to own scope
2. access to parent function's variables
3. access to global variables
<br>
to use a closure, simply define a function inside another function and return it to another function.

```
function outerFunction( ) {
  var a = 1;

    function innerFunction( ) {
		    var b = 2;
				console.log(a + b);
		}
   return innerFunction;
}
var newFunction = outerFunction( );
newFunction( )
```

the `innerFunction` can calculate `a + b` using the value of `a = 1` even after `outerFunction` completes execution. closures are able to read and manipulate the variables of their parent functions.
<br><br>
some examples of when closures are useful:
1. using the parent function to create any number of related functions with similar but unique purposes
2. enabling data privacy (enclosed variables are only in scope within the parent function and can only be accessed by an outside scope through privileged methods)
2. creating stateful functions (return values are influenced by their internal state)
3. partial application & currying (functional programming)
