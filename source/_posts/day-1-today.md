---
title: Day 1 is today!
tags: 
- during-bootcamp
- quick-takeaways
comments: true
date: 2016-05-31
---

** One-line takeaways: **

*  Variables do not contain values; they point to values! 
*  Variables cannot point to another variables. 
*  Perimeters are local variables 
*  When we 'return', we return a value, we cannot return a variable 
*  Runtime scope: in memory scope, every time we run a function, we get a new runtime scope. Every time a function finishes running, the runtime scope (and all variables) is garbage collected
* Lexical scope: how you determine what variables you have access to. Lexical scope is set when a function is created, not when it's run. 
*  Closures are the mechanic behind lexical scoping, using variables outside its scope.
*  A closure happens when a function uses a variables outside its scope. Closure is set when a function is created. 
*  Nested object: the inner object doesn't live inside the outer object. It lives somewhere else in the memory. 
* 'this' is just a perimeter, and 'this' usually refers to whatever that is left of the dot
* Scope means where can I access a variable. 

** To do: (good practices)**
1. draw diagrams 
```
var createIncrement = function(){
  var counter = 0;
  return function() {
    counter = counter + 1;
    return counter;
  }
}

var incA = createIncrement();
var incB = createIncrement();
incA();
incA();
incB();
```

2. draw diagrams

```
var speak = function () {
  return "I want to eat ' + this.favFood;
};

var rabbit = {
  speak: speak,
  favFood = 'carrot'
};
var mouse = {
  speak: speak,
  favFood = 'cheese'
};

var obj = rabbit;
obj.speak = 99;

mouse.speak // function
rabbit.speak // 99
```