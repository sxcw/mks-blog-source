---
title: Day 5 
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
* Accessing an array is constant(random access--give me array[3]),but that is rarely the case, we usually search an array(linear: give me an item that is greater than 100) 
* Deleting an item from array is linear, because getting rid a spot will cause other items to shift over, number of operation depends on how many items we have. Adding an item to the start of an array is linear too. (consider shift())
* myArray.push(20)-- this operation is constant
* Allocating too much -- need to reallocate often; allocating too big -- waste of memory
* Amortized constant: mostly constant, but sometimes more than that(slower)

<h3> Linked Lists like scanvager hunt:</h3>
* Upside: rooms can be anywhere
* Downside: need to access the first room to get to any room
* Adding/removing items are always constant
* Searching for an item is linear

