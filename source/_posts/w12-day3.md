---
title: Day 61 is Polish
tags: 
- during-bootcamp
- thesis
comments: true
date: 2016-08-17
---

I spent most time working on CSS today, making the form mobile responsive.  Stuck in a weird 'bug': Chrome kept adding a horizontal scrollbar there was a 10 pixels jump to the left when clicking on the 'More Options'.   I found out it was because of bootstrap `row` adding extra padding on the sides.  Removing the `row` class fixed it.  