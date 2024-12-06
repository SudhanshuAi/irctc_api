
`# Railway Management System API

## Prerequisites

- **Node.js** (v16+)
- **PostgreSQL**
- **npm**

## Setup Instructions

### 1. Clone Repository
```bash
git clone https://github.com/SudhanshuAi/irctc_api.git
cd railway-management-system` 

## 2. Install Dependencies

`npm install` 

### 3. Database Setup

#### Create PostgreSQL Database

`# Create database
createdb railway_db

### 4. Environment Configuration

Create a `.env` file in the project root and add the following:


`DATABASE_URL="postgresql://username:password@localhost:5432/railway_db"
JWT_SECRET="your_unique_secret_key"
ADMIN_API_KEY="your_generated_admin_api_key"
PORT=3000` 

### 5. Prisma Configuration

`# Generate Prisma Client
npx prisma generate

# Run database migrations
npx prisma migrate dev --name init` 

### 6. Generate Admin API Key

`# Use OpenSSL
openssl rand -hex 32` 

### 7. Run Application

#### Development Mode

`npm run dev` 

----------

## API Endpoints

### Authentication

-   `POST /auth/register`: User Registration
-   `POST /auth/login`: User Login
-   `GET /auth/profile`: Get User Profile

### Train Management

-   `POST /trains/add`: Add Train (Admin Only)
-   `GET /trains/availability`: Check Train Availability

### Booking

-   `POST /bookings/book`: Book Train Seat
-   `GET /bookings/details`: Get Booking Details
