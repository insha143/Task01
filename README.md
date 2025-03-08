Basic Authentication System with Node.js
Features:
User Registration:

Register with username and password.
Passwords are hashed using bcrypt.
Prevents duplicate usernames.
User Login:

Login with username and password.
Returns a JWT token upon successful login.
JWT Authentication:

JWT token is valid for 1 hour.
Protected Route:

Requires JWT token for access.
Technologies Used:
Node.js & Express: API server.
MongoDB & Mongoose: Database.
bcrypt: Password hashing.
jsonwebtoken (JWT): Authentication.
dotenv: Environment variables.
Installation:
Clone the repo:
bash
Copy
Edit
git clone https://github.com/insha143/Task01.git
cd Task01
Install dependencies:
bash
Copy
Edit
npm install
Set up .env file with:
ini
Copy
Edit
PORT=5000
MONGO_URI=mongodb://localhost:27017/auth_system
JWT_SECRET=your_jwt_secret
Start the server:
bash
Copy
Edit
npm start
API Endpoints:
POST /api/users/register

URL: http://localhost:5000/api/users/register
Body:
json
Copy
Edit
{ "username": "user123", "password": "password123" }
Response: Success or 400 if username exists.
POST /api/users/login

URL: http://localhost:5000/api/users/login
Body:
json
Copy
Edit
{ "username": "user123", "password": "password123" }
Response:
json
Copy
Edit
{ "token": "jwt-token" }
Protected Route

URL: http://localhost:5000/protected
Header: Authorization: Bearer <token>
Response: Protected data if valid token.
Postman Collection:
POST http://localhost:5000/api/users/register for registration.
POST http://localhost:5000/api/users/login for login (returns JWT).
Use the JWT token in the Authorization header for protected routes.
