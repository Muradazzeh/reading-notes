## Authentication


### Securing Passwords with Bcrypt Hashing Function
* Passwords are the first line of defense against cyber criminals. It is the most vital secret of every activity we do over the internet and also a final check to get into any of your user account
 * Cryptographic hash algorithms: general purpose hash functions, designed to calculate a digest of huge amounts of data in as short a time as possible

 ### PROBLEMS WITH CRYPTOGRAPHIC HASH ALGORITHM
 * Brute Force attack: Hashes can't be reversed, so instead of reversing the hash of the password, an attacker can simply keep trying different inputs until he does not find the right now that generates the same hash value

 * Hash Collision attack: Hash functions have infinite input length and a predefined output length, so there is inevitably going to be the possibility of two different inputs that produce the same output hash

 #### BCrypt, IT's SLOW AND STRONG AS HELL
To overcome such issues, we need algorithms which can make the brute force attacks slower and minimize the impact

## Basic access authentication
* is a method for an HTTP user agent (e.g. a web browser) to provide a user name and password when making a request. In basic HTTP authentication, a request contains a header field in the form of Authorization: Basic <credentials>, where credentials is the Base64 encoding of ID and password joined by a single colon:

* The BA mechanism does not provide confidentiality protection for the transmitted credentials. They are merely encoded with Base64 in transit and not encrypted or hashed in any way. Therefore, basic authentication is typically used in conjunction with HTTPS to provide confidentiality

### Protocol
* Server side
When the server wants the user agent to authenticate itself towards the server after receiving an unauthenticated request, it must send a response with a HTTP 401 Unauthorized status and a WWW-Authenticate header field
* Client side
When the user agent wants to send authentication credentials to the server, it may use the Authorization header field
    * For example, if the browser uses Aladdin as the username and open sesame as the password, then the field's value is the Base64 encoding of Aladdin:open sesame, or QWxhZGRpbjpvcGVuIHNlc2FtZQ==. Then the Authorization header field will appear as:

Authorization: Basic QWxhZGRpbjpvcGVuIHNlc2FtZQ==

## Authentication
*  is the process of verifying that an individual, entity or website is whom it claims to be. Authentication in the context of web applications is commonly performed by submitting a username or ID and one or more items of private information that only a given user should know

### Authentication General Guidelines
*  User IDs
Make sure your usernames/user IDs are case-insensitive. 
*  Implement Proper Password Strength Controls
A key concern when using passwords for authentication is password strength

### Authentication and Error Messages
Incorrectly implemented error messages in the case of authentication functionality can be used for the purposes of user ID and password enumeration. An application should respond (both HTTP and HTML) in a generic manner.

* Authentication Responses¶
Using any of the authentication mechanisms (login, password reset or password recovery), an application must respond with a generic error message regardless of whether:

The user ID or password was incorrect.
The account does not exist.
The account is locked or disabled. 

### Protect Against Automated Attacks
* Multi-Factor Authentication
* Account Lockout
* CAPTCHA

## bcrypt
* A library to help you hash passwords

### Install via NPM
* in the terminal we type this code 
````
npm install bcrypt
```` 
#### Usage
async (recommended)
````
const bcrypt = require('bcrypt');
const saltRounds = 10;
const myPlaintextPassword = 's0/\/\P4$$w0rD';
const someOtherPlaintextPassword = 'not_bacon';
`````

* to hash password 
`````
bcrypt.genSalt(saltRounds, function(err, salt) {
    bcrypt.hash(myPlaintextPassword, salt, function(err, hash) {
        // Store hash in your password DB.
    });
});
`````
* To check a password:
````
// Load hash from your password DB.
bcrypt.compare(myPlaintextPassword, hash, function(err, result) {
    // result == true
});
bcrypt.compare(someOtherPlaintextPassword, hash, function(err, result) {
    // result == false
});
````