---
title: Day 42 is Setting Up Rules
tags: 
- during-bootcamp
- thesis
- git
comments: true
date: 2016-07-27
---

The past projects taught us how important it is to set up a git workflow that everyone agrees to follow before we even start the project. We created a dummy repo for everyone to practice git workflow. 

Git Workflow for Team
-----------

My previous group agreed on doing `merge` so that we keep every single commits. The downside is the master looks a little bit messy.  This time, my group decided to do `rebase` instead of `merge` to keep master pristine. Below is our workflow:

1. open up an issue on zen hub
2. create a new branch with the number zen hub generates: `iss##` such as `iss5` , `iss30`
3. work and commit on that branch
4. `git pull --rebase origin master` to get the latest copy from remote origin. 
5. `git add {resolved conflicts}` and `git rebase --continue` to work through rebasing. 
6. when rebasing is finished, keep working on the issue branch, commit and `git push origin issue_branch`


