# Stateful VS Stateless

## Session :
A temporary and interactive information interchange between two or more communicating devices, or between a computer and user.

## 1. Session based authentication:
After authentication, a session id is stored in the cookie, and that id is cross referenced with a database which contains all the user information, such as username.

## 2. Token based authentication
With token based authentication, claims of the user are stored in a jwt, and there is no need to cross reference a database which stored details about the user's session, as its all in the jwt.

Hint: sensitive information should still not be stored in a jwt.

------------

## Session based authentication diagram:
<img src='https://dzone.com/storage/temp/4804843-flow-cookie-session-large.jpg'>



## Token based authentication diagram:
<img src = 'https://camo.githubusercontent.com/52a690dc90ea0ce69ebfd3d19f1c1abfaeb70bb8/68747470733a2f2f692e696d6775722e636f6d2f4f434435414a422e706e67'>


------------

## What are the advantages and disadvantages of each ?


### Advantages of Session based authentication:
* More detailed data can be referenced to a session ID in a cookie.


### Disadvantages of Session based authentication:
* Requires big database.
* Difficult to scale when more than one server.


---------------

### Advantages of token based authentication:
* Light-weight.
* You do not need to append database.
* you can still set max-age and then on verify it will not approve if it's expired
.

### Disdvantages of token based authentication:
* Header and payload are only encoded, not encrypted.
* For more sophisticated websites, you may still need to store session IDs to reference session activity.



> By: Mohannad, Ali, Ons and Donia