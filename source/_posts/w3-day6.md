---
title: Day 17 is React Again
tags: 
- during-bootcamp
- react
comments: true
date: 2016-06-18
---

After some struggles with React yesterday, I went back to re-watch some of the codeSchool videos and a few concepts finally clicked now. 


<h3>Lecture Notes</h3>

* React is the 'view' in MVC
* `fetch` returns a promise: future standard (eventually will be built into the broswer), had a polyfill (a lirary we can download and use)
* polyfill: a library that we can use today that works exactly like the future standard (it doesn't implement the standard)
* Framework : More opionated, it usually has standard way of building software. Do it the Angular way.  Angular, Ruby, Ember: here is how you do stuff, and you must do it this way.  
* Library: a piece of code that does one thing well. Less opionated. 
* must do `setState()` to redraw 
* write HTML-ish syntax in JS --> JSX (need to pipe it to JS so browsers can understand)
* `{}` let us interprest stuff, otherwise plain text
* Babel: a transpiler, which means it translates source code (JS-ish) to source code (JS)
* ES6, offcially name is es2015 --> ES5
* presets: `react` turn JXS to JS; `es2015` turns ES6 TO ES5 so all browsers can read 
* Unlike Mithril, in React, Components only redraw themselves when their own state updates (as opposed to redrawing the whole app every time).
* ES6 arrow function:

```
var f = (x,y) => x+y;
var f = function(x,y) {return x+y}

var g = (x,y) =>{
	var result = x+y;
	return result;
}
// arrow function also solves `this`. It will not receive a hidden perimeter `this`. (`.call('hello')` doesn't work) Arrow function will look up to the outer scope. React uses `this` to maintain what `this` refers to (class)
```

* consturctor() : function that runs when we create a new instance. Always have to call super() first and set inital state.
* `this.setState({})` ==> just to update the component. no redraw()
* `props` all the HTML properties we pass in(they should be immuntable). `props` comes from parents. 
* expressions result in values
* statements don't result in values (`if`is a statement)
* in react: no while loop, if statements
* class is called className, e.g. <div className="pet"></div>
* once it is on the page, take note that your component will not re-render again until it calls its own `this.setState(...)`
* Containers deal with state and components deal with props
