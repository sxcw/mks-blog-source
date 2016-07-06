---
title: Day 24 Brings Another Bright Week   
tags: 
- during-bootcamp

comments: true
date: 2016-06-27
---

Another bright week! I am going to learn authentication, deployment and angular this week.  A lot of content packed into 6 days. I will be very struggling but I am still looking forward to the challenges! 



Notes
-------------------

* `.use` returns a middleware
* middleware function: just a function, between the start of the class and endpoint

```
app.use(function(req,res,next) {
	next();
})
```

* redirect: set a specific header, send another `GET` request
* Many users re-use passwords across multiple websites. Hackers want these passwords to use them for sensitive websites, such as bank accounts. Hashing better protects your user's passwords in the case your database gets compromised. By hashing a password, the original password is much harder to obtain.
* Dictionary attack : A hacker pre-generates a long list of common passwords. When the hacker compromises your database, he compares your password hashes against his pre-generated list. If any match, he instantly knows the password for that user.
* Adding salt: A hacker could not have a pre-generated list against salted password hashes; they would need to re-generate an entirely new list using your server's salt.
* A hacker needs to re-generate their list of common passwords when a salt is involved. Because bcrypt is designed to be slow, this generating process will take them a very long time.
* session id points to the session itself (might be an object) --> give client the key to the session, not the entire session. (he doesn't need to know he is user_id 10)
* `http`: send everything including session id in plain text. 

<h3>Sessions</h3>
* Client: Only get access to session id, provides session id when doing account-sensitive actions (updating user's credit card)
* Server: generate a session (and id) when client signs in, only exposes session id. 
* Cookie: a small file, get sent to the server. Every cookie is restricted to that particular domain. Cookie is a collection of key value pairs. One Cookie per domain
* Delete cookie --> rip off key card


