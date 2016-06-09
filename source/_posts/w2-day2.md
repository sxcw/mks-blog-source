---
title: Day 7 is Functional Programming
tags: 
- during-bootcamp
- functional-programming
comments: true
date: 2016-06-07
---

Today is second day of second week. Yesterday, I did a lot of self-studying on scopes, closure, modules. I will continue to do more self-study on prototypes and functional programming and do pair programming in the afternoon.  

Self-Studying Notes:
-----------------------
* A constructor makes an object 'linked to' its own prototype
* The word `.constructor` is an arbitrary word, it doesn't mean what it was constructed by. 
* ` __proto__` is pronounced as  Dunder proto
* `a1.__proto__ === Object.getPrototypeOf(a1)`
* `[[prototype]]` is a linkage between one object to another. We can get that linkage from `Object.create` or using `new`. `[[prototype]]` : gives us the ability to walk up the prototype chains, delegating failed lookups.

Callback, Functional Programming
-------------------------------
* Definition of Functional Programming: First class function, passing function to another function, lack of mutation
* Curried function: receives only a single perimeter; if more than 1, returns another function. In other words, when a function is curried, that means it is a function that takes one argument, and returns another function. This other function also takes one argument, and returns a further function. And so on and so on, until you finally get your value.

```
function getProp(propName) {
  return function(player) {
    return player[propName];
  }
}
map(Data.players,getProp('name'))
```
```
function add(x,y) {return x + y};
function add_(x) {
  return function(y) {
    return x+y;
  }
}
```
```
function add3(x) {
	return function(y){
		return function(z) {
			return x+y+z;
		}
	}
}
var result = add(10)(20)(30) // ==>60
```

```
// partial application: most of the time we don't provide all the perimeters
function add (x,y,z) {
	return x+y+z;
}
var addFive = add.bind(null,3,2) // we don't care what 'this' refers to now
addFive(10) // 5

```