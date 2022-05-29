# Express and node 
**node** : is open source , cross plateform run time time envinroment that allows developer to build all kind of server side tools and application in javascripts

## node js has number of benefits
* great performance was desgined to optimized throughput in web good solution for common web development 
* code written in plan old Javascript 
*  JavaScript is a relatively new programming language and benefits from improvements in language design when compared to other traditional web-server languages
* The node package manager (NPM) provides access to hundreds of thousands of reusable packages
* Node.js is portable. It is available on Microsoft Windows, macOS, Linux
* You can use Node.js to create a simple web server using the Node HTTP package
### this the test app
![link](./class1image/Screenshot%20(113).png)
![link](./class1image/Screenshot%20(114).png)
![link](./class1image/Screenshot%20(115).png)
 # Web framework express
 * is the most popular node web frame work and is the underlying library for a number of other popular
 * Write handlers for requests with different HTTP verbs at different URL paths
 * Integrate with "view" rendering engines in order to generate responses by inserting data into templates.
 * Set common web application settings like the port to use for connecting, and the location of templates that are used for rendering the response
 

 ## How popular are node and express
 * The popularity of a web framework is important because it is an indicator of whether it will continue to be maintained . Based on the number of high profile companies that use Express, the number of people contributing to the codebase it is popular .

 ## What does Express code look like
 * Express provides methods to specify what function is called for a particular HTTP verb (GET, POST, SET
 ![linke](./class1image/Screenshot%20(116).png)

 ## Creating route handlers

  app.get('/', (req, res)=> {

  res.send('Hello World!')

});

## Using middleware
* Middleware is used extensively in Express apps, for tasks from serving static files to error handling, to compressing HTTP responses


## Serving static files
* You can use the express.static middleware to serve static files, including your images, CSS and JavaScript (static() is the only middleware function that is actually part of Express
* app.use(express.static('public'));


## Handling errors
* Errors are handled by one or more special middleware functions that have four arguments, instead of the usual three


## Using databases
* Express apps can use any database mechanism supported by Node (Express itself doesn't define any specific additional behavior/requirements for database management). There are many options, including PostgreSQL, MySQL, Redis, SQLite, MongoDB


## About npm
npm is the world's largest software registry. Open source developers from every continent use npm to share and borrow packages, and many organizations use npm to manage private development as well
 
 npm consists of three distinct components:

* the website
* the Command Line Interface (CLI)
* the registry

## TDD 
### Test-driven development” refers to a style of programming in which three activities are tightly interwoven: coding, testing (in the form of writing unit tests) and design (in the form of refactoring)


## CI/CD
### CI : Continous integration is work flow startigy that help ensure every one changes will integrat with the current version of the project , catch bugs and reduce merge conflict . 
> so it will ensure all changes will integrat .

### CD: Continous delevery is an extintion of countinous deployment 
> it is developing to realese at any time git hub track and communicate 


 
