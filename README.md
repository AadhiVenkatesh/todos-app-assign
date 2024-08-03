Project Overview

This project is a web application that allows users to register, log in, and
manage their to-do items. The backend is built using Node.js with Express and
SQLite, while the frontend is developed with React. The application features
user authentication, CRUD operations for to-do items, and JWT-based session
management.

Setup Instructions

Prerequisites

 Node.js and npm (Node Package Manager) installed on your machine.
 SQLite installed for the database.
 
Backend Setup

1. Clone the Repository
git clone https://github.com/your-repo/your-project.git
cd your-project/backend
2. Install Dependencies
npm install
3. Create the .env File
Create a file named .env in the backend directory with the following
content:
JWT_SECRET=your_jwt_secret_key
Replace your_jwt_secret_key with a secure random key.
4. Run Database Migrations
The database schema will be set up automatically when you run the
server for the first time.
5. Start the Server
node server.js
The backend server will start on http://localhost:4000.

Frontend Setup

1. Navigate to the Frontend Directory
cd frontend
2. Install Dependencies
npm install
3. Run the Development Server
npm start
The React application will start on http://localhost:4000.

Technologies Used

 Node.js: JavaScript runtime used for the backend.
 Express: Web framework for building the REST API.
 SQLite: Lightweight database for storing user and to-do data.
 bcryptjs: Library for hashing passwords securely.
 jsonwebtoken: Library for creating and verifying JWTs.
 cors: Middleware to enable cross-origin requests.
 dotenv: Library to manage environment variables.
 React: JavaScript library for building the user interface.
 axios: HTTP client for making API requests from the frontend.

API Endpoints

User Endpoints

 POST /register
 
o Description: Register a new user.

o Request:

{
 "username": "string",
 "password": "string"
}

o Response:

{
 "message": "User registered successfully."
}

 POST /login

o Description: Log in a user and receive a JWT.

o Request:

{
 "username": "string",
 "password": "string"
}

o Response:

{
 "token": "jwt_token"
}

To-Do Endpoints

 POST /todos

o Description: Add a new to-do item.

o Request:

{
 "description": "string",
 "status": "string"
}

o Response:

{
 "id": "integer",
 "description": "string",
 "status": "string"
}

 GET /todos

o Description: Retrieve all to-do items for the logged-in user.

o Response:

[
 {
 "id": "integer",
 "description": "string",
 "status": "string"
 }
]

 PUT /todos/

o Description: Update a specific to-do item.

o Request:

{
 "description": "string",
 "status": "string"
}

o Response:

{
 "id": "integer",
 "description": "string",
 "status": "string"
}

 DELETE /todos/

o Description: Delete a specific to-do item.

o Response:

{
 "message": "Todo item deleted successfully."
}

Database Schema

Users Table

 id: INTEGER, Primary Key, Auto Increment

 username: TEXT, Unique

 password: TEXT

Todos Table

 id: INTEGER, Primary Key, Auto Increment

 user_id: INTEGER, Foreign Key (references Users.id)

 description: TEXT

 status: TEXT
