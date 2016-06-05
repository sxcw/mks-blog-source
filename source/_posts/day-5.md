---
title: Day 5 is the End of First Week 
tags: 
- during-bootcamp
- data-structures
comments: true
date: 2016-06-04
---

 First Weekend is Coming 
---------------------

Today marks the first weekend at MKS.  I almost make it through the first week! 

Arrays and Linked Lists
-----------------------
* JS's arrays are closer to hash tables
* Array as spots 
* Accessing an array is constant(random access--give me `array[3]` ),but that is rarely the case, we usually search an array(linear: give me an item that is greater than 100) 
* Deleting an item from array is linear, because getting rid a spot will cause other items to shift over, number of operation depends on how many items we have. Adding an item to the start of an array is linear too. (consider `shift()`)
* `myArray.push(20)`-- this operation is constant
* Allocating too much -- need to reallocate often; allocating too big -- waste of memory
* Amortized constant: mostly constant, but sometimes more than that (slower)

<h3> Linked List is like a scavenger hunt:</h3>

* Upside: rooms can be anywhere
* Downside: need to access the first room to get to any room
* Adding/removing items are always constant
* Searching for an item is linear


Algorithm
-----------------------

* Step by step instruction to solve problems, like a recipe
* We should have an expected result in the end 

<h3> Steps: </h3> 

-  Establish rules of problems, constraints, what are inputs/ outputs
-  (if using TDD) Write a test that would verify a solution
-  Explore the problem space and discover techniques (what are some edge cases-- empty list, nested list?) 
-  Generate a simple plan in plain language that solve the problem (You must be able to articulate the solution first)
-  Elaborate the plan into steps (pseudo code) : using indentation to show hierarchy.  More explicitly define things, and more technical. 
-  (Walk through the code as the interpreter)Optionally, verify each step using simple inputs. 
-  Translate each step into code


jQuery
-----------------------
* Get something, do something
* `$` is jQuery's convenience variable so that we don't need to spell out `jQuery`
* `$('.person').css({'font-size' :'1em'})` === `$('.person).css({'font-size', '1em'})`
* Can have multiple pairs: `$('.person').css({'font-size' :'1em', 'background':'#ccc'})`
* jQuery's `on` method helps us respond to user's action like clicking 

```
$('p').on('click',function(e){
	var text = $(this).text();
	alert();
})
```

Merge
-------------------------
* `git mergetool` --> `git add` --> `git commit`