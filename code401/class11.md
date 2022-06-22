## Event-Driven Programming in Node.js

* Event-Driven Programming is a logical pattern that we can choose to confine our programming within to avoid issues of complexity and collision. In this article we’re going to go over how Event-Driven Programming works and how we can make the best use of it in our Node.js projects

* EventEmitter
Node.js natively provides us with a useful module called EventEmitter that allows us to get started incorporating Event-Driven Programming in our project right away. Of course, creating our own version of EventEmitter wouldn’t be much of a challange, and in fact there are several modules published on npm such as EventEmitter2 and EventEmitter3 which promise a faster performance than the native EventEmitter.

````
const EventEmitter = require('events').EventEmitter;
const myEventEmitter = new EventEmitter;

`````
* Removing Listeners This could be for performance reasons (the event is no longer needed) or to avoid memory leaks (if an event listener references an object that is no longer needed, it won’t be able to be garbage-collected. This can lead to a build up of unnecessary objects).
> To remove event listeners in EventEmitter we can use the removeListener or removeAllListeners method
### Object Oriented Programming + Event-Driven Programming

* The Object Oriented approach promotes the idea that all behavior of an individual unit (or object) be handled from code within that unit. Using this approach, applications are built with many different units that all speak to and interact with each other

#### Node.js v18.4.0 documentation
[link for Events](https://nodejs.org/api/events.html#passing-arguments-and-this-to-listeners)
