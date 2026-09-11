# REST API with Authentication

A RESTful API built with Node.js, Express, and PostgreSQL featuring JWT-based authentication and Zod request validation.

## Features
- User signup with hashed passwords (bcrypt)
- Login with JWT token generation
- Protected routes using JWT middleware
- Request validation with Zod

## Tech Stack
- Node.js, Express.js
- PostgreSQL
- bcrypt, jsonwebtoken, zod

## Setup
1. Clone the repo
2. Run `npm install`
3. Create a `.env` file (see `.env.example`)
4. Create the `users` table in PostgreSQL (see below)
5. Run `npm run dev`

## Database Schema
\`\`\`sql
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  name VARCHAR(100) NOT NULL,
  email VARCHAR(100) UNIQUE NOT NULL,
  password VARCHAR(255) NOT NULL,
  created_at TIMESTAMP DEFAULT NOW()
);
\`\`\`

## API Endpoints
| Method | Endpoint | Description | Auth Required |
|--------|----------|--------------|----------------|
| POST | /api/auth/signup | Register new user | No |
| POST | /api/auth/login | Login and get JWT token | No |
| GET | /api/auth/profile | Get logged-in user profile | Yes |