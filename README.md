Railway Management System API
Prerequisites

Node.js (v16+)
PostgreSQL
npm

Setup Instructions
1. Clone Repository
bashCopygit clone https://github.com/yourusername/railway-management-system.git
cd railway-management-system
2. Install Dependencies
bashCopynpm install
3. Database Setup
Create PostgreSQL Database
bashCopy# Create database
createdb railway_db

# Alternative manual method
psql
CREATE DATABASE railway_db;
4. Environment Configuration
Create .env file in project root:
CopyDATABASE_URL="postgresql://username:password@localhost:5432/railway_db"
JWT_SECRET="your_unique_secret_key"
ADMIN_API_KEY="your_generated_admin_api_key"
PORT=3000
5. Prisma Configuration
bashCopy# Generate Prisma Client
npx prisma generate

# Run database migrations
npx prisma migrate dev --name init
6. Generate Admin API Key
bashCopy# Use OpenSSL
openssl rand -hex 32
7. Run Application
bashCopy# Development Mode
npm run dev

# Production Mode
npm start
API Endpoints
Authentication

POST /auth/register: User Registration
POST /auth/login: User Login
GET /auth/profile: Get User Profile

Train Management

POST /trains/add: Add Train (Admin Only)
GET /trains/availability: Check Train Availability

Booking

POST /bookings/book: Book Train Seat
GET /bookings/details: Get Booking Details
