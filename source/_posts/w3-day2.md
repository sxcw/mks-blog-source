---
title: Day 13 
tags: 
- during-bootcamp
- MVC
- REST
comments: true
date: 2016-06-14
---

Tha pair programming yesterday went well and my partner and I had a lot of things done, we will keep working on the rest of basic requirements today. Hope we can get everything done on time.  My understanding of using ajax calls and promises also deepens a little. I can handle async problems more confidently. 

MVC
--------------
* Model View Controller 

<h3> Model </h3>

* A way to identify different types of our code and keep it organized
* Model : code that interacts with model data (source of truth, abstract representation of truth)
* Model can CRUD(create, read, update, delete) model data
* Model should never know about the view or try to update the view
* Control and view ask model to do crud, they cannot do crud

<h3> Controller </h3>

* Handle an user event
* Quite often, controller will ask model to CRUD, controller doesn't know how to deal with data.

<h3> View </h3>
* Read data from the model and update the page when we have the data
* Debate: how and when do we update the view (like append to DOM). Every framework/library has its own approach


REST
---------
* REST stands for 'representational state transfer'. REST makes a call from the client to the server and gets data back over the HTTP protocol
