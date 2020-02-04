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

"A client is a piece of computer hardware or software that access a service made available by a server. It can be a desktop computer, laptop, mobile device, and more."

###### Understanding the Server

"Depending on the context a server is both a physical hardware and a software that _"hears"_ requests from users and returns something. For instance, an HTML or image file, or it could complete a process."

"In modern web applications, there is constant back-and-forth communication between the visuals displayed on the user's _browser_ (**the front end**) and the data and logic stored on the _server_ (**the backend**)

![The Client Server Model]('./Client-Server-Model.png')

###### So, what is Node.js?

"**Node.js is an open source, cross-platform JavaScript runtime environment designed to be run outside of the browser.**

It is a general utility that can be used for a variety of purposes including asset compilation, scripting monitoring, and **most notably as the basis for web servers**.

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

"There you have it - an array containing any arguments you passed in. Notice the first two elements- node and the path to your script. These will always be present- even if your program takes no arguments of its own, your script's interpreter and path are still considered arguments to the shell you're using.
