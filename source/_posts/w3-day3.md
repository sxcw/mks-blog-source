---
title: Day 14 is the beginning of Mithril
tags: 
- during-bootcamp
- Mithril
- virtual DOM
- promises
comments: true
date: 2016-06-15
---

Today, I am going to make a pet shop web app using <a href="http://mithril.js.org/index.html" target="_blank"> Mithril framework</a>. It is the first framework I will use. It's going to be fun and very challenging.


jQuery VS. Mithril
--------------
* Recreates ALL elements every time the function runs
* DOM is slow
* Dreadful 'blink effect'
* Only update DOM elements whose data has changed
* DOM Diffing: not wiping out everything, only render the things that have changed

<h3> Mithril: </h3>

* virtual DOM:  `m('.item','Item #1')` --> work on these little objects are faster than working with actual DOM elements because the former don't have a lot of properties
* virtual Dom is : A PLAIN JS OBJ THAT REPRESENTS A DOM ELEMENT
* `var vdom1 = m('h1','Hello')`
* With Mithril we can still construct declarative HTML code but don't worry about performance 
* Component: an object with view and controller(optional). It needs at least a `view` property
* mount a component to page
* `m.redraw()`: run the view function again. We rarely use this though
*  Mithril automatically redraws 1) when we call `m.mount()` 2) after running a DOM event handler function 3) after an ajax request, `m.request`. It redraws everything! (good feature)

* `this` refers whatever that triggers the event listener
* controller: initializer of my component, get initialized once as a constructor function, good place to put view states, temp variable, use per component


Notes
--------------

<h3> The era of jQuery </h3>
* IE6, Firefox, Opera (no Chrome)
* Terribly inconsistent behavior for JS, CSS, HTML
* jQuery got popular for its consistency merging 
* jQuery has competition: prototype.js and Mootool.js
* Blame jQuery, jQuery === spaghetti code, so Backbone.js emerges (touted as the solution for code organization)
* Backbone is big : requires underscore and jQuery (~80kb gzipped)

<h3> The Hotness of Angular (by Chrome)</h3>
* Two-way data binding
* Created by a couple of Java developers

<h3> The Simplicity (sort of) of React (by Facebook)</h3>
* Virtual DOM
* Uses functional programming concepts to make app dev easier 
* Just the V in MVC
* Downside: Need more stuff - model layer: Flux, Redux, or something else (mobx?)
* Needs a compiler(need JSX, basically javascript with HTML syntax in it)

Note #1: every time we create an ID, we create a global variable
Note #2: Backbone and Angular don't have virtual DOM
Note #3: Every file gets its own scope. Browsify(make stuff work like node.js), `require` is part of Browsify


Promises
-------------

* a Promise object always hold a future value, we send the request to serve, wait the value comes back, and we fill the promise with a value and then we can access it. 
* `.then` --> when it is finally filled up, it runs that funcion with that returned value
* `.then` returns a new promise object 

* a promise sends out --> wait on HTTP request
* a promise is like an empty box, once the request is complete, value will be fed into the empty box. We cannot access the box directly. The only way to get to the value is to use `.then`

* resolve -- go down the happy path (`.then`); reject: go down the sad path (`.catch`)
* If we deal with the `.catch`, then it might go back to happy path. We can also return values from `.catch`
* `throw new Error ()` --> code stops running (like return)
