---
title: Day 51 is Refactoring Form  
tags: 
- during-bootcamp
- thesis
comments: true
date: 2016-08-05
---

I spent a lot of time tracking down a bug. The setState did not work as I expected-- it did not update the state. The problem was setState in react is not synchronous. To fix this, I would need to pass a callback so that it didn't run the function prematurely.  Placing most form validation logics in the component state also made my code messier, so I decided to re-factor the code by moving the logics to reducers. The user inputs and validation errors would be stored in Redux application state and are accessible anywhere in the form.  

