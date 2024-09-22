# Node.js - Fundamentals

This section aims to provide a hands-on understanding of key Node.js concepts, including handling HTTP requests and responses, working with streams, and integrating with databases.

## Table of contents
- [Server](#server)
    - [Endpoints](#endpoints)
- [Streams](#streams)
- [Streams simulation](#streams-simulation)
- [Buffer](#buffer)
- [Middleware](#middleware)
- [Database](#database)
- [Routes](#routes)
    - [Route parameters](#route-parameters)
    - [Query parameters](#query-parameters)

## Server

The purpose of the server was to investigate HTTP requests and their routes using various methods, including GET and POST, as well as the use of headers and status codes for different results of each request.

In this example, user information is set using POST and obtained via GET with JSON content type.

### Endpoints

-  /users (POST) : **Create** a new user and send data in the JSON format in the request body.
    - Example: `{"name": "John Doe", "email": "johndoe@email.com"}`
- /users (GET): **Get all** users in database into an array.
- /users/:id (PUT): **Update** user by `id`
- /users/:id (DELETE): **Delete** user by `id`

To run server:
```
npm run dev 
```

## Streams

Node.js stream implementation for writing, reading, and manipulation.

Use of streams to simulate partial reading, transformation, and writing is demonstrated in [fundamentals.js](streams/fundamentals.js). 

In this example, a readable stream reads one integer from 1 to 100 times per second. Next, use the transform stream to multiply by -1 and the writable stream to multiply by 10.

Run example:
```
node streams/fundamentals.js
```

## Streams simulation

Here, [fake-upload-to-http-stream.js](streams/fake-upload-to-http-stream.js) uses streams to simulate an upload to a server [stream-http-server.js](streams/stream-http-server.js) that alters the data it receives.

Run server:
```
node streams/stream-http-server.js
```

Run upload:
```
node streams/fake-upload-to-http-stream.js
```

## Buffer

A low-level format buffer is an effective way to read and write data to and from memory.

[buffer.js](streams/buffer.js) contains one example of a buffer. 

Run example:
```
node streams/buffer.js
```

## Middleware

Request and response interceptor. An example of how middleware transforms input and output into JSON content type may be found in [src/middlewares/json.js](src/middlewares/json.js).

## Database

To store data in a persistent format, a local database is created. A JSON file called [db.json](src/db.json) contains data that simulates a database. [database.js](src/middlewares/database.js) contains a class for database operations such as insert and select. "src/server.js" calls database operations using the database class. 

In this example, class Database is responsable to 

## Routes

In order to manage routes more effectively, a file named [routes.js](src/routes.js) was made. It uses an array of routes, with each item being an object that has route parameters:

- Method: request method
- Path: endpoint
- Handler: route function

Now, if a route exists in [Routes](src/routes.js), the [Server](src/server.js) will call it.

### Route parameters

The data supplied in url on `/users/:id` format, with `id` being a dynamic parameter that will be sent on url, is known as a route parameter. 

Dynamic parameters are located and checked using Regex in [BuildRoutePath](src/utils/build-route-path.js) to identify them. Inserted into the request parameters for use in the route function, if it a valid parameter. 

### Query parameters

To send optional data in a URL like `/users?search=John`, query parameters are utilized. 

As in [Route Parameters](#route-parameters), Regex is utilized to identify and verify these inputs. [BuildRoutePath](src/utils/build-route-path.js) is where it is implemented.