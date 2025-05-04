# Authentication API

## Setup
1. Clone repository
2. Install dependencies: `npm install`
3. Create `.env` file with your MongoDB URI and JWT secret
4. Start server: `npm run dev`

## API Endpoints
- POST /api/auth/register - User registration
- POST /api/auth/login - User login
- GET /api/users/me - Get current user (protected)


# Postman Documentation:

Authentication API Documentation
1. Register User
URL: POST {{base_url}}/api/auth/register

Headers:

Content-Type: application/json

Request Body:

json
{
  "username": "testuser",
  "email": "test@example.com",
  "password": "password123"
}
Success Response (201 Created):

json
{
  "message": "User registered successfully"
}
Error Responses:

409 Conflict (Duplicate user):

json
{
  "message": "User already exists"
}
400 Bad Request (Validation error):

json
{
  "message": "Validation failed",
  "errors": ["email must be valid", "password must be at least 6 characters"]
}
2. User Login
URL: POST {{base_url}}/api/auth/login

Headers:

Content-Type: application/json

Request Body:

json
{
  "email": "test@example.com",
  "password": "password123"
}
Success Response (200 OK):

json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
Error Responses:

401 Unauthorized:

json
{
  "message": "Invalid credentials"
}
3. Get Current User (Protected)
URL: GET {{base_url}}/api/users/me

Headers:

Authorization: Bearer <JWT_TOKEN>

Content-Type: application/json

Success Response (200 OK):

json
{
  "id": "64c3a5b7e8b1b2a3d4f5g6h7",
  "username": "testuser",
  "email": "test@example.com"
}
Error Responses:

401 Unauthorized:

json
{
  "message": "Authentication invalid"
}
