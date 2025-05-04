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
