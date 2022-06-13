## JWT : Json web token 
* what is JWT : jason web token it is an open standered that any one can use it and  it used to securely transfer data between two user 
* digitally signed : that mean the information is verified and trusted 
* compact : that can we send it as URL, post , HTTP header 
and fast transmission
* self contained : that is mean the token containe information about the user 

### the jason web token 
* has form like aaaaaaaaaaaaaaaaaaaaa.bbbbbbbbbbbbbbbb.ccccccccccccc
    * a part is the **Header** 
        * the header contain algorithim and the JWT type
    * b part is the **payload**
        * which contains the claims. Claims are  object, that contain the user details 
     * c part is the **signture**
        * it is addation to make token more secure ,To create the signature part you have to take the encoded header, the encoded payload, a secret, the algorithm specified in the header, and sign that.

![link](./class7%20image/jwt-token.png)

### When should you use JSON Web Tokens?
* Authorization: This is the most common scenario for using JWT. Once the user is logged in, each subsequent request will include the JWT, allowing the user to access routes, services, and resources that are permitted with that token
* Information Exchange: JSON Web Tokens are a good way of securely transmitting information between parties. Because JWTs can be signed—for example, using public/private key pairs—you can be sure the senders are who they say they are
* 
![link](./class7%20image/client-credentials-grant.png)

### Why should we use JSON Web Tokens?
Let's talk about the benefits of JSON Web Tokens (JWT) when compared to Simple Web Tokens (SWT) and Security Assertion Markup Language Tokens (SAML).

As JSON is less verbose than XML, when it is encoded its size is also smaller, making JWT more compact than SAML. This makes JWT a good choice to be passed in HTML and HTTP environments

### **What Happens If Your JWT Is Stolen?**
![link](./class7%20image/if%20JWT%20stolen.png)
* All of us know what happens if our user credentials (email and password) are discovered by an attacker: they can log into our account . But a lot of modern applications are using JSON Web Tokens (JWTs) to manage user sessions—what happens if a JWT is compromised? Because more and more applications are using token-based authentication

## Finally How are JSON Web Tokens Used?
![link](./class7%20image/how-you-use.jpg)
* JWTs are typically used as session identifiers for web applications, mobile applications, and API services. But, unlike traditional session identifiers which act as nothing more than a pointer to actual user data on the server-side, JWTs typically contain user data directly

### we can install this as depandance 
$ npm install jsonwebtoken




