---
title: Day 9 is Full of Promises 
tags: 
- during-bootcamp
- functional-programming
- asynchronous
- promises
comments: true
date: 2016-06-09
---

After 3 days of self-studying, I will start a longer sprint that spans over 3 days. The sprint will test how well I have learned from the study materials.    

Self-Studying Notes:
-----------------------

* From the outside world, we don't know/care whether the value is available immediately 
* We factor time out of the equation: we produce a wrapper around a value that becomes time-independent: it doesn't matter if the value is available now or it will come later. 
* Time is the most complex factor of state in programming. Managing time is the very complex! 
* Again, promises are the time-independent wrapper around values. Thunks are promises without a fancy API.
* By using the closure to maintain the state of something, we eliminate time as the complex factor of state (time is abstracted away... not really a concern)
* Kyle Simpson: "Promises represent a placeholder for a future value. They solve the inversion of control issue that exists with callbacks by providing completion events for asynchronous tasks. This puts the control back inside the application."
* Instead of passing a callback to utility (it will finish later) --> inversion of control, we can add event listeners on some functions that will finish later. We just listen to the completion of events. When function finishes, we will get notified by the event listener. We are in control now.
* Rather than passing the callbacks in, how about having API that returns the event listeners to us?
* Promises restore trust: 1) only resolved once, 2) either success or error, 3) messages passed/kept 4) exceptions become errors, 5) immutable once resolved. It is a callback manager. A pattern of managing callbacks in a trust-able fashion.
