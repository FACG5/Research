
 #  Engineering # 
 
---------


 #  Modules 
  ## Why is it a good idea to modularise your code ?
  
 *  #### The most important benefit of modularizing is that Modularized code is easy to understand.

 * #### By modularizing code, you can make the code reusable and you can replace parts of it easily witout affecting other parts of the code.
 
 ## What are require and module.exports?

require: it's used to load modules. which is why its return value is typically assigned to a variable:
```
var misc = require('./misc');
```
### however a a file can't access the functions and variables in another file, require alone is useless
###  To expose things we use module.exports and export everything we want.

```
ar x = 5;
var addX = function(value) {
return value + x;
};
module.exports.x = x;
module.exports.addX = addX;
_
```
## Why can't you use them in the browser?
#### browsers don't support node.js libraries

## How might you modularise client-side code?
by dividing the code
into independent smaller chunks of code that can function on their own regardless of the rest of the code
which makes it easier to understand

-------------
 # Asyncronous functions

 *  #### Synchronously, in which the script stops and waits for the server to send back a reply before continuing. 
  * #### Asynchronously, in which the script allows the page to continue to be processed and handles the reply if and when it arrives.


  ## Why should you use asyncronous forms of functions wherever possible in Node? 

  ####  Processing your request asynchronously avoids the delay while the retrieval from the server takes place because your visitor can continue to interact with the web page; the requested information will be processed in the background, and the response will update the page as and when it arrives. 



## What are error-first callbacks, and why is it important to follow that pattern in your own code?

#### The “error-first” callback, also known as an “errorback”, “errback”, or “node-style callback”
#### The callbacks may not expect any data and the err is the only parameter that they take, and sometimes the functions expect more than one value on success
```
request(url, (err, res, data) => {
  if (err) {
    // you have error
  } else {
    // you have both res and data
  }
});
```

 ## Why should you avoid using throw in callbacks?
 #### exceptions are only a synchronous mechanism, which is logical: in an asynchronous environment, the exception could be thrown when the handler block is already out of scope and thus meaningless.
 #### Asynchronous exception is uncatchable because the intended catch block is not present when the asynchronous code is executed. Instead, the exception will propagate all the way and terminate the program.

## When might you use the syncronous form of a function instead?

 #### When the functions don't require a time to execute, and it don't have a fumctions like setTimeout() or anything require a time more than the others.

------

# Input/output (the fs and path modules)

## What kind of tasks does the fs module enable you to perform that you wouldn't be able to in the browser?

#### The File System module provides a way of working with the computer's file system.



#### To include the File System module, use the require() method:



```
var fs = require("fs");
```
1.  #### readFile() method is used to read files on your computer.

    * fs.readFile()
```

http.createServer(function (req, res) {
  fs.readFile('demofile1.html', function(err, data) {
    res.writeHead(200, {'Content-Type': 'text/html'});
    res.write(data);
    res.end();
  });
}).listen(8080);
```
2. #### Create Files : The File System module has methods for creating new files :
    * fs.open()
    * fs.writeFile()
    * fs.appendFile() : appends specified content to a file. If the file does not exist, the file will be created
```
    fs.appendFile('mynewfile1.txt', 'Hello content!', function (err) {
  if (err) throw err;
  console.log('Saved!');
});
```

3. #### other method 
   * To delete a file with the File System module,  use the fs.unlink() method.

   * To rename a file with the File System module,  use the fs.rename() method.

## What are some of the issues of working with paths when accessing a file system? 

```
root
-config
--dev
---foobar.json
-helpers
--helper1.js
----------------
var fs = require('fs');
var path = require('path');

var jsonPath = path.join(__dirname, '..', 'config', 'dev', 'foobar.json');
var jsonString = fs.readFileSync(jsonPath, 'utf8');
```


## How does the path module help, and why should you use it instead of manually writing file paths as strings?

#### When multiple, sequential path segment separation characters are found (e.g. / on POSIX and either \ or / on Windows), they are replaced by a single instance of the platform specific path segment separator (/ on POSIX and \ on Windows). Trailing separators are preserved.


--------
# Working with URLs (the url and querystring modules)

##  What is a urlObject and how is it structured?
#### A URL string is a structured string containing multiple meaningful components. When parsed, a URL object is returned containing properties for each of these components.
 ![url](https://files.gitter.im/OnsNader/Tagm/Screenshot-from-2018-07-23-14-51-17.png)


## Why is it important to be able to turn JavaScript objects into querystrings and back again?
#### query string turns the string input into object. So it is understandable and readable. We change the object into a string so the server understands it and we can send a request and get a response.

## Why is it a bad idea to build a query string manually from other strings (think about URL encoding and escape characters)?
#### if we didn't parse the query string into an object, the url would contain many symbols and characters each with a special meaning. So, if i on my own manually wrote the string form of the object i can misuse or forget a character I would send a different request than required and get a different response than wanted.
------------
## By : 
#### Ibrahem , Mohannad , Ons , Asala 
