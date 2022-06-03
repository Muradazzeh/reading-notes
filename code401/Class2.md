## Classes
 * class 2 reading 
 * Classes are a template for creating objects. classes are special function .
 * class syntax has two components
    * class expressions 
    * class declarations.

* Class declarations
One way to define a class is using a class declaration. To declare a class, you use the class keyword with the name of the class ("name" here)

```
class name {
    constructor(name,age){
        this.name=name;
        this.age=age;
            }

}

```
* Class expressions
A class expression is another way to define a class. Class expressions can be named or unnamed. The name given to a named class expression is local to the class's body

* Constructor : using class is simpler way to work with constructor , we can use extend and super method with the class constructor 
* Instance properties
Instance properties must be defined inside of class methods:
* Sub classing with extends
The extends keyword is used in class declarations or class expressions to create a class as a child of another class
```
class name {
    constructor(name,age){
        this.name=name;
        this.age=age;
            }

}

class home extend name{
    constructor(name){
        super(name)
    }
}
```
* Super class calls with super
The super keyword is used to call corresponding methods of super class. This is one advantage over prototype-based inheritance.

> note that i want to know more about prototype method in the classes.

## Routes 
* Routing refers to how an application’s endpoints (URIs) respond to client requests
* routes methods are app.get() to handle GET requests and app.post to handle POST requests , and app.use() to specify middleware as the callback function
* basic route code 
```
const express = require('express')
const app = express()

app.get('/', (req, res) => {
  res.send('HELLOW WORLD WAR THREE')
})
```

### Route paths 
* We have different routes path usually we using "/" home path and "/about", also we can use the regular expression to make pattern for the requierd path 

## Route parameters
* Route parameters are named URL segments that are used to capture the values specified at their position in the URL 

```
Route path: /users/:userId/books/:bookId
Request URL: http://localhost:3000/users/34/books/8989
req.params: { "userId": "34", "bookId": "8989" }
```
* we also can uae in the routes handdler middle ware function to handle other request .

## Response methods
 * res.download() :=>	Prompt a file to be downloaded.
* res.end():=>	End the response process.
* res.json():=>	Send a JSON response.
* res.jsonp():=>	Send a JSON response with JSONP support.
* res.redirect():=>	Redirect a request.
* res.render():=>	Render a view template.
* res.send():=>	Send a response of various types.
* res.sendFile():=>	Send a file as an octet stream.
 * res.sendStatus():=>	Set the response status code and send its string representation as the response body.


 ### app.route it is way to call express routes 
 * You can create chainable route handlers for a route path by using app.route()
 * Use the express.Router class to create modular, mountable route handlers
 ``` 
const express = require('express')
const router = express.Router()
```

* Use express.Router() multiple times to define groups of routes
 * Apply the express.Router() to a section of our site using app.use()
* Use route middleware to process requests
* Use route middleware to validate parameters using .param()
* Use app.route() as a shortcut to the Router to define multiple requests on a route



