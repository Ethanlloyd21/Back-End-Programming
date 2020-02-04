# Back-End-Programming

A repository to host various file types an an effort to organize the topics covered since Project-One completion

## Node.js

#### Learning Objectives

1. Client-Server Model
2. Run Node.js applications
3. Import standard library packages
4. Initialize projects and install modules using npm
5. Build CLI applications with Inquirer

#### Client-Server Model

###### Understanding the Client

"A client is a piece of computer hardware or software that access a service made available by a server. It can be a desktop computer, laptop, mobile device, and more." -slide deck

###### Understanding the Server

"Depending on the context a server is both a physical hardware and a software that _"hears"_ requests from users and returns something. For instance, an HTML or image file, or it could complete a process."

"In modern web applications, there is constant back-and-forth communication between the visuals displayed on the user's _browser_ (**the front end**) and the data and logic stored on the _server_ (**the backend**) - slide deck

![The Client Server Model]('./Client-Server-Model.png')

###### So, what is Node.js?

"**Node.js is an open source, cross-platform JavaScript runtime environment designed to be run outside of the browser.**

It is a general utility that can be used for a variety of purposes including asset compilation, scripting monitoring, and **most notably as the basis for web servers**. -slide deck

###### How do I use Node.js?

###### Node.js Random

- The process object

"The process object is a `global` that provides information about, and control over, the current Node.js process. As a global, it is always available to Node.js without using `require('process')`

So, what is that `process.argv` all about?

"Passing in arguments via the command line is an extremely basic programming task, and a necessity for anyone trying to write a simple Command-Line Interface (CLI). In node.js, as in C and many related environments, all command-line arguments recieved by the shell are given to the process in an array called `argv`

**`argv`** is short for **argument values**

Example:

**Simple Form**

argv.js file containing :

```
console.log(process.argv)

```

Run the following in your shell :

```
$ node argv.js one two three four five
['node',
'/home/avian/argvdemo/argv.js',
'one',
'two',
'three',
'four',
'five' ]

```

"There you have it - an array containing any arguments you passed in. Notice the first two elements- node and the path to your script. These will always be present- even if your program takes no arguments of its own, your script's interpreter and path are still considered arguments to the shell you're using."

**More Complex**

argv.js file containing :

```
const myArgs = process.argv.slice(2);
console.log('myArgs: ', myArgs);

```

would return :

```
$ node argv.js one two three four
myArgs:  [ 'one', 'two', 'three', 'four' ]

```

then you can manipulate your args :

```
const myArgs = process.argv.slice(2);
console.log('myArgs: ', myArgs);

switch (myArgs[0]) {
case 'insult':
    console.log(myArgs[1], 'smells quite badly.');
    break;
case 'compliment':
    console.log(myArgs[1], 'is really cool.');
    break;
default:
    console.log('Sorry, that is not something I know how to do.');
}
```

- Library packages

  **fs**

[fs readFile DOCS](https://nodejs.org/api/fs.html#fs_fs_readfile_path_options_callbacks)

fs is a Node library package used for reading and writing files.

```
'use strict';

const fs = require('fs');

fs.readFile('data.csv', 'utf8', function(error, data) {
  if (error) {
    return console.log(error);
  }
  console.log(data);
});

fs.writeFile('log.txt', 'hello world!', function(err) {
  if (err) {
    return console.error(err);
  }
  console.log('Success!');
});

fs.appendFile('log.txt', process.argv[2] + '\n', function(err) {
  if (err) {
    console.error(err);
  } else {
    console.log('Commit logged!');
  }
});


```

- Math Module Example

**File: index.js**

```
var maths = require('./maths');

var operation = process.argv[2];

var numOne = parseInt(process.argv[3]);
var numTwo = parseInt(process.argv[4]);

switch (operation) {
  case 'sum':
    console.log(maths.sum(numOne, numTwo));
    break;
  case 'difference':
    console.log(maths.difference(numOne, numTwo));
    break;
  case 'product':
    console.log(maths.product(numOne, numTwo));
    break;
  case 'quotient':
    console.log(maths.quotient(numOne, numTwo));
    break;
  default:
    console.log('Check your maths!');
}

```

**File: maths.js**

```
module.exports = {
  sum: function(a, b) {
    return a + b;
  },
  difference: function(a, b) {
    return a - b;
  },
  product: function(a, b) {
    return a * b;
  },
  quotient: function(a, b) {
    return a / b;
  }
};
```

**How to create your package.json file**

"From the command line

```
 run npm init.
```

Remember to run the command from within your working directory.
Follow the prompts and enter the following:

- package-name

- version number

- description

- entry point

- git repository

- keywords

- author

- license

When ready to install a package for use pull up the package.json in command line and run the package name as listed in [] :

```
npm install [package name] --save

```
