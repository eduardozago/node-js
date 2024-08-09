# Node.js

Node.js fundamentals, including first server and introduction to streams in Node.js

## Requirements

The following resources (necessary for execution) were used for this project:
 - [nvm](https://github.com/nvm-sh/nvm)
 - [httpie](https://httpie.io/)

## Server

Server created with the aim of exploring http requests and their routes with different methods, such as GET and POST, including the use of headers and status codes for the different results of each request.

To run the server:
```
npm run dev 
```

## Streams

Stream implementation in Node.js in the forms of writing, reading and transformation.

Demonstrative use in "streams/fundamentals.js" simulating partial reading, transformation and writing using streams, to execute:
```
node streams/fundamentals.js
```

### Streams - Simulation

Simulation of an upload using streams in "streams/fake-upload-to-http-stream.js" to a server in "streams/stream-http-server.js" that transforms the data as it is received.

To run the server:
```
node streams/stream-http-server.js
```

To upload:
```
node streams/fake-upload-to-http-stream.js
```