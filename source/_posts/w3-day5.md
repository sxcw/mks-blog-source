---
title: Day 16 is React
tags: 
- during-bootcamp
- react
comments: true
date: 2016-06-17
---

First day of React. Definitely much more complicated than Mithril. 

React First Look -- notes from react.js program
--------------

<h3> Terminology </h3>

* React router: allows us to map components to certain urls
* Webpacks: bundle all code into one file for me. Webpack, at its core, is a code bundler. It takes your code, transforms and bundles it, then returns a brand new version of your code.

1) Webpack needs to know the starting point of your application, or your root JavaScript file.

2) Webpack needs to know which transformations to make on your code.

3) Webpack needs to know to which location it should save the new transformed code.

* Bable: transform JSX into Javascript that browsers can understand
* Axios: make HTTP requests
* package.json will, among other things, keep track of which packages or modules you've installed in your project
*  `--save flag` : what that does is it saves jQuery to our `package.json` file as a dependency. Without that, jQuery would have been installed into our node_modules folder but not saved to the package.json file.



<h3> React Virtual DOM </h3>

* React can keep track of the difference between the current virtual DOM (computed after some data changes), with the previous virtual DOM (computed befores some data changes). React then isolates the changes between the old and new virtual DOM and then only updates the real DOM with the necessary changes.
* Signal to notify our app some data has changed: Re-render virtual DOM -> Diff previous virtual DOM with new virtual DOM -> Only update real DOM with necessary changes.
* Workflow: entry --> Babel loader --> output it
