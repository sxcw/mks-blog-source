---
title: Day 25 is Express  
tags: 
- during-bootcamp
- sessionID
comments: true
date: 2016-06-28
---
After the express sprint, I have better understanding of how to build a login box. Session IDs and cookies are not longer scary... wait how can cookies be scary?? 



Notes
-------------------
* Time complexity for bubble sort: quadratic at worst, linear at best 
* `truncate()`: remove all rows, remove all data from the table
* `err && reject(err) || resolve(res)`
* A session gives the user the convenience of to signing in once (as opposed to providing their username/password on every request).
* The server stores a session id and a user id in the session. On each HTTP request: The client sends its session id. The server look up a session that has an id matching what the client sent. Having found the session, the server reads the user id in the client's session. If a user id is present, then the client is signed in as that user. Otherwise, the client is not considered signed in.
* A cookie lives on the user's computer, so technically a user can edit their own cookie values. In this case, a user could set admin: true in their own cookie before making another request to the server, effectively bypassing the server's security logic.
* Managing group dynamics avoids merge conflicts
* `git rebase`: look at the feature branch, merge the changes from remote and try re-applying your features
* Any bug fixes or adding new features: working on a branch, rebase and do a pull request
* NEVER PUSH TO THE REMOTE MASTER when working in a team