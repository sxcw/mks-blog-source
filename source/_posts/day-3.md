---
title: Day 3 is Better than Yesterday
tags: 
- during-bootcamp
- complexity-analysis
comments: true
date: 2016-06-02
---

After a good night's sleep, day 3 is going to be better! I will have the first pair programming this morning on stacks and queues. Several lectures today will focus on object creation and code reuse. Looking forward to those lectures! 

Human body's ability to self heal and adjusting to new changes is amazing. On day 3, I feel I am almost on top of everything and can gradually appreciate such hectic, intense schedule. 

Quick Notes
---------------------

Note #1: For `call` and `apply`, the first argument is always something I want to bind to `this`. 

Note #2: `bind` : create a copy of function, bind something to be perimeter `this`, the original function is unchanged.

Note #3: The only difference between an object decorator and a class is that a class builds the object it's augmenting, whereas decorators accept their target object as an input.

Note #4: Prototypal : instead of assigning methods directly to child object, child object inherits from them. 

Note #5: `Inherit method: Object.create(parent)` -- create an empty object and inherit from it. Child doesn't have all properties from parents, there is just a link. Create a link to the parental object, continuous relationship 

Note #6: `Object.getPrototypeOf(child) === parent` ; To check prototypal relationship: `Object.getPrototypeOf(Array.prototype) === Object.prototype`

Note #7: `console.dir(Array.prototype)`

Note #8: All functions come with a `.prototype` property that points to an empty object (almost empty, because it has a `.constructor` property that points back to its own ). 
Note #9: `.prototype` is not a keyword, it's just a property name( good thing is we get it for free, every function has it!)


Complexity Analysis in the Real World
-------------------------------------

<h3> Quick Notes </h3>
* Two types: time and space, but we mostly worry about time. 
* n : input size
* Example: find out the greatest difference in `[10,5,15,50]`;
How many operations we need to do ? 
- n * n (n square), if we take 10 and do 10-5, 10-5, 10-15, 10-50... and take the next number 5, 5-15,5-50..., the number of steps is close to n square. ==> O(n2) 
- 2n, find the smallest number and biggest number, and result = biggest - smallest ==> O(n)
- constant (awesome!), if the list is sorted, then result = last item -first item ==> O(1)

<h3> Types </h3>

* logarithmic algorithm, faster than linear, because each step we eliminate half of the input.
* constant: O(1)
* linear: O(n)
* quadratic: O(n2)
* exponential: O(c^n),c:constant password validation








