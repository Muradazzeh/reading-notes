# DEFINITION OF ROLE-BASED ACCESS CONTROL (RBAC)
Role-based access control (RBAC) restricts network access based on a person's role within an organization and has become one of the main methods for advanced access control. The roles in RBAC refer to the levels of access that employees have to the network.

## EXAMPLES OF ROLE-BASED ACCESS CONTROL
Through RBAC, you can control what end-users can do at both broad and granular levels. You can designate whether the user is an administrator, a specialist user, or an end-user, and align roles and access permissions with your employees’ positions in the organization. Permissions are allocated only with enough access as needed for employees to do their jobs.

## Some of the designations in an RBAC tool can include:

* Management role scope – it limits what objects the role group is allowed to manage.
* Management role group – you can add and remove members.
* Management role – these are the types of tasks that can be performed by a specific role group.
* Management role assignment – this links a role to a role group.


## BENEFITS OF RBAC
* Reducing administrative work and IT support. 
* Maximizing operational efficiency.
* Improving compliance. 

# cookies
* <CookiesProvider />
Set the user cookies

* On the server, the cookies props must be set using req.universalCookies or new Cookie(cookieHeader)
```
useCookies([dependencies])
Access and modify cookies using React hooks.

const [cookies, setCookie, removeCookie] = useCookies(['cookie-name']);
```

## dependencies (optional)
Let you optionally specify a list of cookie names your component depend on or that should trigger a re-render. If unspecified, it will render on every cookie change.

* cookies
Javascript object with all your cookies. The key is the cookie name.

* setCookie(name, value, [options])
Set a cookie value

    * name (string): cookie name
    * value (string|object): save the value and stringify the object if needed
    * options (object): Support all the cookie options from RFC 6265
    * path (string): cookie path, use / as the path if you want your cookie to be accessible on all pages
    * expires (Date): absolute expiration date for the cookie
    * maxAge (number): relative max age of the cookie from when the client receives it in seconds
    * domain (string): domain for the cookie (sub.domain.com or .allsubdomains.com)
    * secure (boolean): Is only accessible through HTTPS?
    * httpOnly (boolean): Can only the server access the cookie? Note: You cannot get or set httpOnly cookies from the browser, only the server.
    * sameSite (boolean|none|lax|strict): Strict or Lax enforcement
    * removeCookie(name, [options])
Remove a cookie

```
import React from 'react';
import App from './App';
import { CookiesProvider } from 'react-cookie';

export default function Root() {
  return (
    <CookiesProvider>
      <App />
    </CookiesProvider>
  );
}
```
```
import React from 'react';
import { useCookies } from 'react-cookie';

import NameForm from './NameForm';

function App() {
  const [cookies, setCookie] = useCookies(['name']);

  function onChange(newName) {
    setCookie('name', newName, { path: '/' });
  }

  return (
    <div>
      <NameForm name={cookies.name} onChange={onChange} />
      {cookies.name && <h1>Hello {cookies.name}!</h1>}
    </div>
  );
}

export default App;
```
# Usage

```
import { Component } from 'react'
import cookie from 'react-cookies'
 
import LoginPanel from './LoginPanel'
import Dashboard from './Dashboard'
 
class MyApp extends Component {
  constructor () {
    super()
 
    this.onLogin = this.onLogin.bind(this)
    this.onLogout = this.onLogout.bind(this)
  }
 
  componentWillMount() {
    this.state =  { userId: cookie.load('userId') }
  }
 
  onLogin(userId) {
    this.setState({ userId })
    cookie.save('userId', userId, { path: '/' })
  }
 
  onLogout() {
    cookie.remove('userId', { path: '/' })
  }
 
  render() {
    const { userId } = this.state
 
    if (!userId) {
      return <LoginPanel onSuccess={this.onLogin} />
    }
 
    return <Dashboard userId={userId} />
  }
}
```