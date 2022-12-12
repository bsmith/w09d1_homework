# Diagram

!(diagram)[diagram.jpeg]

# Questions

## Q: "What is responsible for defining the routes of the games resource?"

createRouter inside helpers/create_router.js

## Q: "What do you notice about the folder structure? Whats the client responsible for? Whats the server responsible for?"

The server is responsible for the API routes, seeding the database.  Talking to the database is inside the routes, not separate.

The client has 'components' that are the View (they just display data), the 'container' acts as a Controller (moving data between the components and the services), the 'services' issue requests to the APIs and handle the responses.

The server seems to handle errors and passes them back to the client, the client doesn't appear to handle them.

## Q: "What are the the responsibilities of server.js?"

server.js connects to the database and passes the database's collection object to the helper for creating the router.  It configures express with middleware and the router.

## Q: "What are the responsibilities of the gamesRouter?"

gamesRouter implements the routes of the API by issuing the database queries and forming API responses.

## Q: "What process does the the client (front-end) use to communicate with the server?"

The client uses fetch in GamesService.

## Q: "What optional second argument does the fetch method take? And what is it used for in this application? Hint: See Using Fetch on the MDN docs"

The second parameter configures the request.  This app uses it to change the method, the request body and the request headers.  Instead of using the second parameter you can create a Request object and pass that to fetch.

## Q: "Which of the games API routes does the front-end application consume (i.e. make requests to)?"

It only uses GET /, POST / and delete /:id relative to the baseURL which gives a path prefix of /api/games/.

## Q: "What are we using the MongoDB Driver for?"

The MongoDB Driver is used to make asynchronous database requests in the API router.

