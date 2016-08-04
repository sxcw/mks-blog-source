---
title: Day 39 and Redux!
tags: 
- during-bootcamp
- redux
comments: true
date: 2016-07-22
---

Notes from <a href="http://teropa.info/blog/2015/09/10/full-stack-redux-tutorial.html" target="_blank">Full Stack Redux Tutorial</a>
---------

* All kinds of frameworks and architectures have state. In Ember apps and Backbone apps, state is in Models. In Angular apps, state is often in Factories and Services. In most Flux implementations, it is in Stores. How does Redux differ from these?  The main difference is that in Redux, the application state is all stored in one single tree structure. In other words, everything there is to know about your application's state is stored in one data structure formed out of maps and arrays.

* A Redux application's state tree is an immutable data structure. This means any two successive states of the application are stored in two separate and independent trees. (upside: get undo/redo for free, encourages pure functions: functions we trust to behave predictably)

* An action is a simple data structure that describes a change that should occur in your app state. It's basically a description of a function call packaged into a little object. By convention, every action has a type attribute that describes which operation the action is for.

* It is a much better idea to, whenever you can, make operations work on the smallest piece (or subtree) of the state possible. What we're talking about is modularization: Have the functionality that deals with a given piece of data deal with only that part of the data, as if the rest didn't exist.

* This is a small example of the kind of pattern that becomes much more important the larger an application gets: The main reducer function only hands parts of the state to lower-level reducer functions. We separate the job of finding the right location in the state tree from applying the update to that location.

