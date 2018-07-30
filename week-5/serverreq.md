## Sending Requests to External APIs
* Connecting to external APIs is easy in Node. You can just require the core HTTP module and start sending requests.

* Of course, there are much better ways to call an external endpoint. On NPM you can find multiple modules that can make this process easier for you. Fo​r example, the two most popular ones are the:
### 1. request
### 2. superagent
Both of these modules have an error-first callback interface

```
npm install request
```

```js
const request = require('request')
```
Sending a GET request is as simple as:
```js
const options = {
  method: 'GET',
  uri: 'https://risingstack.com'
}
​
request(options)
  .then(function (response) {
    // Request was successful, use the response object at will
  })
  .catch(function (err) {
    // Something bad happened, handle the error
  })
```
If you are calling a JSON API, you may want the request-promise to parse the response automatically. In this case, just add this to the request options:

```js
json: true
```

POST requests work in a similar way:
```js
const options = {
  method: 'POST',
  uri: 'https://risingstack.com/login',
  body: {
    foo: 'bar'
  },
  json: true
    // JSON stringifies the body automatically
}
​
request(options)
  .then(function (response) {
    // Handle the response
  })
  .catch(function (err) {
```

now Lubna will explain her example on request modules
then
Ali will explain his example on superagent module
