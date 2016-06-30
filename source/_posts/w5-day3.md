---
title: Day 26   
tags: 
- during-bootcamp
comments: true
date: 2016-06-29
---
Feeling tired this week even after 7 hours of sleep, and no tea can really wake me up.  The joy of learning is still there though...it's just I need to constantly remind myself to focus.  


Notes
-------------------
* Deployment (with Heroku) : take a project that works on my laptop and make it work on the cloud (servers running on the internet, hosted servers, accessible via the internet)
* Heroku: app hosting platform, we can deploy with `git push`. Originally built for Ruby on Rails. Easy scaling
* Configuration: makes my app behave slightly different in different environments. Environment variables are in the terminal ('bash'). Everything is a string in bash. 
* `process.env.NODE_ENV` 
* MongoDB: Document-oriented database (as opposed to relational database), storing JSON objects.  Collections(arrays). Each object doesn't have a schema. (no table schemas) Less strict, more flexible, but also easier to insert wrong data. Can write/ read more data in seconds. 
*`$PATH` : represent a list of folders separated by colons. Show all the executable files (run which `git` to see where git lives )
* Build systems: get source code and package it up. Bundling up JS files for the browser --> so that browser can run JS faster
* HTTP request is slow, and every `<script>` tag is one extra HTTP request. Serve one gaint JS file instead.
* Many build systems: browserify, webpack,jspm, broccoli, bower, require.js
* Transpiling (compile almost JS to JS): from ES6 to ES5 so all browsers can run the JS 
* Task Runners: a program to run tasks, many task runners: grunt, gulp, jake, cake. Only useful for complicated tasks with lots of dependencies 
*  Some useful tasks: JSHINT, UGLIFY
* Grunt: configuration; Gulp:take a function and pipe it to another function
* Using a separate database for a test environment allows you to clear your test database before running your test suite. Production servers might need to listen on different ports. You usually want to reload code every request in development, but employ heavy caching when in production.
* When you run a command, your terminal will look in each colon-separated folder in your PATH for a file that matches the executable you're trying to run. For example, when you run git status, your terminal iterates through each folder in your PATH until it finds a file named git. When it finds it, it runs that file with status as an argument.
