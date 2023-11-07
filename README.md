
[Go to NodeJs Logic questions](https://github.com/sidduloni/nodejs-interview-questions/blob/main/logic.md)

## Nodejs FAQ

#nodejs-interview-questions
---

## S.No 1: Difference between var, let, and const variables in javascript?
**Ans:**
- \`var\` is function-scoped and can be redeclared and reassigned.
- \`let\` is block-scoped, can be reassigned but not redeclared.
- \`const\` is block-scoped and cannot be reassigned or redeclared (but can be modified for objects and arrays).

## S.No 2: What is hoisting in Javascript?
**Ans:** Hoisting is a JavaScript mechanism where variable and function declarations are moved to the top of their containing scope during the compile phase. This allows variables and functions to be used before they are declared.

## S.No 3: Explain currying in JavaScript?
**Ans:** Currying is the process of transforming a function with multiple arguments into a series of functions with single arguments. It enables partial application of functions, making the code more modular and flexible.

## S.No 4: What is a callback function?
**Ans:** A callback function is a function passed as an argument to another function and is executed after the completion of a specific task. It's commonly used in asynchronous programming to handle results once an operation finishes.
```javascript
function asyncOperation(callback) {
    setTimeout(function () {
        callback("Operation completed successfully");
    }, 1000);
}

function callbackFunction(message) {
    console.log(message);
}

asyncOperation(callbackFunction);
```

## S.No 4.1: What is promise write equivalent promise for the above callback function?
**Ans:** Promises are a way to implement asynchronous programming in JavaScript. They are easy to manage when dealing with multiple asynchronous operations where callbacks can create callback hell leading to unmanageable code.
A Promise can be in one of three states:
- Pending: Initial state, neither fulfilled nor rejected.
- Fulfilled (Resolved): The operation completed successfully.
- Rejected: The operation failed or encountered an error.
```javascript
const myPromise = new Promise((resolve, reject) => {
    setTimeout(function() {
        resolve("Promise callback executed");
    }, 4000);
})

myPromise.then((result) => {
    console.log("Promise result: ", result)
}).catch((error) => {
    console.log("Promise error:", error)
})
```

## S.No 4.2: Explain async/await
**Ans:** Async/Await makes it easier to write promises. 
- \`async\`: return a promise, always. 
- \`await\`: the program waits until the Promise resolves.

## S.No 5: Explain Polymorphism.
**Ans:** Polymorphism in JavaScript allows objects to be treated as instances of their parent class. This enables methods to be used interchangeably among objects, promoting code reusability and flexibility.

## S.No 6: What is IIFE?  
**Ans:** Immediately Invoked Function Expression (IIFE) is a JavaScript function that is executed immediately after it's created. It's a way to encapsulate and isolate variables, preventing them from polluting the global scope.

## S.No 7: What is callback hell in Node.js?
**Ans:** Callback hell refers to the situation where multiple asynchronous operations are nested within callback functions, making the code hard to read and manage. This often occurs when dealing with complex or deeply nested asynchronous logic.

## S.No 8: What is the event loop in Node.js?
**Ans:** The event loop is a core concept in Node.js that allows it to handle multiple asynchronous tasks without getting blocked. It constantly checks the call stack and the callback queue, pushing functions from the queue to the call stack for execution.

## S.No 9: What are semantic elements in HTML?  
**Ans:** Semantic elements in HTML are those that provide meaningful information about the content they wrap. 
Examples:
Examples **Sementic ** include `<header>`, `<footer>`, `<nav>`, `<section>`, and `<article>`. 
**Non-semantic** elements include `<div>`, `<span>`, `<p>`, etc.


## S.No 10: How will you avoid built-in form validation in HTML?
**Ans:** To avoid built-in form validation, use the 'novalidate' attribute in the form tag. This disables the browser's default form validation, allowing you to implement custom validation using JavaScript.
```html
<form novalidate>
...
</form>
```

## S.No 11: How to place a div at the center of another div?
**Ans:** To center a `<div>` within another `<div>`, you can use CSS properties like `position`, `top`, `left`, and `transform`. Set `position: absolute` on the inner `<div>` and use `top: 50%; left: 50%; transform: translate(-50%, -50%);` to center it.

```html
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
```

## S.No 12: Difference between display:none & visibility:hidden?  
**Ans:**
- \`display: none\` hides the element completely, removing it from the layout and making it occupy no space.
- \`visibility: hidden\` hides the element, but it still takes up space as if it were visible.

## S.No 13: What is the entry point of an Angular application?  
**Ans:** The entry point of an Angular application is typically the \`main.ts\` file. This file bootstraps the Angular application by calling \`platformBrowserDynamic().bootstrapModule(AppModule)\`.

## S.No 14: How will you do error handling?  
**Ans:** Error handling in Angular involves using try-catch blocks in TypeScript code to capture errors. Additionally, Angular provides error handling mechanisms like \`ErrorHandler\` to centralize error handling.

## S.No 15: What are decorators in Angular and its types?  
**Ans:** Decorators in Angular are functions that modify the behavior of classes or class members. Types of decorators include \`@Component\`, \`@Directive\`, \`@Injectable\`, \`@Pipe\`, and \`@NgModule\`.

## S.No 16: What is pipes chaining?  
**Ans:** Pipes chaining in Angular is the practice of applying multiple Angular pipes sequentially to transform the output in a desired way.

## S.No 17: Explain the concept of dependency injection?  
**Ans:** Dependency Injection (DI) is a design pattern where a class receives its dependencies from an external source rather than creating them itself. It promotes modularity, testability, and maintainability of the application.

## S.No 18: What are common interfaces provided by Angular?  
**Ans:** Common Angular interfaces include \`OnInit\`, \`OnDestroy\`, \`OnChanges\`, \`AfterViewInit\`, \`AfterContentInit\`, etc. These interfaces allow components and directives to implement specific lifecycle hooks.

## S.No 19: What is the difference between Subject and BehaviorSubject?  
**Ans:**
- \`Subject\` doesn't have an initial value and only emits values that are pushed to it after a subscription.
- \`BehaviorSubject\` has an initial value and emits the most recent value to new subscribers or those that have just subscribed.

## S.No 20: Significance of strings being immutable?  
**Ans:** Strings being immutable means their value cannot be changed after creation. This ensures data integrity and security, especially when dealing with sensitive information. Immutable strings also facilitate concurrency and caching optimizations.

## S.No 21: Difference between if-else and switch?  
**Ans:**
- \`if-else\` allows for branching based on multiple conditions using logical expressions.
- \`switch\` evaluates a single expression against multiple cases, providing a more readable and efficient alternative for multiple \`if\` conditions.

## S.No 22: Basic structure of Angular, difference in AngularJS & Angular?  
**Ans:**
- Basic structure of Angular: Angular follows a component-based architecture. It includes modules, components, services, templates, directives, and a dependency injection system.
- Difference between AngularJS and Angular: AngularJS (Angular 1.x) is an older version of the framework and uses JavaScript. Angular (from version 2 onwards) is a complete rewrite, utilizing TypeScript for better type safety, performance improvements, and a component-based architecture.

## S.No 23: Angular basic commands: create app, update library, create component, create module?  
**Ans:**
- Create a new Angular app: \`ng new <app-name>\`
- Update a library: \`ng update <library-name>\`
- Create a new component: \`ng generate component <component-name>\`
- Create a new module: \`ng generate module <module-name>\`

## S.No 24: Angular design patterns,? and why we use Angular and not React?  
**Ans:**
- Angular design patterns include the component architecture, dependency injection, and observables for handling asynchronous operations. These patterns promote a clean and maintainable codebase.
- The choice between Angular and React depends on project requirements. Angular is a full-featured framework suitable for large-scale applications, providing more structure and built-in features. React, on the other hand, is a flexible library, allowing developers to choose their tools and libraries, making it suitable for smaller projects or when performance is a top priority.

## S.No 25: How to handle exceptions in frontend?  
**Ans:** Exception handling in the frontend involves using try-catch blocks to capture and handle errors.

## S.No 26: What is a thread pool in Node.js?
**Ans:** In Node.js, a thread pool is a collection of worker threads that handle asynchronous operations. It allows Node.js to execute non-blocking I/O operations in a more efficient manner by utilizing multiple threads from the thread pool. This enhances concurrency and performance, especially when dealing with I/O-bound tasks.

## S.No 27:  EventEmitter in Node.js?
**Ans:** EventEmitter is a core module in Node.js used to handle events, we can create custom events using the events module.
```javascript
const EventEmitter = require('events');

const myEmitter = new EventEmitter();

myEmitter.on('greet', (msg) => {
  console.log(msg);
});

myEmitter.emit('greet', 'Event emitted! message here');
// Output - Event emitted! message here

```

## S.No 28: Buffers in nodejs with example
**Ans:** The Buffer class in Node.js is used to perform operations on raw binary data. Generally, Buffer refers to the particular memory location in memory. Buffer and array have some similarities, but the difference is an array can be any type, and it can be resizable. Buffers only deal with binary data and cannot be resizable.

Example:
```javascript
const buf = Buffer.from('Hello, Node.js', 'utf-8');

console.log(buf.toString()); // Output: Hello, Node.js
console.log(buf.length);      // Output: 13
```

## S.No 29: Streams in nodejs with methods:
**Ans:** Streams in Node.js are a powerful and efficient way to handle reading and writing data, especially for large amounts of data or continuous data flow. Streams allow you to process data piece by piece (or chunk by chunk) rather than loading the entire data into memory. Streams are especially useful when dealing with network operations, file system operations, or other I/O operations.

There are several types of streams in Node.js:

**Readable Stream:**
Readable streams allow you to read data from a source. They are instances of the stream.Readable class. Common methods and events associated with readable streams include:

read(size): Reads and returns the specified number of bytes or characters.
on('data', callback): Event emitted when data is available to be read.
on('end', callback): Event emitted when there is no more data to be read.
on('error', callback): Event emitted if an error occurs.
pipe(destination): Pipes the data from the readable stream to a writable stream.

**Writable Stream:**
Writable streams allow you to write data to a destination. They are instances of the stream.Writable class. Common methods and events associated with writable streams include:

write(chunk, encoding, callback): Writes data to the stream.
end([chunk], [encoding], [callback]): Signals the end of writing and optionally writes the last chunk of data.
on('finish', callback): Event emitted when all data has been flushed.

**Duplex Stream:**
Duplex streams combine both readable and writable functionalities. They are instances of the stream.Duplex class. You can both read from and write to a duplex stream.

**Transform Stream:**
Transform streams are a special type of duplex stream where the output is computed based on the input. They are instances of the stream.Transform class. You can modify the data as it is being written or read.

Examples: -
```javascript
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
```


## S.No 30: What are some commonly used timing features of Node.js? 
**Ans:**
- `setTimeout/clearTimeout`: This is used to implement delays in code execution.
- `setInterval/clearInterval`: This is used to run a code block multiple times.
- `setImmediate/clearImmediate`: Any function passed as the `setImmediate()` argument is a callback that's executed in the next iteration of the event loop.
- `process.nextTick()`: It is executed at last in iteration but before the next iteration.

## S.No 31: Node.js modules
**Ans:**
Node.js provides a rich set of built-in modules to make various functionalities available to your application. Some commonly used modules include:
- `http`: Provides functionality to create HTTP servers and clients.
- `fs` (File System): Allows for file system operations like reading and writing files.
- `path`: Helps in working with file and directory paths.
- `events`: Enables event handling and emitting events, and creating custom events.
- `util`: Contains utility functions that are useful for developers.
- `os` (Operating System): Provides information about the operating system.
- `querystring`: Helps in parsing and formatting URL query strings.
- `crypto`: Contains cryptographic functionality, including hash, HMAC, and encryption/decryption.
- `stream`: Provides an interface for streaming data.
- `buffer`: Allows for handling binary data directly.
- `url`: Helps in URL resolution and parsing.
- `zlib`: Provides functionality for compression and decompression using the zlib library.

## S.No 32: Difference between Observable and Promise
**Ans:**
- **Observable:**
  - Observables are for streams of events over time.
  - It is cancelable/retryable and supports operators such as map, filter, and reduce, etc.
  - Stream data in multiple pipelines.
  - Provides chaining in subscriptions.
  - Subscribe method is used for error handling.

- **Promise:**
  - A Promise can handle only one event.
  - Not easy to cancel and it returns a single value.
  - Having one pipeline.
  - Uses only `.then()` clause.
  - Push error to the child promises.

## S.No 33: What is a closure in JavaScript?
**Ans:**
A closure in JavaScript is a function that remembers the variables from the scope in which it was created, even after that scope has finished executing. It has access to its own scope, the scope of the outer function, and the global scope.

## S. No 34:  What is middleware?
**Ans:** Middleware comes in the middle of the request and response cycle of the node.js execution. Middleware has the access to the request object, responses object, and next().  App.get(‘/’, (req,res,next)=>{ next() }, (req, res)=> { } ).
• Middleware can be used to add logging and authentication functionality.
• Middleware is used for setting some specific HTTP headers.
• (Middleware chaining) Body-parser(), routing (Middleware Stack)..


## S.No 35: Difference between Spawn and Fork child process:
**Ans:**
- Spawn :
  - This starts sending data back to a parent process from the child process as soon as the child process starts executing.
  - It creates a new process through a command rather than running on the same node process.
  - In this, no new V8 instance is created.
  - It is used when we want the child process to return a large amount of data back to the parent process.
  
- Fork :
  - This does not send data automatically, but we can use a global module name process to send data from the child process and in the parent module, using the name of the child the process to send to the child process.
  - It makes several individual processes (child processes) but all of them run on the same node process as the parent.
  - In this, a new V8 instance is created.
  - It is used to separate computation-intensive tasks from the main event

 loop.

## S.No 36: How to handle errors in Node.js?  
**Ans:**
- **Synchronous Code:** Use try-catch blocks to handle errors in synchronous code.
```javascript
try {
  // code that may throw an error
  fs.readFileSync('file-that-does-not-exist.txt');
} catch (error) {
  console.error('Error:', error.message);
}
```
- **Asynchronous Code:** For asynchronous operations, use error-first callbacks or Promises with try-catch for error handling.
```javascript
// Using error-first callbacks
fs.readFile('file-that-does-not-exist.txt', (err, data) => {
  if (err) {
    console.error('Error:', err.message);
  } else {
    console.log('Data:', data);
  }
});

// Using Promises
const readFilePromise = (file) => {
  return new Promise((resolve, reject) => {
    fs.readFile(file, (err, data) => {
      if (err) {
        reject(err);
      } else {
        resolve(data);
      }
    });
  });
};

readFilePromise('file-that-does-not-exist.txt')
  .then(data => console.log('Data:', data))
  .catch(error => console.error('Error:', error.message));
```


## S.No 37  How does Node.js provide security in applications?
**Ans:**

**Dependency Management:**  Node.js promotes regular updates and maintenance of dependencies to ensure the use of the latest security patches and updates.
Input Validation and Sanitization: Proper input validation and sanitization techniques prevent malicious code injection, such as SQL injection and cross-site scripting (XSS) attacks.

**Authentication and Authorization:**
Robust authentication mechanisms and access controls ensure that only authorized users can access sensitive parts of the application.

**HTTPS and SSL/TLS:**
Utilizing HTTPS with SSL/TLS encryption guarantees data privacy and integrity during transmission.

**Secure Coding Practices:**
Following secure coding practices helps prevent common vulnerabilities like injection attacks, XSS, and CSRF.

**File Upload Security:**
Implementing stringent validation and restrictions on file uploads prevents security threats like file inclusion and executable file uploads.
**Least Privilege Principle:**
Applying the principle of least privilege ensures that users and processes have minimal access necessary for their functions, reducing potential attack surfaces.

**Security Headers and CORS:**
Configuring secure headers (e.g., Content Security Policy) and enforcing proper Cross-Origin Resource Sharing (CORS) mitigates specific types of attacks like clickjacking and data theft.

**Security Libraries and Middleware:**
Leveraging security-focused libraries and middleware, such as Helmet.js, automates the application of security measures, enhancing overall security.

**Error Handling:**
Implementing secure error handling prevents exposure of sensitive information, ensuring that error messages are informative yet safe.

**Logging and Monitoring:**
Incorporating logging mechanisms and monitoring tools allows tracking and detection of security-relevant events, facilitating timely responses to potential security incidents.

**Security Audits and Code Reviews:**
Conducting regular security audits and code reviews identifies vulnerabilities and weaknesses in the application, enabling proactive security enhancements.


## S.No 38 Cluster module in nodejs?
**Ans:**
In the context of Node.js, a "cluster" typically refers to a mechanism that allows a Node.js application to utilize multiple CPU cores efficiently by creating child processes, also known as workers. This enables parallel processing and improves the overall performance and scalability of the application.

Here are the key points about clusters in Node.js:

1. **Node.js Single-Threaded Nature:**
   Node.js is single-threaded, meaning it runs on a single core of the CPU by default. This can be a limitation when trying to fully utilize modern multicore CPUs.

2. **Cluster Module:**
   The `cluster` module in Node.js allows you to create multiple child processes (workers) that share the same server port. Each worker runs on its own core, effectively leveraging the available CPU resources.

3. **Master and Worker Process:**
   - The master process is responsible for managing the worker processes. It listens for incoming connections and distributes them among the workers.
   - Worker processes handle the actual requests and perform the application logic.

4. **Load Balancing:**
   When a request is received, the master process uses a round-robin algorithm to distribute the request to one of the worker processes. This achieves basic load balancing across the CPU cores.

5. **Scalability and Performance:**
   By utilizing multiple cores, a Node.js application can handle a higher volume of concurrent requests and achieve better performance compared to running on a single core.

6. **Fault Tolerance:**
   If a worker process crashes due to an error, the master process can create a new worker to replace it, ensuring that the application remains available.

7. **Event Loop Per Worker:**
   Each worker process has its own event loop, enabling independent processing of requests.

Here's a simple example of how to create a cluster in Node.js using the `cluster` module:

```javascript
const cluster = require('cluster');
const http = require('http');
const numCPUs = require('os').cpus().length;

if (cluster.isMaster) {
  // Fork workers for each CPU
  for (let i = 0; i < numCPUs; i++) {
    cluster.fork();
  }

  cluster.on('exit', (worker, code, signal) => {
    console.log(`Worker ${worker.process.pid} died`);
  });
} else {
  // Worker code
  http.createServer((req, res) => {
    res.writeHead(200);
    res.end('Hello, World!\n');
  }).listen(8000);
}
```
In this example, the master process forks multiple worker processes, and each worker handles HTTP requests independently. The requests are distributed among the workers in a round-robin fashion.


## S.No 39  Difference between PUT and POST
**Ans:** 

**Put:**
Update or replace an existing resource
Idempotent (Multiple identical requests have the same effect as a single request)
Considered safe, as it should not have side effects on the server (though it modifies data).

**Post:**
Submit data to create a new resource
Not idempotent 
Not considered safe - creating or deleting resources.

## S.No 40 Explain Cookie and session cookie and cookie limit
**Ans:** 
They are sent by the browser with every subsequent request to the same domain
Cookie limit 4KB
Protecting Cookies in JavaScript: 

**Secure and HTTP-only Cookies:**
Use the Secure flag to ensure cookies are only sent over HTTPS, and use the HttpOnly flag to prevent client-side scripts from accessing the cookie, thus protecting against certain types of attacks like cross-site scripting (XSS).

**Limit Cookie Scope:**
Set the Domain and Path attributes appropriately to limit the scope of the cookie to specific domains and paths, ensuring it's not accessible where it's not needed.

**Session Cookies:**
For sensitive information, consider using session cookies that expire when the user closes the browser, ensuring data isn't stored longer than necessary.

**Regularly Rotate and Invalidate Cookies:**
Rotate session IDs or tokens periodically, especially after critical operations like login or password change, to mitigate the risk of stolen or leaked credentials.


## S.No 41 Diff btw package.json and package-lock.json files
**Ans:**
package.json contains dependency declarations with version ranges (e.g., "express": "^4.17.1"), allowing for flexibility in updating to compatible versions
package-lock.json contains specific, exact versions of each dependency and its sub-dependencies, ensuring consistency and reproducibility across different installations.


## S.No 42 what take(), map, exhaustMap and tap operators of rxjs does in angular
**Ans:**

The **take(1)** operator instructs the observable to emit only the first value it encounters and then complete. After it receives and emits the first value, it automatically unsubscribes from the observable, preventing any further emissions.

The **map** operator transforms the emitted value

The **exhaustMap:** It maps the source observable's value to another observable, but it only emits values from the inner observable while ignoring new values from the source until the inner observable completes.

The **tap:** It allows you to perform side effects (e.g., logging, debugging) on the source observable's values without affecting the values themselves, then passes them along unchanged.

## S.No 43 Explain 5 types of guards in Angular
**Ans:** 

**CanActivate:** Controls if a route can be activated.

**CanActivateChild:** Controls if children of a route can be activated.

**CanDeactivate:** Controls if a route can be deactivated.

**Resolve:** Fetches necessary data before activating a route.

**CanLoad:** Controls if a module can be loaded lazily.

## S.No 44 How to implement real-time chatting using Socket.io in nodejs
**Ans***
```javascript
// In app.js root file of your nodejs import socket.io package
const http = require("http")

const httpServer = http.createServer()

const socketio = require("socket.io")

const io = socketio.Server(httpServer)

io.on('connection', (socket)=> {
    socket.on('join', (room) => {
        socket.join(room)
    })

    socket.on("chat", (data) => {
        const { room, msg, senderId, type, time, msgId } = JSON.parse(data);
        socket.broadcast.to(room).emit("receive", { msg, senderId, type, time, msgId });
      });
...
    socket.io('disconnect', () => {
        socket.emit("offlineStatus")
    })
        
})

```

## S.No 45 How to setup web socket in angular
**Ans:** 

```typescript
// socket.service.ts
// npm install socket.io-client

   import { Injectable } from '@angular/core';
   import { io, Socket } from 'socket.io-client';
   import { Observable } from 'rxjs';

   @Injectable({
     providedIn: 'root'
   })
   export class SocketService {
     private socket: Socket;

     constructor() {
       this.socket = io('http://your-socket-server-url'); // Replace with your Socket.io server URL
     }

     joinRoom(room: string) {
       this.socket.emit('join', room);
     }

     sendMessage(room: string, message: string) {
       this.socket.emit('chat', { room, message });
     }

     receiveMessages(): Observable<any> {
       return new Observable<any>(observer => {
         this.socket.on('receive', (data: any) => observer.next(data));
       });
     }

     // Add other Socket.io event handlers and emit functions here
   }
   ```

3. **Create Angular Component for Chat:**

   Create a component to display the chat interface and handle chat functionality.

   ```typescript
   // chat.component.ts

   import { Component, OnInit } from '@angular/core';
   import { SocketService } from './path/to/socket.service';

   @Component({
     selector: 'app-chat',
     templateUrl: './chat.component.html',
     styleUrls: ['./chat.component.css']
   })
   export class ChatComponent implements OnInit {
     messages: any[] = [];
     message: string = '';

     constructor(private socketService: SocketService) { }

     ngOnInit() {
       this.socketService.receiveMessages().subscribe((data) => {
         this.messages.push(data);
       });
     }

     sendMessage() {
       if (this.message) {
         this.socketService.sendMessage('room1', this.message);
         this.message = '';
       }
     }
   }
   ```

4. **Create Chat HTML Template:**

   Create the HTML template for the chat component.

   ```typescript
   <!-- chat.component.html -->

   <div>
     <div *ngFor="let msg of messages">
       {{ msg.senderId }}: {{ msg.msg }}
     </div>
   </div>

   <input [(ngModel)]="message" placeholder="Type a message..." />
   <button (click)="sendMessage()">Send</button>
   ```

   Don't forget to add the necessary FormsModule import and declaration in the AppModule for using ngModel.

5. **Integrate Chat Component in Main App Component:**

   Integrate the chat component into your main app component.

   ```typescript
   // app.component.ts

   import { Component } from '@angular/core';

   @Component({
     selector: 'app-root',
     template: '<app-chat></app-chat>',
     styles: []
   })
   export class AppComponent { }
   ```

## S.No 46 Write example for Reactive form in angular
**Ans:**
```typescript

//Reactive Form (HTML):
<form [formGroup]="registerForm" (ngSubmit)="onSubmit()">
  <label for="firstName">First Name:</label>
  <input type="text" id="firstName" formControlName="firstName">

  <label for="email">Email:</label>
  <input type="email" id="email" formControlName="email">

  <label for="mobileNumber">Mobile Number:</label>
  <input type="tel" id="mobileNumber" formControlName="mobileNumber">

  <button type="submit" [disabled]="registerForm.invalid">Submit</button>
</form>

Component File (TypeScript):
import { Component, OnInit } from '@angular/core';
import { FormBuilder, FormGroup, Validators } from '@angular/forms';

@Component({
  selector: 'app-register',
  templateUrl: './register.component.html',
  styleUrls: ['./register.component.css']
})
export class RegisterComponent implements OnInit {
  registerForm: FormGroup;

  constructor(private fb: FormBuilder) { }

  ngOnInit() {
    this.registerForm = this.fb.group({
      firstName: ['', Validators.required],
      email: ['', [Validators.required, Validators.email]],
      mobileNumber: ['', [Validators.required, Validators.pattern('[0-9]{10}')]]
    });
  }

onSubmit() {
  if (this.registerForm.valid) {
    console.log('Form values:', this.registerForm.value);
    // You can send the form values to a server or perform other actions here
  } else {
    console.log('Form is invalid. Please check the fields.');
  }
}
```

## S.No 47 Explain how to authenticate a Node.js app with JWT (JsonWebToken)
**Ans**
```javascript
// We create a separate file jwt.js

const jwt = require('jsonwebtoken');

module.exports = function (req, res, next) {
  console.log(req.headers);
  const authHeader = req.headers['authorization'];
  if (!authHeader || !authHeader.startsWith('Bearer ')) {
    return res.status(401).send({ auth: false, message: 'No token provided.' });
  }

  const token = authHeader.split('Bearer ')[1];
  jwt.verify(token, process.env.JWT_SECRET, function (err, decoded) {
    if (err)
      return res
        .status(500)
        .send({ auth: false, message: 'Failed to authenticate token.' });
    req.userId = decoded.id;
    // console.log('jwt ', req.userId)
    next();
  });
};

// In login.js file we generate the token 
 const token = jwt.sign({ id: newUser._id }, process.env.JWT_SECRET);

```

## S.No 48 Explain how to implement encryption and decryption of passwords in Node.js
**Ans**
```javascript
const bcrypt = require("bcryptjs");

// In registration we hash the password 
let salt = await bcrypt.genSalt(10);
password = await bcrypt.hash(password, salt);

// In login we compare the hassed password
bcrypt.compare(password, user.password)

```

## S.No 49 Write mongodb queries for CRUD and joining collection and search query.
**Ans**
```javascript
const User = require('./userModel');
const Client = require('./clientModel'); 

// 1. Insert a User
const newUser = new User({ name: 'John' });
newUser.save();

// using insertOne
User.insertOne({
		First_Name: "Radhika",
		Last_Name: "Sharma"
	})

// Using insertMany
User.insertMany([{...}, {...}]) // Or simgply use User.insert

// 2. Edit a User
User.findByIdAndUpdate(userId, { name: 'Updated Name' }, { new: true });

// 3. Update a User
User.updateOne({ _id: userId }, { age: 30 }); // Use User.updateMany for many

// 4. Delete a User
User.findByIdAndRemove(userId);

// 5. Aggregate Users by Age
User.aggregate([{ $group: { _id: '$age', count: { $sum: 1 } } }]);

// 6. Search Users with Skip and Limit
User.find({ age: { $gte: 25 } }, {username: 1}).skip(10).limit(5); // We use projection in the 2nd parameter

// We can use "findOne" 

// 7. Join Users and Clients using Populate and Aggregate
// Using Aggregate
User.aggregate([
  {
    $lookup: {
      from: 'clients', // Assuming the collection name for clients is 'clients'
      localField: '_id',
      foreignField: 'userId',
      as: 'userClients',
    },
  },
]);

// Using Populate
User.findOne({ _id: userId })
  .populate({
      path: "clientId",
      select: "_id fullName profilePic username"
    });

Note: To use populate we must add "ref" is other collection schema definition.

Example: Add ref in the client schema's definition userId field.

userId: {
      type: mongoose.Schema.Types.ObjectId, // Type is important
      ref: "User", // This is important to use populate
      required: true,
    },

```

## S.No 50 Explain object and array destructuring in javascript
**Ans** 
- **Array Destructuring:** Array destructuring is a feature in JavaScript that allows you to extract values from an array and assign them to variables in a single, concise statement. It provides an easy way to work with individual elements of an array by specifying which elements you want to destructure and assign to variables.
- **Object Destructuring:** Object destructuring is a feature in JavaScript that enables you to extract values from an object and assign them to variables using a simple and intuitive syntax. It allows you to access and work with specific properties of an object by specifying the property names, making your code more readable and organized.
```javascript
// Basic Array Destructuring:
const colors = ['red', 'green', 'blue'];
const [first, second, third] = colors;

console.log(first);  // Output: 'red'
console.log(second); // Output: 'green'
console.log(third);  // Output: 'blue'

// Skipping Elements in Array Destructuring:
const numbers = [1, 2, 3, 4, 5];
const [first, , third] = numbers;

console.log(first);  // Output: 1
console.log(third);  // Output: 3

// Basic Object Destructuring:
const person = { firstName: 'John', lastName: 'Doe', age: 30 };
const { firstName, lastName, age } = person;

console.log(firstName);  // Output: 'John'
console.log(lastName);   // Output: 'Doe'
console.log(age);        // Output: 30

// Renaming Variables in Object Destructuring:
const user = { name: 'Alice', email: 'alice@example.com' };
const { name: fullName, email: userEmail } = user;

console.log(fullName);  // Output: 'Alice'
console.log(userEmail); // Output: 'alice@example.com'

```
## S.No 51 What is Absctract class in javascript 
**Ans** Absctract class contains one or more abstract methods within it. An abstract method is a method that can only be declared but has no implementation to it.

## S.No 52 What is fork in nodejs 
**Ans** The fork() allows the separation of computation-intensive tasks from the main event loop

## S.No 53 How to communicate between different components in Angular
**Ans**
In Angular, you can communicate between components in several ways, depending on the relationship between the components and the data flow. Here are some common methods for communication between components:

1. Input and Output Properties:
   - Parent components can pass data to child components using input properties.
   - Child components can emit events using output properties to notify the parent component of changes.
   - This is a unidirectional data flow, with data flowing from parent to child and events flowing from child to parent.

2. Services:
   - Services are singleton objects that can be used to share data and functionality between components.
   - Components can inject the same service and interact with shared data.
   - This is a good approach for sharing data or functions across unrelated components.

3. Event Emitters and Observables:
   - You can use RxJS Observables and subjects to create custom event emitters.
   - Components can subscribe to these observables to receive updates when events occur.
   - This allows for more complex, flexible communication patterns.

4. @ViewChild and @ViewChildren:
   - You can use ViewChild and ViewChildren decorators to access child components from a parent component.
   - This allows you to directly interact with child component methods and properties.

5. @Input and @Output Decorators:
   - Components can use the @Input decorator to accept data from their parent components.
   - The @Output decorator allows components to emit events that the parent can subscribe to.

6. Router and Query Parameters:
   - You can pass data between components using route parameters or query parameters when navigating between routes.

7. NgRx/Redux:
   - For managing complex state and communication in large Angular applications, you can use NgRx, which implements the Redux pattern.
   - This provides a centralized store and actions for communication and **state management.**

For more complex scenarios or inter-component communication, **services** and **observables** may be a better choice.

Examples:

1. Event Emitters and Observables:
   - Using RxJS Observables to communicate between components:

     Service with an Observable:
     ```typescript
     import { Injectable } from '@angular/core';
     import { BehaviorSubject } from 'rxjs';

     @Injectable()
     export class DataService {
       private messageSource = new BehaviorSubject<string>('Initial message');
       currentMessage = this.messageSource.asObservable();

       changeMessage(message: string) {
         this.messageSource.next(message);
       }
     }
     ```

     Component 1:
     ```typescript
     import { Component, OnInit } from '@angular/core';
     import { DataService } from './data.service';

     @Component({
       selector: 'app-component1',
       template: `
         <p>{{ message }}</p>
       `
     })
     export class Component1 implements OnInit {
       message: string;

       constructor(private dataService: DataService) {}

       ngOnInit() {
         this.dataService.currentMessage.subscribe(message => this.message = message);
       }
     }
     ```

     Component 2:
     ```typescript
     import { Component } from '@angular/core';
     import { DataService } from './data.service';

     @Component({
       selector: 'app-component2',
       template: `
         <button (click)="updateData()">Update Data</button>
       `
     })
     export class Component2 {
       constructor(private dataService: DataService) {}

       updateData() {
         this.dataService.changeMessage('New message from Component 2');
       }
     }
     ```

2. @ViewChild and @ViewChildren:
   - Accessing child components from a parent component:

     Parent Component:
     ```typescript
     import { Component, ViewChild } from '@angular/core';
     import { ChildComponent } from './child.component';

     @Component({
       selector: 'app-parent',
       template: `
         <app-child></app-child>
         <button (click)="callChildMethod()">Call Child Method</button>
       `
     })
     export class ParentComponent {
       @ViewChild(ChildComponent) child: ChildComponent;

       callChildMethod() {
         this.child.childMethod();
       }
     }
     ```

     Child Component:
     ```typescript
     import { Component } from '@angular/core';

     @Component({
       selector: 'app-child',
       template: `
         <p>Child Component</p>
       `
     })
     export class ChildComponent {
       childMethod() {
         console.log('Child method called');
       }
     }
     ```

3. @Input and @Output Decorators:
   - Parent to Child (Input) and Child to Parent (Output):

     Parent Component:
     ```typescript
     import { Component } from '@angular/core';

     @Component({
       selector: 'app-parent',
       template: `
         <app-child [message]="parentMessage" (messageEvent)="receiveMessage($event)"></app-child>
         <p>{{ receivedMessage }}</p>
       `
     })
     export class ParentComponent {
       parentMessage = 'Message from parent';
       receivedMessage: string;

       receiveMessage(message: string) {
         this.receivedMessage = message;
       }
     }
     ```

     Child Component:
     ```typescript
     import { Component, Input, Output, EventEmitter } from '@angular/core';

     @Component({
       selector: 'app-child',
       template: `
         <p>{{ message }}</p>
         <button (click)="sendMessage()">Send Message</button>
       `
     })
     export class ChildComponent {
       @Input() message: string;
       @Output() messageEvent = new EventEmitter<string>();

       sendMessage() {
         this.messageEvent.emit('Message from child');
       }
     }
     ```


---
