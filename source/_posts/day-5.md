---
title: Day 5 
tags: 
- during-bootcamp
- data-structures
- pair-programming
comments: true
date: 2016-06-04
---

First Pair Programming Feedback
---------------------

So I had my first pair programming at MKS yesterday. It was quite an experience! Yes, there were struggles, frustration, fear of not being able to finish the sprint in time... but there were also so many wonderful moments -- joy of problem solving, debugging, helping out each other. Seeing my code passing all the tests made those negative moments insignificant. 

Arrays and Linked Lists
-----------------------
* JS's arrays are closer to hash tables
* Array as spots 
* Accessing an array is constant(random access--give me array[3]),but that is rarely the case, we usually search an array(linear: give me an item that is greater than 100) 
* Deleting an item from array is linear, because getting rid a spot will cause other items to shift over, number of operation depends on how many items we have. Adding an item to the start of an array is linear too. (consider shift())
* myArray.push(20) this operation is constant
* Allocating too much -- need to reallocate often; allocating too big -- waste of memory
* Amortized constant: mostly constant, but sometimes more than that

** Linked Lists like scanvager hunt:**
upside: rooms can be anywhere
downside: need to access the first room to get to any room
* Adding/removing items are always constant
* Searching for an item is linear

```
var head = {value:10}
var tail= head;
var newNode = {value:20}
tail.next = newNode;
tail = newNode;