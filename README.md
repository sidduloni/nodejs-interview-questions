# nodejs-interview-questions

To format your Node.js and JavaScript Q&A for GitHub with headings and bold style, you can utilize Markdown, which is a lightweight markup language. Here's the formatted content:

```markdown
# S.No 1: Javascript difference between var, let, and const?
**Ans:**
- `var` is function-scoped and can be redeclared and reassigned.
- `let` is block-scoped, can be reassigned but not redeclared.
- `const` is block-scoped and cannot be reassigned or redeclared (but can be modified for objects and arrays).

# S.No 2: What is hoisting in Javascript?
**Ans:** Hoisting is a JavaScript mechanism where variable and function declarations are moved to the top of their containing scope during the compile phase. This allows variables and functions to be used before they are declared.

# S.No 3: Explain currying in JavaScript?
**Ans:** Currying is the process of transforming a function with multiple arguments into a series of functions with single arguments. It enables partial application of functions, making the code more modular and flexible.

... (continue for other questions)

# S.No 36: What is middleware?
**Ans:** Middleware comes in the middle of the request and response cycle of the node.js execution. Middleware has access to the request object, response object, and next(). `App.get('/', (req,res,next)=>{ next() }, (req, res)=> { } )`.
- Middleware can be used to add logging and authentication functionality.
- Middleware is used for setting some specific HTTP headers.
- (Middleware chaining) Body-parser(), routing (Middleware Stack)..
```

This will render your content with headings and bold styles on GitHub. You can copy and paste this into your GitHub repository's Markdown file for a nicely formatted Q&A.
