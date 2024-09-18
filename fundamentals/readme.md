# Node.js - Fundamentals

This section aims to provide a hands-on understanding of key Node.js concepts, including handling HTTP requests and responses, working with streams, and integrating with databases.

## Table of contents
- [Server](#server)
    - [Endpoints](#endpoints)
- [Streams](#streams)
- [Streams simulation](#streams-simulation)

## Server

The purpose of the server was to investigate HTTP requests and their routes using various methods, including GET and POST, as well as the use of headers and status codes for different results of each request.

In this example, user information is set using POST and obtained via GET.

### Endpoints

- /users (POST): Set user data
- /users (GET): Get user data

To run server:
```
npm run dev 
```

## Streams

Node.js stream implementation for writing, reading, and manipulation.

Use of streams to simulate partial reading, transformation, and writing is demonstrated in "streams/fundamentals.js". 

In this example, a readable stream reads one integer from 1 to 100 times per second. Next, use the transform stream to multiply by -1 and the writable stream to multiply by 10.

Run example:
```
node streams/fundamentals.js
```

## Streams simulation

Here, "streams/fake-upload-to-http-stream.js" uses streams to simulate an upload to a server "streams/stream-http-server.js" that alters the data it receives.

Run server:
```
node streams/stream-http-server.js
```

Run upload:
```
node streams/fake-upload-to-http-stream.js
```