# Dynamic API Server
An Express/Node.js based server designed to be a “model agnostic” REST API server, which can perform CRUD operations on any data model

* Support all REST/HTTP methods
    * GET: Retrieve record(s) from a data source
All
    * One (by id)
    * Some (by filtering)
     * POST: Create a new record in a data source
    * PUT: Update a single full record in a data source
     * PATCH: Update part of a single record in a data source
    * DELETE: Delete a record in a data source

    ## Obey a standard output format
* Results will be returned in JSON format
* Results will be served with the correct HTTP header - application/json
* The GET Route, when not retrieving by ID, must return a full header, with count ,pages, and a results array
* All other routes must return a single object, representing the state of the entity following the operation

## Authentication Server / Module
An Express/Node.js based server using a custom “authentication” module that is designed to handle user registration and sign in using Basic, Bearer, or OAuth along with a custom “authorization” module that will grant/deny users access to the server based on their role or permissions level.

### Technical Requirements
The application will be created with the following overall architecture and methodologies

 * Node.js
* ES6 Classes and best practices
* ExpressJS Web Server, built modularly
“Auth” routes for handling the login and authentication system
* POST /signup to create an account
* POST /signin to login with Basic Auth
* GET /oauth
* Middleware for handling 404 and 500 conditions
* Middleware for handling each type of authentication
* Basic (username + password) to be used on the /signin route only
    * i.e. app.post('/signin', basicAuthentication, (req, res) => { ... })
    * OAuth (3rd Party) to be used on the /oauth route only
i.e. app.get('/oauth', OAuth, (req, res) => { ... })
* Handles the handshake process from a 3rd party OAuth system
* Bearer (token) to be used on any other route in the server * that requires a logged in user
* i.e. app.get('/secretstuff', tokenAuthentication, (req, res) => { ... })
* Middleware for handling authorization
* To be run after Bearer Middleware on routes to be protected
*  Accepts a “capability” as a parameter
i.e. app.delete('/secretstuff', tokenAuthRequired, capability('delete'), (req, res) => { ... })