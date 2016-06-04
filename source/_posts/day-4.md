---
title: Day 4 is Seniors Project Presentation
tags: 
- during-bootcamp
- object-creation
- pair-programming
comments: true
date: 2016-06-03
---

First Pair Programming Feedback
---------------------

So I had my first pair programming at MKS yesterday. It was quite an experience! Yes, there were struggles, frustration, fear of not being able to finish the sprint in time... but there were also so many wonderful moments -- joy of problem solving, debugging, helping out each other. Seeing my code passing all the tests made those negative moments insignificant. 

Seniors presented their legacy project tonight. It was exciting to see what kinds of projects I will be able to make in 6 weeks. 

Two things I noticed from the presentation: 
* Most seniors use React in their projects and they recommend taking the React course at the Code School as a gentle introduction. 
* Git becomes a huge thing when collaborating others, getting to know more advanced git and modularizing your code will make the workflow smoother. 

One side(interesting) note: no female student in the senior cohort... 



Object Creation
---------------

My last sprint focuses on 4 styles of object creation:

<h3> Functional style </h3>

```
var Person = function (name, hobby) {
  var person = {}
  person.name  = name
  person.hobby = hobby

  person.greet = function () {
    return "Hi I am " + person.name
  }
  return person
}


var alice = Person('Alice', 'programming')
var bob   = Person('Bob', 'gaming')

alice.greet() //=> "Hi I am Alice"
alice.greet === bob.greet //=> false


var f = alice.greet

f() //=> "Hi I am Alice"
```

<h3> Functional style with shared methods </h3>

Notice that the `greet` method is taken out of the `Person`. This will save some memory.  `_.extend(destination, *sources) ` is one of the function from underscore library. It takes the first perimeter as the destination object, and copy all the properties in the source object(s) to the destination object. 

```
var Person = function (name, hobby) {
  var person = _.extend({}, personMethods)
  person.name  = name
  person.hobby = hobby

  return person
}
var personMethods = {
  greet: function () {
    return "Hi I am " + this.name
  }
}

var alice = Person('Alice', 'programming')
var bob   = Person('Bob', 'gaming')

alice.greet() //=> "Hi I am Alice"
alice.greet === bob.greet //=> true
```

<h3> Prototypal </h3>

Note that `Object.create(prototype of the new object)` sets up the inheritance relationship.  The newly created object will inherit all the properties/methods from the prototype object. 

```
var Person = function (name, hobby) {
  var person = Object.create(persounMethods)
  person.name  = name
  person.hobby = hobby

  return person
}
var personMethods = {
  greet: function () {
    return "Hi I am " + this.name
  }
}

var alice = Person('Alice', 'programming')
var bob   = Person('Bob', 'gaming')

alice.greet() //=> "Hi I am Alice"
alice.greet === bob.greet //=> true
```
 
<h3> Pseudo-classical </h3>

This works similarly to the Prototypal style but pseudo-classical provides some syntactical convenience -- saving some typing. 

```
var Person = function (name, hobby) {
  // the below 3 lines are automatically inserted by Javascript if the 'new' keyword is used during object creation-- save some typing! 
  // var person   = this
  // person.name  = name
  // person.hobby = hobby
  this.name  = name
  this.hobby = hobby
  // no need to explicitly return the object 
}

Person.prototype.greet = function () {
  return "Hi I am " + this.name
}


var alice = new Person('Alice', 'programming')
// ^ Equivalent to below two lines:
// var alice = Object.create(Person.prototype)
// Person.call(alice, 'Alice', 'programming')


var bob   = new Person('Bob', 'gaming')

alice.greet() //=> "Hi I am Alice"
alice.greet === bob.greet //=> true
```

```
var alice = new Person('Alice')
// equivalent to these two lines:
var alice = Object.create(Person.prototype) //empty object that inherits from Person.prototype
Person.call(alice,'Alice') // 'this' now points to alice

```



Hash Tables
---------------

* Assigning a key is 'amortized constant'(almost constant, but sometimes slower); looking up a key is 'constant'. 
* Goal is to keeping buckets small, only need to iterate a few times. (constant-ish), each bucket can only contain a few items
* Need to resize table if there are too many elements, also need to redistribute 
* One directional: easy to get from key to hash (120 % 3 === 0, 123 % 3 === 0, hard to track if the key is 120 or 123)
* Bucket index === 0; put it in the index 0 (first) bucket. 74178 %3 === 0 (3 is the bucket.length, it is the number of buckets)
* Bucket function: important --> control how many buckets there will be. Will there be a lot of buckets remaining empty? 
* Too few buckets or resize too early: resizing is CPU expensive; too many buckets or resize too late: waste memory.
* When resizing, we are redistributing items to new budgets (74178 % 6 ===0) Module by 6 gives us a larger table with 6 buckets.


Trees 
---------------

* Like linked list, but with more nodes
* Each node has keys 
* Deleting a node can be tricky, logarithmic operation
* Downside: inserting  17-18-19-20, it becomes linear,a way to bypass it, using red black tree.


Test Driven Development (TDD)
---------------

* A methodology to develop software, aka behavior driven development
* red: write a failing test ; green: make test pass; refactor: clean up and improve code ==> iterative process
* Why write test?  
- modules with interfaces
- drives you to look for failure modes and corner cases, not just developing happy paths
- demands you write an MVP(minimal viable product) first, always.  avoid wasted code, not used, just build the core. Tests make you write minimally sufficient code, no more
- documents the expected behavior of the system
- catches errors: safety in refactoring process 

<h3>Types of Tests</h3>

* Unit Test: focuses on a single method or class
- focuses on a single method or class
- local, no database, network, one thing at a time
- only testing input and output, not the inner working of a function

* Integration Test: ensures different parts of a system, work correctly together 
- ensure links between parts work together 
- network, database, more than one part of a system
- Example: POST to a REST API , then GET the posted record 

* End-to-End Test: makes sure your app works in real world
- as if a person were using it
- testing a feature

* Visual Test: ensures a UI hasn't changed unexpectedly
- tests a rendered page against a known good screenshot
- don't recommend practicing VT

* Mocha is not an opinionated test runner, thing for running tests
* Chia has assertion ('expect')
* Jasmine and Karma: integration test

Best Practice
---------------

* Two types of people:
- the conjurer: ignore complexity, intuitive leaps,'magic', don't care how it works, only knows how to use it
- the scribe: meticulous understanding, deep debugging, 'mastery'

* Abstraction: 
- Use high level terms, not worrying about details when communicating
- Butler: please make breakfast, then you have output: breakfast(no need to specify lower-level, very detailed steps)
- Map is an abstraction of looping, pushing to an array 

* Leaky Abstraction: 
- Have abstraction but it is not sufficient enough, so we may have to add details

* Encapsulation:
- data hiding 
- IIFE (only useful because it creates another scope):

```
var MathHelpers = {}
MathHelpers.average = function(){}
MathHelpers.mean = function(){}
```

* Mutation: can create new data or assign new variable but don't change data. 


Review
--------

* What message will eventually be alerted? After how long?

```
var name = "Window";
var alice = {
  name: "Alice",
  sayHi: function() {
    alert(this.name + " says hi");
  }
};
var bob = { name: "Bob" };

setTimeout(function() {
  alice.sayHi();
}, 1000);
```
Answer: Alice says hi, after 1 second

* What message will eventually be alerted? After how long?

```
var name = "Window";
var alice = {
  name: "Alice",
  sayHi: function() {
    alert(this.name + " says hi");
  }
};
var bob = { name: "Bob" };

var sayHi = alice.sayHi.bind(bob)

setTimeout(function () {
  window.sayHi()
}, 1000);
```
Answer: Bob says hi, after 1 second. (`bind` creates a copy of function, and it forever sets the value of 'this' to bob)

ClearTimeout 
------------

```
var t = setTimeout(function(){
  console.log('Timed out!')
},7000);
clearTimeout(t);
```
