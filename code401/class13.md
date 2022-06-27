## Message Queues

### Get started
* In this guide we’ll create a basic chat application. It requires almost no basic prior knowledge of Node.JS or Socket.IO, so it’s ideal for users of all knowledge levels.

### Introduction
* Writing a chat application with popular web applications stacks like LAMP (PHP) has normally been very hard. It involves polling the server for changes, keeping track of timestamps, and it’s a lot slower than it should be.

* Sockets have traditionally been the solution around which most real-time chat systems are architected, providing a bi-directional communication channel between a client and a server.

* This means that the server can push messages to clients. Whenever you write a chat message, the idea is that the server will get it and push it to all other connected clients.

### The web framework
The first goal is to set up a simple HTML webpage that serves out a form and a list of messages. We’re going to use the Node.JS web framework express to this end. Make sure Node.JS is installed.

### Integrating Socket.IO
Socket.IO is composed of two parts:

* A server that integrates with (or mounts on) the Node.JS HTTP Server socket.io
* A client library that loads on the browser side socket.io-client
During development, socket.io serves the client automatically for us, as we’ll see, so for now we only have to install one module:

npm install socket.io
That will install the module and add the dependency to package.json. Now let’s edit index.js to add it:

## Rooms
* A room is an arbitrary channel that sockets can join and leave. It can be used to broadcast events to a subset of clients:

### Joining and leaving
* You can call join to subscribe the socket to a given channel:
````
io.on("connection", (socket) => {
  socket.join("some room");
});
````
And then simply use to or in (they are the same) when broadcasting or emitting:
````
io.to("some room").emit("some event");

````

## Default room
* Each Socket in Socket.IO is identified by a random, unguessable, unique identifier Socket#id. For your convenience, each socket automatically joins a room identified by its own id

## Disconnection
Upon disconnection, sockets leave all the channels they were part of automatically, and no special teardown is needed on your part.

You can fetch the rooms the Socket was in by listening to the disconnecting event:
````
io.on("connection", socket => {
  socket.on("disconnecting", () => {
    console.log(socket.rooms); // the Set contains at least the socket ID
  });

  socket.on("disconnect", () => {
    // socket.rooms.size === 0
  });
});
````

## Room events
Starting with socket.io@3.1.0, the underlying Adapter will emit the following events:

* create-room (argument: room)
* delete-room (argument: room)
* join-room (argument: room, id)
* leave-room (argument: room, id)
Example:

`````
io.of("/").adapter.on("create-room", (room) => {
  console.log(`room ${room} was created`);
});

io.of("/").adapter.on("join-room", (room, id) => {
  console.log(`socket ${id} has joined room ${room}`);
});
`````

## Namespaces
A Namespace is a communication channel that allows you to split the logic of your application over a single shared connection (also called "multiplexing").
