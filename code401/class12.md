# Socket.io
### Web Sockets
* What is web socket: is a computer communications protocol, providing full-duplex communication channels over a single TCP connection

* the WebSocket protocol enables interaction between a web browser (or other client application) and a web server with lower overhead than half-duplex alternatives such as HTTP polling, facilitating real-time data transfer from and to the server.

* To establish a WebSocket connection, the client sends a WebSocket handshake request, for which the server returns a WebSocket handshake response

## Socket.IO 
* is a JavaScript library for real-time web applications. It enables real-time, bi-directional communication between web clients and servers. It has two parts − a client-side library that runs in the browser, and a server-side library for node.js. Both components have an identical API

### Real-time Applications 
* Instant messengers
* Push Notifications
* Collaboration Applications
* Online Gaming

* we have to prepare express server using npm , and we have to install socket io 
````
npm install --save express socket.io
````

* and this is small example how we use sockit io with the express server 

````
var app = require('express')();
var http = require('http').Server(app);
var io = require('socket.io')(http);

app.get('/', function(req, res){ res.sendFile('E:/test/index.html');
});

//Whenever someone connects this gets executed
io.on('connection', function(socket){
   console.log('A user connected');
   
   //Whenever someone disconnects this piece of code executed
   socket.on('disconnect', function () {
      console.log('A user disconnected');
   });
});
http.listen(3000, function(){
   console.log('listening on *:3000');
});
``````

### Socket.IO - Error Handling
The client API provides us with following built in events −

* Connect − When the client successfully connects.

* Connecting − When the client is in the process of connecting.

* Disconnect − When the client is disconnected.

* Connect_failed − When the connection to the server fails.

* Error − An error event is sent from the server.

* Message − When the server sends a message using the send function.

* Reconnect − When reconnection to the server is successful.

* Reconnecting − When the client is in the process of connecting.

* Reconnect_failed − When the reconnection attempt fails.


## Difference Between WebSocket and Socket.io
* WebSocket is the communication Protocol that provides bidirectional communication between the Client and the Server over a TCP connection; WebSocket remains open all the time, so they allow real-time data transfer. When clients trigger the request to the server, it does not close the connection on receiving the response; it rather persists and waits for the Client or server to terminate the request.

* Socket.IO is a library that enables real-time and full-duplex communication between the Client and the Web servers. It uses the WebSocket protocol to provide the interface. Generally, it is divided into two parts; both WebSocket vs Socket.io are event-driven libraries.

* Client-Side: it is the library that runs inside the browser
* Server Side: It is the library for Node.js

|  No. | WebSocket                                                      | Socket.io                                                                      |   |   |   |   |   |   |   |
|------|----------------------------------------------------------------|--------------------------------------------------------------------------------|---|---|---|---|---|---|---|
| 1    | It is the protocol that is established over the TCP connection |  It is the library to work with WebSocket                                      |   
| 2    | It provides full-duplex communication on TCP connections.      | Provides the event-based communication between browser and server.             |  
| 3    | Proxy and load balancer is not supported in WebSocket.         | A connection can be established in the presence of proxies and load balancers. | 
| 4    | It doesn’t support broadcasting.                               | It supports broadcasting.                                                      |  
| 5    | 	It doesn’t have a fallback option.                            | 	It supports fallback options.                                                 |