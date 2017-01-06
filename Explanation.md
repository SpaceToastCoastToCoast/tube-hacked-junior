# tube-hacked-junior - Explanation of HTTP

### Getting started
You have already worked with sockets and connections, sending plain text between a client and a server. At its most basic level, this is how servers in the real world communicate. Web servers use HyperText Transfer Protocol (HTTP) to standardize communication between clients and servers and provide extra information on the content of the message being sent. HTTP is just plaintext (strings) that follows a specific structure.

### How is this different from using sockets?
When you write a program with sockets, the connection between the client and server is kept open for the whole time the client is connected. Web servers, which may have millions of clients connecting to them, don't have enough open ports to keep everyone connected. The HTTP protocol breaks up communication between the client and server into requests and responses: the request comes from the client, and as soon as the server sends a response, it closes the connection to that client and moves onto the next one. This means it is not real-time, two-way communication like a socket connection, but simply a very quick zigzagging of information between the client and the server.

Web servers also have to do a little more than sending and receiving plain text. They need to know what the client wants from them, and they need a universally standardized way to know which type of message they are being sent. All web servers support HTTP, which wraps plain text messages in some information about where they are going and what they are doing. 

#### HTTP request types
The first parameter of an HTTP request is its type. This tells the server what the client wants to do with what the server will send it. Most commonly, we use GET to ask for a response we will display to the client, and POST to tell the server that the client is sending them information. After the request type, the request destination is given.

The request type and destination is only used by client-to-server messages. The server sends back a response, which follows the same structure but has a status code instead of a request type. You have probably seen 404 status codes before when the server can't find a page. If the request came through without any problems, the server sends the 200 (OK) code here.

#### Headers
HTTP also allows for headers on messages, which come before the actual content and give information on how the server should structure its response. The headers can contain information on what kind of browser or program is sending the request, what format the request's content is in, what file type it expects the response to be, whether the client is logged into the system, or others. Think of it like the wrapper on a candy bar: you're not going to eat it (hopefully) but it tells you the ingredients and nutritional information of what's inside.

#### Content
Finally, after the headers, the message itself is placed at the end of the request or response. This could be as short and simple as a plaintext response, or as long as a full HTML file.

### Example request
GET /index.html Content-Type:text/plain Accept:text/plain Hi, server!

### Example response
200 OK Content-Type:text/plain Hello, client!
