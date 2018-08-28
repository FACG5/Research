# Session-management in Express

## What are sessions?

A session can be defined as a server-side storage of information that is desired to persist throughout the user's interaction with the web site or web application.

---

## What are the different ways of managing sessions in express?

There are two broad ways of implementing sessions in Express – using cookies and using a session store at the backend. Both of them add a new object in the request object named session, which contains the session variables.

1. **Express-session:**

A session store is a provision for storing session data in the backend. Sessions based on session stores can store a large amount of data that is well hidden from the user.
~~~
npm install express-session
~~~
> Note Session data is not saved in the cookie itself, just the session ID. Session data is stored server-side.

2. **Cookie-session:**

Using the fact that cookies can store data in the users browser, a sessions API can be implemented using cookies. Express comes with a built-in middleware called cookieSession, which does just that.
~~~
npm install cookie-session
~~~

---

## Create a minimal example of how to set up a session (FYI: pseudo code is fine)

```javascript
const express = require('express');
const session = require('express-session');
const app = express();

app.use(session({
    secret: 'sessionTesting'
}));

const getRandomInt = (max) => {
    return Math.floor(Math.random() * Math.floor(max));
}

app.get('/', (req, res) => {
    if (!req.session.sid && !req.session.visitCount) {
        req.session.sid = getRandomInt(10000);
        req.session.visitCount = 1;
        console.log("logs : id: ",req.session.sid,'visitCount : ',req.session.visitCount);
        res.status(201).send(req.session);
    } else {
        req.session.visitCount += 1;
        console.log("logs : id: ",req.session.sid,'visitCount : ',req.session.visitCount);
        res.status(200).send(req.session);
    }
})

app.listen(3000, () => {
    console.log('Listining on port 3000');
})
```
---


#### source:

[https://nodewebapps.com/2017/06/18/how-do-nodejs-sessions-work/](nodewebapps.com)

