# Feature: User Authentication and Todo Management

## Description
This Flask app should provide basic user authentication (register, login, logout) and a simple Todo list management (CRUD operations).

## Endpoints

### User Authentication
- POST /register : register a new user with `username`, `email`, `password`
- POST /login : authenticate user with `username` and `password`
- GET /logout : log out current user

### Todo Management
- GET /todos : list all todos for logged-in user
- POST /todos : create a new todo (`title`, `description`)
- PUT /todos/<id> : update a todo
- DELETE /todos/<id> : delete a todo

## Models

### User
- id: int
- username: str
- email: str
- password_hash: str

### Todo
- id: int
- user_id: int
- title: str
- description: str
- completed: bool

## Tests

### User Authentication
- Register with valid credentials should succeed
- Register with existing username/email should fail
- Login with correct credentials should succeed
- Login with wrong credentials should fail
- Logout should clear session

### Todo Management
- Creating a todo should succeed for logged-in user
- Listing todos should return all user's todos
- Updating a todo should modify its content
- Deleting a todo should remove it
- Accessing todos without login should fail
