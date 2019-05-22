---
layout: post
title:      "what is functional programming?"
date:       2019-05-21 23:07:55 -0400
permalink:  what_is_functional_programming
---


getting to know functional programming.
<br><br>
**definitions:**
* *side-effects* - global program state along with a function's arguments can affect a function's resulting value
<br>
* *referential transparency* - an expression evaluates to the same value without changing the program's behavior
<br>
* *expressions* - produces a value; e.g. identifiers, literals, operators
* *statements* - performs an action (e.g. loops, `if/else` statements, `switch`, `throw`)
<br><br><br>
functional programming (FP) is a declarative programming paradigm that:
* can compose pure functions
* avoids shared state, mutable data, and side-effects<br>
**FP vs. OOP**
| functional programming | object-oriented programming |
| --------------------------- | ---------------------------------- |
|    declarative paradigm    |          imperative paradigm          |
| "what to solve"        | "how to solve" |
| uses expressions | uses statements |
| recursion | iteration |
| no side-effects | can have side-effects  |
| referential transparency | referentially opague (lacks referential transparency) |
| data and behavior kept separate | data and behavior kept in single location (known as "objects") |
| function composition | imperative control flow |
<br><br>
**concepts and paradigms specific to functional programming:**
1) **functions are first-class and can be higher order**<br>
higher order functions are functions that operate on other functions. they can either:
- can take other functions as arguments and/or
- return a function
they allow abstraction of actions and not just values.
<br><br>
first-class functions are treated as a first-class variable, in other words, functions are treated as data in that it can be:
- passed to functions as a parameter
- returned from functions
- stored in data structures
in FP, higher order functions allow reusability on various data types rather than only having the ability to operate on a specific data type that it is designed to operate on.
<br><br>
2) **pure functions/function purity**<br>
pure functions are functions that:
- always produce the same output for the same arguments and
- has no side-effects
function calls are not dependent on the timing and the order they are called:
```
const add = (x, y) => x + y;
add(12, 10); 
// 22
add(10, 12); 
// 22
```
however, note that the order of the composition will change the output:
`f(g(x)) != g(f(x))`<br>

3) **recursion**<br>
there are no "for" or "while" loops. iteration is implemented via recursion.
recursion does not require a pre-determined number of times to execute a block of code. instead it divides the problem into smaller problems and then reverses and combines the smaller pieces. for instance, merge sort is a sorting algorithm that recursively splits a list into sublists and then merges the sublists to produce a complete sorted list.
![](https://upload.wikimedia.org/wikipedia/commons/c/cc/Merge-sort-example-300px.gif)

4) **referential transparency**<br>

5) **immutability**<br>
an immutable variable cannot be modified after it is initialized. it helps maintain state throughout runtime of a program. instead, new variables are defined to store a new value.

6) **function composition**<br>
function composition is the process of combining two or more functions to produce a new function. it is used to abstract simple functions to build more complicated functions to help refactor code into short, clean, and functional code.<br>

**some FP facts:**
* origins in lambda calculus
* one of the first languages supporting FP was Lisp (1958). it was developed by John McCarthy at MIT for the IBM 700/7000 series scientific computers
* ES5 adds several common functional utilities to JavaScript

**some functional programming languages:**
* Lisp
* Clojure (dialect of Lisp)
* Scheme (dialect of Lisp)
* Haskell
* Erlang
* Elixir
* Scala
* F#
* Elm
* OCamel
* Racket
* Standard ML
* Wolfram Language
* JavaScript
