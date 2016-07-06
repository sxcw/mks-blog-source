---
title: Day 18 is the Beginning of Server
tags: 
- during-bootcamp
- react
- Node.js
comments: true
date: 2016-06-20
---

Started server side from today!


React.js Program Notes
-----------------------

* The reason for the consistency and predictability is because pure functions have the following characteristics.
- Pure functions always return the same result given the same arguments. 
- Pure function's execution doesn't depend on the state of the application.
- Pure functions don't modify the variables outside of their scope.


Node.js
-------------------

* `Node.js` is Javascript runtime, allowing us to run Javascript on the server side
* CommonJS (the 'require' stuff): also available via browserify, commonJS takes each file and make each of them an individual scope. 
* require is a function call, it returns an object (every single file return implicitly return `module.exports`) Implicitly put everything of a file to `module.exports={}`
* `require` points to what `exports` assigns to
`var mod= require(./lib/my-module)` `module.exports={}`
* Multiple files may require the same file
* File runs once and it will be remembered next time we request
* `./` ==> same folder. Anytime we require a folder, need to start with a `.`
* `../` ==> go up a directory
* no dot ==> check for npm installed module, or a built in module for node like `http`
* 3000-10000 (3000,4000,5000,6000)
* Non-blocking nature: request.on('data')-- > look this up
* write response status code and headers `response.writeHead`
* wrtie response body `response.end()`	
* npm install nodemon `nodemon demo.js`
* server: receive a request, look at endpoint(request.url), send something back
