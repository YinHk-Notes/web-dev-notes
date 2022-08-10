## Websocket

> The WebSocket API is an advanced technology that makes it possible to open a **two-way interactive communicatio**n session between the user's browser and a server. With this API, you can send messages to a server and receive event-driven responses without having to poll the server for a reply.

> A WebSocket is a **persistent connection** between a client and server.

> WebSocket is a computer communications protocol providing full-duplex communication channels over a single TCP connection.

> WebSocket is especially great for services that require continuous data exchange, e.g. online games, real-time trading systems and so on.



> **HTTP protocol**: HTTP is **unidirectional** where the **client sends the request and the server sends the response.** Let’s take an example when a user sends a request to the server this request goes in the form of HTTP or HTTPS, after receiving a request server send the response to the client, **each request is associated with a corresponding response**, ***after sending the response the connection gets closed***, each HTTP or HTTPS request **establish the new connection to the server every time and after getting the response the connection gets terminated by itself**. 

> **WebSocket**: WebSocket is **bidirectional**, a full-duplex protocol that is used in the same scenario of client-server communication, unlike HTTP it starts from ws:// or wss://. ***It is a stateful protocol, which means the connection between client and server will keep alive until it is terminated by either party (client or server)***. After closing the connection by either of the client and server, the connection is terminated from both ends. 
