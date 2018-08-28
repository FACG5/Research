# Promises and Fetch

### What is a Promise?

A Promise is an object representing the eventual completion or failure of an asynchronous operation. Since most people are consumers of already-created promises, this guide will explain consumption of returned promises before explaining how to create them.

**Creating a Promise**

```js
const myFirstPromise = new Promise((resolve, reject) => {
  // do something asynchronous which eventually calls either:
  //
  //   resolve(someValue); // fulfilled
  // or
  //   reject("failure reason"); // rejected
});
```


### What is fetch and how do you use it?

The Fetch API provides a JavaScript interface for accessing and manipulating parts of the HTTP pipeline, such as requests and responses.
It also provides a global fetch() method that provides an easy, logical way to fetch resources asynchronously across the network.


Our fetch request looks a little like this:
 ```js
 fetch('./api/some.json')
  .then(
    function(response) {
      if (response.status !== 200) {
        console.log('Looks like there was a problem. Status Code: ' +
          response.status);
        return;
      }

      // Examine the text in the response
      response.json().then(function(data) {
        console.log(data);
      });
    }
  )
  .catch(function(err) {
    console.log('Fetch Error :-S', err);
  });
 ```




### What advantages do promises provide over callbacks, what are the downsides of using promises?
![](https://i0.wp.com/digitalfortress.tech/wp-content/uploads/2017/07/promises-vs-callbacks.png?w=785&ssl=1)

* **Readability**


```js
// Regular Callbacks
api1(function(result1){
    api2(function(result2){
        api3(function(result3){
             // do work
        });
    });
});

// Using Promises
api1().then(function(result1){
    return api2();
}).then(function(result2){
    return api3();
}).then(function(result3){
     // do work
});

```

With Callbacks, more the number of callbacks you chain, more difficult does it get to read and more difficult to debug as well.

Promises, on the other hand, offer much better readability allowing you to chain as many calls as you’d like. With the advent of ES6, flattening can also be easily achieved like this:

```js
api().then(result => api2()).then(result2 => api3()).then(result3 => console.log(result3));
```
* **Error Handling**

```js
// Regular Callbacks
api1(function(error1, result2){
    if (error1) {
      // log error
    } else {
        api2(function(error2, result2){
            if (error2) {
            // log error
            } else {
                api3(function(error, result3){
                    if (error2) {
                        // log error
                    } else {
                        // do work
                    }
                });
            }
        });
    }   
});

// Using Promises
api1().then(function(result1){
    return api2();
}).then(function(result2){
    return api3();
}).then(function(result3){
     // do work
}).catch(function(error) {
     //handle any error that may occur before this point
});
```
As you can see above, the solution with promises is pretty much like a try {} catch block but with regular callbacks its becomes a literal *callback hell.*

* **Parallel Execution**

With Promises, you can make simultaneous calls to the 3 apis and wait for them to be resolved. An intriguing use-case could be to make ajax calls in parallel instead of waiting for each one.

```js
Promise.all([api1(), api2(), api3()]).then(function(result) {
    // Do some work.
    // result is an array containing values of the three fulfilled promises.
}).catch(function(error) {
    // Handle error
    // Executes when at least one of the promises was rejected.
});

```
Parallel Execution is not natively possible with callbacks but can be integrated using async.parallel().

* **Integrated Error Handling**
Promises come with integrated error handling. The result of the computation might be that either the promise is fulfilled with a value, or it is rejected with a reason.

```js
promise.then(function(result){
    // do something
}).catch(function(error) {
    //handle any error that may occur before this point
}).then(function() {
    // do something whether there was an error or not
    // eg: hiding a spinner while performing an AJAX request
});
```
Errors are handled and propagated automatically in promise chains, so that you don’t need to care about it explicitly compared to plain callbacks.


So After all >> As you can see all the obvious advantages of using Promises, I would recommend all serious Javascript developers to migrate towards promises if not already 😉


### What are the downsides to using Fetch? i.e. what does fetch not do for you?
 ..........
