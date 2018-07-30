# Node Shell project

This search follow the Node-Shell-Workshop, So we using the instructions [here](https://github.com/foundersandcoders/Node-Shell-Workshop/blob/master/PROJECT.md)

The main goal in this research, We learned how build a test output formatter.
A test output formatter is a program that when you pipe the results of your tests into, will read the results of those tests and reformat them as output. We will use tape for our tests in this exercise.

## Task
Make your own output formatter!

### Step to solve this project :

1. **Clone** [this](https://github.com/foundersandcoders/Node-Shell-Workshop) repo and go into the **`project`** folder
2. **In terminal**
    1. You'll need to create a **`package.json`** and install **tape**
    
         ~~~
         npm init
         ~~~
         ~~~
         npm i tape -D 
         ~~~

   2. Create the file output-formatter.js

       ~~~
       touch output-formatter.js
       ~~~
  
   3. Format should be implemented like so  in **`package.json`** file

       ~~~
       node test.js | node output-formatter.js
       ~~~
    
   4. Run the code   
   
      ~~~
      npm test
      ~~~

3. Now we bulid the **`output-formatter.js`** file
   
   1. We use chalk module to change the color in test
      ```javascript
      const chalk = require('chalk');
      ```
      example : 
      ```javascript
      consol.log(chalk.blue('Hello') + ' World' + chalk.red('!'));
      ```
    2. Now we want read the result of test file
          ```javascript
            const readline = require("readline");
            let rl=readline.createInterface(process.stdin,{});
            rl.on('line', (data) => {
                console.log(data);
            });
          ```
    3. t is time for your creativity to change your test output
    
--- 
    
## Example to our work **`output-formatter.js`**

```javascript

```

---
### By : 
* Asmaa
* Marwan
* Kanna'n
    
