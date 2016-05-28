---
title: Birthday Celebration with JS Koans
date: 2016-04-19 17:34:08
comments: true
tags: pre-bootcamp
---

Birthday celebration with JS Koans. My 28th birthday. Best to celebrate it with something fun -- JS Koans. Ryan and I started working on the Koans. They are great review practices, reinforcing our JS fundamentals.
                           
I was confused about the JS sorting function, and Ryan's clarification helps: 

`Array.sort()` sorts the array based on what the expression evaluates to. If the expression evaluates to a negative number, the first argument will be moved to the left and the second arugment moved to the right, if the expression evaluates to 0, there will be no change, **if the expression evaluates to a positive number then the first arguement will be moved to the right and the second aruguement moved to the left**.

Consider the following array: `[1, 5, 3]`. If the expression compares `a - b`, because `1 - 5` is `-4` then a will be moved to the left and b to the right. However, if the expression was `b - a`, then the expression would evaluate to `4` and b would then be shifted to the left and a to the right => `[5, 1, 3]`
