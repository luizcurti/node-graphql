# Node GraphQL API

Description
This project is a Node.js backend API implementation using GraphQL for querying and mutating data. It is built with a focus on modularity and scalability, ensuring that the API is easy to maintain and extend. The project also implements best practices like using Apollo Server for the GraphQL layer and includes authentication, authorization, and database interactions.

Features
GraphQL API: Use GraphQL queries and mutations to interact with the backend.
Apollo Server: For handling GraphQL requests.
Node.js & Express: Backend API built using Node.js and Express.
MongoDB: NoSQL database used to store data.
Authentication & Authorization: Secure endpoints with JWT tokens.
Modular & Scalable: Structured to easily add new features and endpoints.

Installation
Prerequisites
Make sure you have the following installed:

Node.js (>=14.0.0)

MongoDB (or MongoDB Atlas for cloud hosting)

Steps
Clone the repository:
git clone https://github.com/luizcurti/node-graphql.git

Navigate to the project directory:
cd node-graphql

Install dependencies:
npm test or  yarn test

Set up environment variables:

Create a .env file at the root of the project and add your environment variables. You can use .env.example as a reference.

MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
PORT=your_server_port
Run the application:
npm test or  yarn test

The server will start running on http://localhost:4000 (or the port you specified).

GraphQL Playground
Once the application is running, you can test your GraphQL queries and mutations by navigating to the following URL:

http://localhost:4000/graphql

This will open up the GraphQL Playground where you can interact with the API by writing GraphQL queries and mutations.

Authentication
This project includes JWT-based authentication for securing GraphQL mutations and queries. Upon logging in, the user receives a JWT token that must be included in the Authorization header for any subsequent requests that require authentication.

Example of login mutation:
graphql

mutation {
  login(email: "user@example.com", password: "password") {
    token
  }
}
Once you receive the token, include it in the Authorization header for protected queries:

Authorization: Bearer your_token_here
Example Queries

Get all users
graphql

query {
  users {
    id
    name
    email
  }
}

Get a single user by ID
graphql

query {
  user(id: "12345") {
    id
    name
    email
  }
}

Create a new user
graphql

mutation {
  createUser(name: "John Doe", email: "john.doe@example.com", password: "password123") {
    id
    name
    email
  }
}

Update user information
graphql

mutation {
  updateUser(id: "12345", name: "Updated Name") {
    id
    name
    email
  }
}

Delete a user
graphql

mutation {
  deleteUser(id: "12345") {
    id
    name
    email
  }
}

Technologies Used
Node.js: JavaScript runtime for the backend API.
Express: Web framework to handle HTTP requests.
Apollo Server: Framework for building GraphQL APIs.
MongoDB: NoSQL database for storing data.
Mongoose: ODM for MongoDB.
JWT: JSON Web Tokens for authentication and authorization.
dotenv: For loading environment variables from a .env file.

Running Tests
To run the tests for the application, you can use the following command:
npm test or  yarn test

Contribution
If you'd like to contribute to this project, feel free to fork it and create a pull request. Please ensure that your code adheres to the existing style and that you write tests for any new features.

Steps to contribute
Fork the repository.

Create a new branch (git checkout -b feature/your-feature-name).

Make your changes and add tests.

Commit your changes (git commit -m 'Add your changes').

Push to your fork (git push origin feature/your-feature-name).

Create a pull request.  Acknowledgments
* Apollo Server for building GraphQL APIs.
* Mongoose for MongoDB object modeling.
* JWT for authentication and securing the API.
