**npm is Node's package manager. It's a repository of hundreds of thousands of useful pieces of code that you may want to integrate with your Node project.**
npm also has a command line tool that lets us easily install, manage and run projects.

* Dependencies: What is a dependency? Why might you want to use a dependency in your project, rather than writing the code from scratch? What have traditionally been some of the issues with managing dependencies?

__In code, there are three kinds of dependencies:__
1. Dependencies we control
This is code written and owned by us or our organization.
2. Dependencies we don’t control
This is code written by a third party vendor or open-source software community.
3. Dependencies once removed
These are the code dependencies our third-party code dependencies depend upon. (Say that three times fast!)
___
__Why third-party code dependencies are good__
A large portion of your web application exists to solve common problems: authentication, authorization, data access, error handling, navigation, logging, encryption, displaying a list of items, validating form inputs, and so on...

Regardless of which technology stack you use, there’s a good chance that common solutions to these problems exist, and are available as libraries that you can easily acquire and plug-in to your codebase. Writing any of this stuff completely from scratch is generally a waste of time.
* Third-party code — in the form of libraries — allows you to quickly implement those commoditized features of your app, so you can stay focused on your “secret sauce.”
___

**To specify the packages your project depends on, you need to list the packages you'd like to use in your package.json file. There are 2 types of packages you can list:**
* **"dependencies"**: These packages are required by your application in production,These are your normal dependencies, or rather ones that you need when running your code (e.g. React or ImmutableJS

~~~~
  npm install <package-name> --save
~~~~
* **"devDependencies"**: These packages are only needed for development and testing,
Dependencies that you need at some point in the development workflow but not while running your code (e.g. Babel or Flow).
~~~~
  npm install <package-name> --save-dev
~~~~

* **peerDependencies**
* **optionalDependencies**
* **bundledDependencies**

___
__Why third-party code dependencies are bad__
Take a look at any non-trivial web-app built in the last couple of years and you’ll be absolutely astounded by the amount of code that actually comes from a third-party library. What if one or more of those third-party libraries changes drastically, or disappears, or breaks?
__Three Core Problems of Dependency Management__

Problem #1: Lack of End-to-End Visibility
Problem #2: Bad Solutions for Lack of Visibility
Problem #3: Teams’ Own Unique Perspectives

[source](https://medium.freecodecamp.org/code-dependencies-are-the-devil-35ed28b556d)

# NPM:

## What is a package manager?
is a package manager for JavaScript, it has hundreds of thousands of useful pieces of code that you may want to integrate with your Node project.
* you can install, share code
* you can manage dependencies in your projects

## What is package.json?
file holds various metadata about the project. used to give information to npm that allows it to identify the project as well as handle the project's dependencies

##what is npm init?

is the first command you need to know to create an node project it will add a file called package.json

## How do you use an installed package in your code?
you can requiring modules like this
~~~~
var express = require('express');
~~~~


# npm install:

## What is the difference between installing a package globally, installing it as a dependency, or installing it as a development dependency?
## When would you use each? How would you do each in the command line?
## Why is it normally a bad idea to install a package globally?

When using NPM, the first thing to do is an
npm init,
which will set up a package.json file for us based off our answers to its survey. This package.json describes our module, and in it we can see a list of all installed dependencies and devDependencies that we have installed and added to our project.


The difference between these two, is that devDependencies are modules which are only required during development, while dependencies are modules which are also required at runtime.


To save a dependency as a devDependency on installation we need to do
**npm install --save-dev**
instead of just an **npm install --save**
A nice shorthand for installing a devDependency is
~~~~
npm i -D.
~~~~
The shorthand for saving a regular dependency is
~~~~
npm i -S
~~~~



**global install:**
aliased to the -g command line switch.
globally —- This drops modules in {prefix}/lib/node_modules, and puts executable files in {prefix}/bin, where {prefix} is usually something like /usr/local.
locally —- This installs your package in the current working directory. Node modules go in ./node_modules
when to use:
* If you’re installing something that you want to use in your shell, on the command line or something, install it globally,
* If you’re installing something that you want to use in your program, using require('whatever'), then install it locally, at the root of your project.
**Why Shouldn’t I Install Dependencies Globally?**


## Where does NPM install packages?##

**Global libraries**
You can run npm **list -g** to see where global libraries are installed.

On Unix systems they are normally placed in /usr/local/lib/node or /usr/local/lib/node_modules when installed globally. If you set the NODE_PATH environment variable to this path, the modules can be found by node.

Windows XP - %USERPROFILE%\Application Data\npm\node_modules
Windows 7, 8 and 10 - %AppData%\npm\node_modules

**Non-global libraries**
Non-global libraries are installed the node_modules sub folder in the folder you are currently in.

You can run **npm list** to see the installed non-global libraries for your current location.


## Why is it important to make sure that installed packages aren't included in your repositories?

This is a good time to mention that you want to keep your node_modules folder off Github.
There can be hundreds of thousands of files in this directory, which can make for some ugly commits.
It can also take up a huge amount of space on something like Github as this folder can easily exceed 100MB for applications with lots of dependencies.


## How do you prevent Git from including these files in your repository?


A .gitignore file is a way to tell Git to leave certain things alone.

If you are creating a repository on Github then you can use the 'Add .gitignore file' dropdown to automatically generate a variety of .gitignore files for different kinds of projects. You'll want to choose 'Node' here.

If you're working locally you can create a file called .gitignore at the root of your project and add node_modules.
