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


Object Creation
---------------
My last sprint focuses on 4 styles of object creation:

###Functional style###

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

###Functional style with shared methods###
Notice that the `greet` method is taken out of the `Person`. This will save some memory.  `_.extend(destination, *sources) ` is one of the function from underscore library. It takes the first perimeter as the destination object, and copy all the properties in the source object(s) to the destination obejct. 

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

###Prototypal###
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

###Pseudo-classical###
This works similarly to the Prototypal style but pseudo-classical provides some syntatical convenience -- saving some typing. 

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



Hash Table
---------------
1. Assigning a key is 'amortized constant'(almost constant, but sometimes slower); adding a key is 'constant'
