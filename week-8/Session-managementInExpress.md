# Session-management in Express

## What are sessions?

A session is a place to store data that you want access to across requests. Each user that visits your website has a unique session.  You can use sessions to store and access user data as they browse your application.

---

## What are the different ways of managing sessions in express?

We have many modules that we can in order to create new session:

1. Express-session:
~~~
npm install express-session
~~~

2. Node-session:
~~~
npm install node-session
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

