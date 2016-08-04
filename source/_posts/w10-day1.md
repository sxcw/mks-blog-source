---
title: Day 47 
tags: 
- during-bootcamp
- thesis
- redux-form
comments: true
date: 2016-08-01
---

I have been working on the create event form for the last few days. I used a third party library called redux form. It has a lot of information and examples in the documentation but sadly because react is changing rapidly, some part of the information does not stay up to date. To made my form work, I spent a lot of time googling. A few people has similar issues and they provided some workarounds. Some issues still don't have clear answers. 

Redux Form Intro
------------------

* Redux form has 2 parts: Redux reducer and React component decorator
* Redux form basically takes care of all the form reducers I need. All I have been written are: form component, action creator, and tests
* The version of the redux form I am using is 6.0.0-rc.3. Version 5 is no longer compatible with react
* The best way to learn: first install redux form by typing in `npm install --save redux-form` in the terminal and read the Getting Started and Simple Form sections of the <a href="http://redux-form.com/6.0.0-rc.3/docs/GettingStarted.md/" target="_blank"> official documentation </a>.  It shows the version number in url, rememeber to read the right version of documentation. There are many significant differences between 6.0.0-rc.3 and older versions like V4. 





