---
title: Day 22 starts SQL
tags: 
- during-bootcamp
- SQL
comments: true
date: 2016-06-24
---

Journey to SQL begins!


Notes
-------------------

* Relational (SQL) database: A collection of tables
* Table: A collection of rows (records)
* Table Schema: A strict set of rules for table column types, sizes, etc.
* SQL columns can only have: numbers, strings, dates
* RDB is stricter form of spreadsheet, can not freely move things around
* a row is like a js object (or a hash table)
* Always have ID so we can direcly reference that row

<h3> One-to-many relationship</h3>
* A user has many comments === a comment belongs to a user
* 'belong-to relationship': that table needs a FOREIGN KEY (a label, a sticky note that claims ownership)

<h3> Many-to-many relationship</h3>
* A student has many cohorts (as student or fellow)
* A cohort has many students 
* 'Joint table'
* Normalize: Don't duplicate any data, so we only need to change data at one spot, not multiple places. <--> 'Denormalized' is good for caching, good for performance 
* polymorphic associations

