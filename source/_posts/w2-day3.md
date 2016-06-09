---
title: Day 8 is Asynchronous
tags: 
- during-bootcamp
- functional-programming
- asynchronous
comments: true
date: 2016-06-08
---

Today I will continue to do some pair-programming on functional programming problems. I will get deeper into using callbacks.  

Self-Studying Notes:
-----------------------
* Pure functions don't change anything. They are testable, portable, memoization, parallelization(can run several copies of same function at a time).
* In essence, what that setTimeout(..) call is doing, besides setting up a timer, is marking the entry point to resume the program at that later time. It's like saying to the engine, "when you resume, call back into my program at this point." And thus we get "callback".
* Promises: continuation events.  A promise is a future value or eventual value. It's a placeholder for a value that we expect to eventually arrive, and once it does, it's fixed and immutable from then on.
* Promises as a callback management system: promises can only be resolved once, so a callback registered in a then(..) can only possibly ever be called once, no matter what the originator of the promise tries to do. This restoration of trust is the most essential part of why promises exist.
* Promise chain lets you express a vertically oriented series of steps, any or all of which can be asynchronous in completion. Promises encapsulate the time-dependent state -- waiting on the fulfillment or rejection of the underlying value -- from the outside, the Promise itself is time-independent, and thus Promises can be composed (combined) in predictable ways regardless of the timing or outcome underneath.
* `then(..)` always produces a promise
* "I am reasoning about my future cheeseburger already, even though I don't have it in my hands yet. My brain is able to do this because it's treating the order number as a placeholder for the cheeseburger. The placeholder essentially makes the value time independent. It's a future value." -- read more at <a href="https://github.com/getify/You-Dont-Know-JS/blob/master/async%20%26%20performance/ch3.md" target="_blank">You Don't Know JS : Promises</a>.

Asynchronous
-----------------------
* Asynchronous with plain callbacks + promises
* Run the entire block of code first before any asynchronous code can run. Asynchronous code does not run until later.
* Single-threaded nature: Only a line of code can run at the same time. Anything that takes a lot of work can be put into the background. 
* Timer starts immediately.


```
console.log("A");

setTimeout(function() {
  console.log("B");
}, 3000);

superLongComputation(); // this takes 5 secs to run

setTimeout(function() {
  console.log("C");
}, 2500);

console.log("D");
```
Answer: ADBC 

```
function playerStats(){
	var API = DataAPI.Callback;
	var data = null;
	// please send this request to server ( initiate asynchronous call, the callback function needs to wait till we hear something from server)
	API.getAllPlayers(function(players){
		players ==> array
		data = players;
		console.log('Data2: ', data )
	})
	console.log('Data: ', data ) // this console logs null
}
playerStats();
```

* Callback hell is composed of these two flaws: 1)Non-trustability of the callback's invocation, due to Inversion of Control
2) Non-linear, non-sequential reasoning
3) 'pyramid of doom'



```
// line1
setTimeout(function(){
	//line3
	//line4
},1000)
// line2
```

* Inversion of Control: there is a part of program I am in control of executing (line1,line2) and there is a portion of my code that I am not in control of executing(line3, line4). (so put that portion in the callback so it will execute in the callback--> inverse the control) 
*`setTimeout` is the utility function, we don't worry too much about the timer not calling the callback. (no trust issue: not too early/late, not too many/few times, no swallowed errors...)
* Thunks: from a synchronous perspective, a thunk is a function that has everything it needs to run the function and gives value back. A function that has a closure state keeping track of some values and give you those values back when we call the function

```
// synchronous example: thunk 
function add(x,y){
	return x+y;
}
var thunk = function(){
	return add (10,15);
}
thunk(); // 25 -- thunk becomes the container of a particular state. It becomes a token that represents 25.  (Promises: a wrapper around a value)
```

* Promises are like asynchronous thunks: they don't need any more values passing into them to do their jobs-- except we do need to pass callbacks so we can get values back. 

```
// asynchronous example: thunk 
function addAsync(x,y,cb){
	setTimeout(function(){
		cb(x+y);
	},1000);
}
var thunk = function(cb){
	addAsync(10,15,cb);
}
thunk(function(sum){
	sum; // 25
})
```

