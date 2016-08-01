---
title: Day 43 is Postgres Postgres and Postgres
tags: 
- during-bootcamp
- thesis
- postgres
comments: true
date: 2016-07-28
---

I fought with postgres for the entire morning today and finally fixed the problem by hours of googling and stack overflowling. 

Problem
-----------

I have <a href="http://postgresapp.com/" target="_blank"> Postgres.app</a> and <a href="http://www.enterprisedb.com/products-services-training/pgdownload" target="_blank">EnterpriseDB Installer</a> installed and for some reason, both of them are competing for the same port. The error message I kept getting was: 

```
WARNING: could not create listen socket for "localhost" 
FATAL: could not create any TCP/IP sockets
```
I am not sure why the conflict happened. Even when I closed out the Postgres.app, the EnterpriseDB still complained about port 5432 was taken. I decided wiping out all the postgres programs and started from fresh.  

There are many ways to remove postgres, depending on how you installed it initially. I found <a href="http://stackoverflow.com/questions/8037729/completely-uninstall-postgresql-9-0-4-from-mac-osx-lion/9240197#9240197" target="_blank"> this stack overflow </a>  and <a href="http://hzchirs-blog.logdown.com/posts/142678-how-completely-uninstall-postgresql-9x-on-mac-osx" target="_blank"> this post </a> helpful. Note that you cannot drag Postgres.app to trash if it is still running. Make sure it stops and then kills it.  Checkout <a href="http://www.uninstallmacapp.com/postgres-app-9-4-2-0-removal.html" target="_blank"> this article </a> if you run into this issue. 

Time to Reinstall
----------------
Okay, now I can start fresh.  I am on a mac and using homebrew looks like the easiest.  

```
// first, check if you have homebrew installed
which brew
// update homebrew
brew update
```

Here comes the exciting part-- install postgres! 
```
brew install postgres
// check version installed
brew info postgres
```

```
// if brew services not installed
brew tap homebrew/services
// run postgres as background service
brew services start postgresql
```

Then I tried `initdb /usr/local/var/postgres` but got some warnings:

```
initdb: directory "/usr/local/var/postgres" exists but is not empty If you want to create a new database system, either remove or empty the directory "/usr/local/var/postgres" or run initdb with an argument other than "/usr/local/var/postgres".
```

To fix this, we need: 
```
initdb `brew --prefix`/var/postgres/data -E utf8
```
The data directory is under postgres home directory, by doing the above command, log file can be shared.  I am still not sure why this fixed the issue but I am glad it did. 

Great, postgres is up and running, now is time to create database.

```
// create database
createdb YOUR_DATABASE_NAME
```

```
// drop database
dropbox YOUR_DATABASE_NAME
```

```
// run database
psql YOUR_DATABASE_NAME
```
