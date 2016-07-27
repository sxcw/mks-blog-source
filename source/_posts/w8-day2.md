---
title: Day 36 and Comes the Legacy!
tags: 
- during-bootcamp
comments: true
date: 2016-07-19
---

Greenfield project is over, and then we are handing it to other groups.  My group is interested in picking a paper scissors stone game project as the legacy project.  We will be adding features to that project for the rest of week. 


Update Node Today! 
-----------

I found out I had been using node version 5 (latest stable version) for a long time. It doesn't go well with ES6 features. It throws syntax errors when I use `let` or `const`.

```
SyntaxError: Block-scoped declarations (let, const, function, class) not yet supported outside strict mode
```

To fix this, I had to update node. Below are some handy commands to check node version and update node.

```
// check node version
node -v
```

```
// return a path like .nvm/versions/node/v5.0.0/bin/npm, where npm is installed
which npm
```

```
// browse available versions
nvm ls-remote
```

```
// install node version 6.3.0 (latest at this moment)
nvm install 6.3.0
```



