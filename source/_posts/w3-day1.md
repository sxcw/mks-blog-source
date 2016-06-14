---
title: Day 12 
tags: 
- during-bootcamp
- HTTP
- API
- REST
comments: true
date: 2016-06-13
---

This week I will delve deeper into MVC by making 3 web apps, using Backbone or Mithril libraries.    

HTTP
--------------
Client: sends a request to server 

<h3> Request </h3>

* Endpoint: overall address that we request, method + url (Method includes `get` , `post` , `put/patch`(update data) ,`delete` ; url can be `/comments` , `users/5` , `/` --> root)
* Headers: see notes
* Body: any request sent to server goes to request body

Note #1: Get requests don't change data, only ask for data, so no request body
(endpoint: get/)
Note #2: status code 404 means endpoint doesn't exist
Note #3: post/put request almost always has a body(like a string of JSON). Must be specific in the header (`content-type`)
Note #4: only send in content-type if we have request body. 
Note #5: every time we hava a style tag or script tag means a new HTTP `get` request
Note #6: Q: When a server receives an HTTP request, how does the server know when the request headers stop, and when the request body (if any) starts? A: empty line seperating header and body
Again, need a request body if it's a get/put request
Note #7: url can have Query parameters  --> `/users/5?order=ASC&name=Alice`
Note #8: `curl`: make an http request from the terminal


Server: sends back a response
<h3> Response </h3>

* Status code: 200 great, 500 something broke on the server side, 400 client side broken
* Headers: key-value pairs, most important --> `content-type` : `text/html` ( server knows how to interpret the data)
* Body: the html text (the meat the server gives back)


Other
--------------
API: interface is a description of how you can interact with something 
* Code API: how we interact with code (array API: .push,.pop, .slice)
* REST API: how to interact with a web app, via HTTP
* Cross-site scripting: 
Inject: As a consumer of a website, I can write data to the website that is then consumed by the other people. Can happen in broswer/server layer
Escaping: Turning executable code to soemthing harmless
* REST: one of the ways we interact with servers that everyone has agreed upon. When interacting with a web resource, the way we interact with it demonstrates our intent. So there are verbs we can have when intereacting with servers, like `GET` (those verbs are foundation of REST)
REST: people agreed on what type of commands they can use and how to use them when interacting with servers.
Bower: front-end dependecies; npm: back-end dependencies 
* HTTP verbs tell the server what to do with the data identified by the URL.
* The HTTP client and HTTP server exchange information about resources identified by URLs.
