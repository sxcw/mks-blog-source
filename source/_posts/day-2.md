---
title: Day 2 starts after a sleepless night
tags: 
- during-bootcamp
- recursion
- debugging
- keyboard-shortcuts
comments: true
date: 2016-06-01
---

Sleepless Night
---------------

Excitement and uncertainty contributed to a sleepless night. I was in bed 11:30pm last night and stayed wide awake till 3:30-ish. My body is still adjusting to the new hectic intense schedule. It senses changes and put itself into the survival mode.  I don't blame it and I know I have to take it easy and be patient. I will help my body go through this transition as painless as possible. 

Regardless of a restless night, I am still very excited to have my first pair programming session today. It will be fun, inspiring, and challenging. It will take my learning experience to a whole different level. Learning in a social context can be powerful and I am going to see the power today.  

Okay, here comes the lecture notes & what I have learned today:


Recursion takeaways
-------------------

Ask these questions when working on recursion problems: 

Q: What is the shape of my input(s) and output? (shape includes types) A: Array of numbers
Q: What am I doing at each step?  A: Double a number
Q: How do these steps fit together to get my final answer? A: put all doubled numbers together
Q: When do I stop recursing? (base case, when array.length is 0)
Q: When do I recurse? (each time, we passed in a newly sliced array as the argument. )

Example: 
```
var doubleEach = function(array) {
  if(array.length === 0){
    return [];
  }
  var double = array[0]*2;
  return [double].concat(doubleEach(array.slice(1)))
}

var numbers = [10,20,30];
doubleEach(numbers)
```



Reference and Value Practice
----------------------------

* After the following code runs, what will be the value of example?

```
var obj = { 
  inner: { x: 10 } 
};
var example = obj.inner;
obj.inner   = undefined;

```
Answer: { x : 10 } // todo: click to show

* After the following code runs, what will be the value of x.foo?

```
var x = { foo: 3 };
var y = x;
y.foo = 2;

```
Answer: 2


* After the following code runs, what will be the value of player?

```
var player = { score: 3 };
function doStuff(obj) {
  obj = {};
};

player = doStuff(player);

```
Answer: undefined


* After the following code runs, what will be the value of myArray?

```
var myArray = [2, 3, 4, 5];
function doStuff(arr) {
  arr[2] = 25;
};

doStuff(myArray);

```
Answer: [2,3,25,5]


* After running the following code, what will be the value of result?

```
var x = 10;

var puzzle = function (amount) {
  this.x += amount;
};

var alice = { x: 10, f: puzzle };

puzzle(5);
alice.f(5);
alice.g = alice.f;
alice.g(5);

var result = alice.x;

```
Answer: 20

* After running the following code, what will be the value of result?

```
window.name = 'window'

var alice = {
  name: 'Alice',
  greet: function () {
    return "Hi I am " + this.name
  }
}

var bob = {
  name: 'Bob',
  greet: alice.greet
}

var result = bob.greet()

```
Answer: "Hi I am Bob"



 Debugger 
---------------------

* Testing includes manual testing, automated testing
* Keyboard shortcut to open Chrome console: command+ option +J
* Every time we `console.log` something, make sure to label it
(use comma to separate arguments, not +)
example: `console.log('a' , a)`
* (Inside console) Put in `debugger` keyword
* (Inside console) Step over: go to next line; step into: go inside a function call
* (Inside console) Highlighted line: ready to run, not run yet
* (Inside console) Call stack: all the functions we are currently running till this point. Each item on the stack has its own runtime scope.
* (Inside console) The code stack shows how the code was running before it broke
* (Inside console) you are trying to call `.classList` on something that is undefined --> node is undefined
* (Inside console) `Conditional: if(node===undefined) {debugger}`, only stop when node is undefined
* A function is always truthy: `if(node.hasChildNodes)`... always truthy 
* Memorize: 0,false, "", NaN, null, undefined are falsey. Negative numbers are truthy (surprise!)


Data structures
---------------------

**Question: why do we need data structures?**

Answer: We need to store/organize data in a way that makes sense. Different data structures have different characteristics. They also provide a known set of assumptions of how the data will act and run (consider time complexity, which way is more difficult to access data, more expensive?)  

An expensive operation: in order to accomplish a goal, the computer has to do tons of things (it could be easier...)

***Limited Data Structures, including stacks and queues are restricted for good reasons: for example: only interact with the top item. ***

### Stacks (First in last out, like a stack of dinner plates)

Interface(how you interact with something), also known as API (application programming interface):

- push: put an item onto the top of the stack
- pop: take an item off the top of the stack
- peek: (optional) look at the top item only

```
stack.push(10);
stack.push(20);
stack.push(30);
// stack is [10,20,30];
stack.pop();
stack.peek(stack.length-1);
```

```
function createStackPusher(){
  var stack = [];
  return function(x){
    stack.push()
    return stack.length;
  }
}
var stackPusher = createStackPusher();
stackPusher(10);  //can only do push 
```

### Queues (First in first out, a line for a popular restaurant)

Interface:
- enqueue: put an item into the queue
- dequeue: take an item out of the front of the queue

```
var queue =[];
queue.push(10);
queue.push(20);
queue.push(30);
// queue is [10,20,30]
queue.shift()
// queue is [20,30]
```

We also have unrestricted data structures, including: 
* Arrays
* Hash tables
* more

Keyboard Shortcuts: good to know
---------------------

1. command + l --- Select line(s)
2. command + ctrl + (up / down) --- Move selection up / down
3. command + ([ or ]) --- Indent selected code
4. command + shift + v --- Paste & Indent
5. command + shift + p --- Open sublime command palette
6. command + option + (1 or 2 or 3 or 4) --- Split screen
7. command ~  --- Tab between windows of same app (not just sublime)


Quick notes on Hoisting
---------------------

Variable hoisting: JS moves variables up. 
Function hoisting: entire function statements get hoisted, get moved to the top.



