# nodejs-interview-questions

#S.No 1:Javascript difference between var, let, and const?
##Ans:
- `var` is function-scoped and can be redeclared and reassigned.
- `let` is block-scoped, can be reassigned but not redeclared.
- `const` is block-scoped and cannot be reassigned or redeclared (but can be modified for objects and arrays).

#S.No 2: What is hoisting in Javascript? 
##Ans: Hoisting is a JavaScript mechanism where variable and function declarations are moved to the top of their containing scope during the compile phase. This allows variables and functions to be used before they are declared.

#S.No 3: Explain currying in JavaScript?  
##Ans: Currying is the process of transforming a function with multiple arguments into a series of functions with single arguments. It enables partial application of functions, making the code more modular and flexible.

#S.No 4: What is a callback function?
##Ans: A callback function is a function passed as an argument to another function and is executed after the completion of a specific task. It's commonly used in asynchronous programming to handle results once an operation finishes.
Ex: function asyncOperation(callback) {
    setTimeout(function () {
        callback("Operation completed successfully");
    }, 1000);
}

function callbackFunction(message) {
    console.log(message);
}

asyncOperation(callbackFunction);

#S.No 4.1 : What is promise write equivalent promise for the above callback function?
##Ans: Promises are a way to implement asynchronous programming in JavaScript. They are easy to manage when dealing with multiple asynchronous operations where callbacks can create callback hell leading to unmanageable code.
A Promise can be in one of three states:
Pending: Initial state, neither fulfilled nor rejected.
Fulfilled (Resolved): The operation completed successfully.
Rejected: The operation failed or encountered an error.

Equvalnt example for above Eg:
 const myPromise = new Promise((resolve, reject) => {
        setTimeout(function() {
            resolve("Promise callback executed")
        },4000)
    })

    myPromise.then((result) => {
        console.log("Promise resut: ", result)
    }).catch((error) => {
        console.log("promise error:", error)
    })
#S.No 4.2 : Explain async/await
##Ans: Async/Await makes it easier to write promises. 
'async' : return a promise, always.  await : the program wait until the Promise resolves.


#S.No 5: Explain Polymorphism.
##Ans: Polymorphism in JavaScript allows objects to be treated as instances of their parent class. This enables methods to be used interchangeably among objects, promoting code reusability and flexibility.

#S.No 6: What is IIFE?  
##Ans: Immediately Invoked Function Expression (IIFE) is a JavaScript function that is executed immediately after it's created. It's a way to encapsulate and isolate variables, preventing them from polluting the global scope.

#S.No 7: What is callback hell in Node.js?
##Ans: Callback hell refers to the situation where multiple asynchronous operations are nested within callback functions, making the code hard to read and manage. This often occurs when dealing with complex or deeply nested asynchronous logic.

#S.No 8: What is the event loop in Node.js?
##Ans: The event loop is a core concept in Node.js that allows it to handle multiple asynchronous tasks without getting blocked. It constantly checks the call stack and the callback queue, pushing functions from the queue to the call stack for execution.

#S.No 9: What are semantic elements in HTML?  
##Ans: Semantic elements in HTML are those that provide meaningful information about the content they wrap. Examples include `<header>`, `<footer>`, `<nav>`, `<section>`, and `<article>`. <form> 
             Non-sementic elelments - <div> <span> <p> etc

#S.No 10: How will you avoid built-in form validation in HTML?
##Ans:  To avoid built-in form validation, use the `novalidate` attribute in the `<form>` tag. This disables the browser's default form validation, allowing you to implement custom validation using JavaScript.

#S.No 11: How to place a div at the center of another div?
##Ans: To center a `<div>` within another `<div>`, you can use CSS properties like `position`, `top`, `left`, and `transform`. Set `position: absolute` on the inner `<div>` and use `top: 50%; left: 50%; transform: translate(-50%, -50%);` to center it.
<!DOCTYPE html>
<html>
<head>
    <style>
        .outer {
            position: relative;
            width: 300px;
            height: 300px;
            border: 1px solid #000;
        }
        
        .inner {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }
    </style>
</head>
<body>
    <div class="outer">
        <div class="inner">
            This is centered.
        </div>
    </div>
</body>
</html>


#S.No 12: Difference between display:none & visibility:hidden?*  
##Ans:
- `display: none` hides the element completely, removing it from the layout and making it occupy no space.
- `visibility: hidden` hides the element, but it still takes up space as if it were visible.

#S.No 13: What is the entry point of an Angular application?*  
##Ans:The entry point of an Angular application is typically the `main.ts` file. This file bootstraps the Angular application by calling `platformBrowserDynamic().bootstrapModule(AppModule)`.

#S.No 14: How will you do error handling?*  
##Ans:Error handling in Angular involves using try-catch blocks in TypeScript code to capture errors. Additionally, Angular provides error handling mechanisms like `ErrorHandler` to centralize error handling.

#S.No 15: What are decorators in Angular and its types?*  
##Ans:Decorators in Angular are functions that modify the behavior of classes or class members. Types of decorators include `@Component`, `@Directive`, `@Injectable`, `@Pipe`, and `@NgModule`.

#S.No 16: What is pipes chaining?*  
##Ans:Pipes chaining in Angular is the practice of applying multiple Angular pipes sequentially to transform the output in a desired way.

#S.No 17: Explain the concept of dependency injection?*  
##Ans:Dependency Injection (DI) is a design pattern where a class receives its dependencies from an external source rather than creating them itself. It promotes modularity, testability, and maintainability of the application.

#S.No 18: What are common interfaces provided by Angular?*  
##Ans:Common Angular interfaces include `OnInit`, `OnDestroy`, `OnChanges`, `AfterViewInit`, `AfterContentInit`, etc. These interfaces allow components and directives to implement specific lifecycle hooks.

#S.No 19: What is the difference between Subject and BehaviorSubject?*  
##Ans:
- `Subject` doesn't have an initial value and only emits values that are pushed to it after a subscription.
- `BehaviorSubject` has an initial value and emits the most recent value to new subscribers or those that have just subscribed.

#S.No 20: Significance of strings being immutable?*  
##Ans:Strings being immutable means their value cannot be changed after creation. This ensures data integrity and security, especially when dealing with sensitive information. Immutable strings also facilitate concurrency and caching optimizations.

#S.No 21: Difference between if-else and switch?*  
##Ans:
- `if-else` allows for branching based on multiple conditions using logical expressions.
- `switch` evaluates a single expression against multiple cases, providing a more readable and efficient alternative for multiple `if` conditions.

#S.No 22: Basic structure of Angular, difference in AngularJS & Angular?*  
##Ans:
- Basic structure of Angular: Angular follows a component-based architecture. It includes modules, components, services, templates, directives, and a dependency injection system.
- Difference between AngularJS and Angular: AngularJS (Angular 1.x) is an older version of the framework and uses JavaScript. Angular (from version 2 onwards) is a complete rewrite, utilizing TypeScript for better type safety, performance improvements, and a component-based architecture.

#S.No 23: Angular basic commands: create app, update library, create component, create module?*  
**##Ans:**
- Create a new Angular app: `ng new <app-name>`
- Update a library: `ng update <library-name>`
- Create a new component: `ng generate component <component-name>`
- Create a new module: `ng generate module <module-name>`

#S.No 24: Angular design patterns,? and why we use Angular and not React?*  
##Ans:
- Angular design patterns include the component architecture, dependency injection, and observables for handling asynchronous operations. These patterns promote a clean and maintainable codebase.
- The choice between Angular and React depends on project requirements. Angular is a full-featured framework suitable for large-scale applications, providing more structure and built-in features. React, on the other hand, is a flexible library, allowing developers to choose their tools and libraries, making it suitable for smaller projects or when performance is a top priority.

#S.No 25: How to handle exceptions in frontend?*  
##Ans:Exception handling in the frontend involves using try-catch blocks to capture and handle errors.

#S.No 26:** What is a thread pool in Node.js?
##Ans: In Node.js, a thread pool is a collection of worker threads that handle asynchronous operations. It allows Node.js to execute non-blocking I/O operations in a more efficient manner by utilizing multiple threads from the thread pool. This enhances concurrency and performance, especially when dealing with I/O-bound tasks.

Here's how the thread pool works in Node.js:

1. **Main Event Loop**:
   Node.js operates on a single main event loop, which is a single-threaded event-driven system for handling requests and executing JavaScript code.

2. **Asynchronous I/O Operations**:
   When Node.js encounters I/O-bound operations like reading from files, making network requests, or interacting with the file system, it doesn't block the main event loop. Instead, it offloads these tasks to the thread pool.

3. **Thread Pool**:
   The thread pool is a pool of worker threads managed by Node.js. It's used to perform blocking or CPU-intensive tasks asynchronously. Node.js maintains a fixed number of threads in the pool, typically four threads by default, although you can configure this number.

4. **Task Queue**:
   When an asynchronous operation is offloaded to the thread pool, it's placed in a task queue. The worker threads in the thread pool pick up tasks from this queue, process them, and then return the result to the main event loop.

5. **Callback Mechanism**:
   Once a task in the thread pool is completed, a callback function associated with the task is invoked. This callback is typically provided by the user to handle the results of the asynchronous operation.

It's important to note that while the thread pool allows Node.js to perform certain operations concurrently, it doesn't mean that the JavaScript code runs in multiple threads. JavaScript code itself still runs in a single thread, but the thread pool handles the underlying asynchronous tasks efficiently.


#S.No 27:  EventEmitter in Node.js?
##Ans: EventEmitter is a core module in Node.js used to handle events, we can create custom events using events module.
Ex: const EventEmitter = require('events');

const myEmitter = new EventEmitter();

myEmitter.on('greet', ( ) => {
  console.log('Hello, world!');
});

myEmitter.emit('greet');


#S.No 28: Buffers in nodejs with exmple
##Ans: The Buffer class in Node.js is used to perform operations on raw binary data. Generally, Buffer refers to the particular memory location in memory. Buffer and array have some similarities, but the difference is array can be any type, and it can be resizable. Buffers only deal with binary data, and it can not be resizable. Note: Buffer is global class no need to use require in nodejs
Methods:
No	Method	Description
1	Buffer.alloc(size)	It creates a buffer and allocates size to it.
2	Buffer.from(initialization)	It initializes the buffer with given data.
3	Buffer.write(data)	It writes the data on the buffer.
4	toString()	It read data from the buffer and returned it.
5	Buffer.isBuffer(object)	It checks whether the object is a buffer or not.
6	Buffer.length	It returns the length of the buffer.
7	Buffer.copy(buffer,subsection size)	It copies data from one buffer to another.
8	Buffer.slice(start, end=buffer.length)	It returns the subsection of data stored in a buffer.
9	Buffer.concat([buffer,buffer])	It concatenates two buffers.

Example:
const buf = Buffer.from('Hello, Node.js', 'utf-8');

console.log(buf.toString()); // Output: Hello, Node.js
console.log(buf.length);      // Output: 13

#S.No 29: Streams in nodejs with methods:
##Ans:
In Node.js, streams are a powerful and efficient way to handle reading and writing data, especially for large amounts of data or continuous data flow. Streams allow you to process data piece by piece (or chunk by chunk) rather than loading the entire data into memory. Streams are especially useful when dealing with network operations, file system operations, or other I/O operations.

There are several types of streams in Node.js:

Readable Stream:
Readable streams allow you to read data from a source. They are instances of the stream.Readable class. Common methods and events associated with readable streams include:

read(size): Reads and returns the specified number of bytes or characters.
on('data', callback): Event emitted when data is available to be read.
on('end', callback): Event emitted when there is no more data to be read.
on('error', callback): Event emitted if an error occurs.
pipe(destination): Pipes the data from the readable stream to a writable stream.

Writable Stream:
Writable streams allow you to write data to a destination. They are instances of the stream.Writable class. Common methods and events associated with writable streams include:

write(chunk, encoding, callback): Writes data to the stream.
end([chunk], [encoding], [callback]): Signals the end of writing and optionally writes the last chunk of data.
on('finish', callback): Event emitted when all data has been flushed.

Duplex Stream:
Duplex streams combine both readable and writable functionalities. They are instances of the stream.Duplex class. You can both read from and write to a duplex stream.

Transform Stream:
Transform streams are a special type of duplex stream where the output is computed based on the input. They are instances of the stream.Transform class. You can modify the data as it is being written or read.

Examples: -
Here's a brief example demonstrating how to use a readable and writable stream:
const fs = require('fs');

// Readable Stream
const readableStream = fs.createReadStream('input.txt', 'utf-8');

readableStream.on('data', (chunk) => {
  console.log('Read chunk:', chunk);
});

readableStream.on('end', () => {
  console.log('Read stream ended.');
});

readableStream.on('error', (err) => {
  console.error('An error occurred:', err);
});

// Writable Stream
const writableStream = fs.createWriteStream('output.txt', 'utf-8');

writableStream.write('This is some data to write.\n');
writableStream.write('More data to write.\n');
writableStream.end('End of writing.');

writableStream.on('finish', () => {
  console.log('Write stream finished writing.');
});

writableStream.on('error', (err) => {
  console.error('An error occurred:', err);
});

#S.No 30 What are some commonly used timing features of Node.js? 
##Ans:
setTimeout/clearTimeout – This is used to implement delays in code execution.
setInterval/clearInterval – This is used to run a code block multiple times.
setImmediate/clearImmediate – Any function passed as the setImmediate() argument is a callback that's executed in the next iteration of the event loop.
process.nextTick() – It is executed at last in iteration but before next iteration.

#S.No 31 Nodejs modules:
##Ans:

http: Provides functionality to create HTTP servers and clients.
fs (File System): Allows for file system operations like reading and writing files.
path: Helps in working with file and directory paths.
events: Enables event handling and emitting events. and creating custome events
util: Contains utility functions that are useful for developers.
os (Operating System): Provides information about the operating system.
querystring: Helps in parsing and formatting URL query strings.
crypto: Contains cryptographic functionality, including hash, HMAC, and encryption/decryption.
stream: Provides an interface for streaming data.
buffer: Allows for handling binary data directly.
url: Helps in URL resolution and parsing.
zlib: Provides functionality for compression and decompression using the zlib library.

S. No 32 Diff btw Observable and promise
##Ans: 
Observable:
Observables are for streams of events over time
It is cancel-able/retry-able and it supports operators such as map, filter and reduce etc.
Stream data in multiple pipeline
Provides chaining in subscriptions
Subscribe method is used for error handling

Promise:
A Promise can handle only one event
Not easy to cancel and it returns single value
Having one pipeline
Uses only .then() clause
Push error to the child promises

S. No 33 
##Ans: A closure in JavaScript is a function that remembers the variables from the scope in which it was created, even after that scope has finished executing. It has access to its own scope, the scope of the outer function, and the global scope.


#S.No 34 let nums = [22, 55, 2, 6] sort in ascending order without using inbuild function in js
##Ans: 
let nums = [22, 55, 2, 6];

function bubbleSort(arr) {
    const length = arr.length;
    for (let i = 0; i < length; i++) {
        for (let j = 0; j < length - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                // Swap elements if they are in the wrong order
                const temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}

bubbleSort(nums);
console.log("Sorted array in ascending order:", nums);

#S.No 35 Difference between Spawn and Fork child process:
##Ans:
Spawn :
This starts sending data back to a parent process from the child process as soon as the child process starts executing.
It creates a new process through command rather than running on the same node process.
In this, no new V8 instance is created.
It is used when we want the child process to return a large amount of data back to the parent process.

Fork :
This does not send data automatically, but we can use a global module name process to send data from the child process and in the parent module, using the name of the child the process to send to the child process.
It makes several individual processes (child processes) but all of them run on the same node process as the parent.
In this, a new V8 instance is created.
It is used to separate computation-intensive tasks from the main event loop.

#S.No 36 What is middleware?
##Ans: Middleware comes in the middle of the request and response cycle of the node.js execution. Middleware has the access to the request object, responses object, and next().  App.get(‘/’, (req,res,next)=>{ next() }, (req, res)=> { } ).
• Middleware can be used to add logging and authentication functionality.
• Middleware is used for setting some specific HTTP headers.
• (Middleware chaining) Body-parser(), routing (Middleware Stack)..

