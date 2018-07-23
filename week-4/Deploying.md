# Depolying

## What is Cloud Computing?
Database storage, applications, and other IT resources through a cloud services platform via the internet

#### There are three ways for cloud computing:
* **SaaS**: Software as a service.
* **PaaS**: Platform as a service.
* **IaaS** : Infrastructure as service.

<p align="center">
  <img src="https://img.eztalks.com/cloud/types-of-cloud-services.png">
</p>

---
## What is PaaS? 

Platform as a Service, often simply referred to as PaaS, is a category of cloud computing that provides a platform and environment to allow developers to build applications and services over the internet. PaaS services are hosted in the cloud and accessed by users simply via their web browser.

---
## Why is it useful to be able to deploy your code to a cloud platform, rather than running it locally? 

Software developers, web developers can all benefit from PaaS:

**Software developers :** can take advantage of a PaaS solution to build an application which they are planning to offer over the internet or software to be sold out of the box.

**Web developers** can use individual PaaS environments at every stage of the process to develop, test and host their websites

**Businesses** can develop their own internal software, particularly to create distinct ring-fenced development and testing environment

---
## What services are there that can provide you with a platform for your code?
Alpha7 **-** Amazon Web Services **-** AppScale **-** Box **-** Bluemix **-** Cloud Foundry **-** Cocaine (PaaS) **-** Engine Yard  **-** Helion **-** GE Predix **-** Google App Engine **-** GreenQloud **-** Heroku **-** Inktank **-** Jelastic **-** Mendix **-** Microsoft Azure **-** MindSphere **-** Oracle Cloud **-** OutSystems **-** openQRM **-** OpenShift **-** PythonAnywhere **-** RightScale **-** Force.com **-** SAP Cloud Platform **-** VMware vCloud Air **-** WaveMaker

---
## Deploy a simple server to Heroku as a demo.

Heroku is a cloud platform that lets companies build, deliver, monitor and scale apps — we're the fastest way to go from idea to URL, bypassing all those infrastructure headaches.

[Heroku Getting Started with Node.js](https://devcenter.heroku.com/articles/getting-started-with-nodejs)

1. install the Heroku Command Line Interface.
~~~
sudo snap install heroku --classic
~~~
2. Log in using the email address and password you used when creating your Heroku account:
~~~
heroku login
~~~
3. clone the repo in your project [e.g node-js-getting-started]
~~~
git clone https://github.com/heroku/node-js-getting-started.git
cd node-js-getting-started
~~~
4. Create heroku app:
~~~
heroku create
~~~
5. Deploy to heroku:
~~~
git push heroku master
~~~
6. Open your app in the browser:
~~~
heroku open
~~~

---

## Environment variables 

Environment variables are the best way of storing sensitive data like API Keys, Login Credentials and Database Passwords.

### Why might some variables in your code need to change for different environments?

We needed a simple/reliable way of managing environment variables; and being able to share a configuration file among the team (without committing it to GitHub!)

### What modules might you use to help manage environment variables?

env2 is our solution.
env2 allows you to store your environment variables in an env.json or a .env file which gets loaded when your app starts.

All the entries in the env file are exported as environment variables available as keys in the process.env object.

#### In the root dir 

```shell
toch config.env
```
**example**

```javascript
export MY_KEY = '4638dc94ad7887e67dc768fd6a6c909c'
````
#### Install ```env2``` from ```npm```
```shell
npm i env2 -D
```
#### Use in your Code
Then in your script/module:

```javascript
const env = require('env2')('./path-to-your/.env');
```

then use  
```use process.env.MY_KEY```
then add thiskey in ```heroku.com``` 

