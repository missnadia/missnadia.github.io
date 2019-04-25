---
layout: post
title:      "simplicity of arrow functions"
date:       2019-04-25 12:25:47 -0400
permalink:  simplicity_of_arrow_functions
---

relationship between arrow functions and `this`.
<br><br>
arrow functions were introduced in ES6 as a new syntax for writing shorter functions and eliminating the binding of `this`. in regular function expressions, the context of `this` was determined by how the function was called. <br>

for example:<br>
in `strict` mode, `this` is undefined
```
'use strict';
function method( ) { return this; }
// undefined
```
**example of shorter functions:**

```
// ES5 - regular function expression
var selected = allJobs.filter(function (job) {
  return job.isSelected();
});

// ES6 - arrow function
var selected = allJobs.filter(job => job.isSelected());
```

**keyword `this`:**<br>
in arrow functions, `this` retains the value of its enclosing lexical context. in other words, it permanently binds to the `this` of its enclosing function because the arrow function does not have its own `this`. (using the example from MDN)

```
function Person( ){
  this.age = 5;

  setInterval(( ) => {
    this.age++; 
  }, 1000);
}

var p = new Person();
// this in the arrow function refers to the Person Object
```


