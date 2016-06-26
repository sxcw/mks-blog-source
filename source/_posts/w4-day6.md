---
title: Day 23   
tags: 
- during-bootcamp
- SQL
comments: true
date: 2016-06-25
---

Notes
-------------------

<h3>Writing SQL </h3>

* 'TEXT' : a string of any length
*  How to uniquely identify the row ==> PRIMARY KEY does that for me, it also creates an index
*  Column indexes: makes querying by that column faster, and allows SQL to jump to that row, instead of iterating over all rows, trades disk space for speed (column index -> is like creating a hash table for that column)
*  `ASC` : auto-increment (useful for creating ID)
* `FOREIGN KEY (user_id) REFERENCES users(id)` , user_id and id must match

* Q: what are all the comments alice has made? 
`SELECT * FROM comments WHERE user_id = 10; `

* Q: what are all the latest 5 comments alice has made? 
```
SELECT * FROM comments 
	WHERE user_id = 1
	ORDER BY created_at DESC (ASC)
	LIMIT 5; 
```