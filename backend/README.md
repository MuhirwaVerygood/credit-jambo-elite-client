# Client Backend

NestJS backend API for the Credit Jambo Elite client portal, providing user-facing functionality for managing personal savings accounts and transactions.

## Features

- User registration and authentication
- Personal savings account management
- Transaction processing (deposits/withdrawals)
- Device verification for security
- JWT-based authentication
- Prisma ORM with PostgreSQL
- RESTful API design

## Prerequisites

- Node.js (v18 or higher)
- PostgreSQL database
- Docker (for database)

## Installation

1. **Navigate to the client backend directory**
   ```bash
   cd Client/backend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Setup environment variables**
   ```bash
   cp .env.example .env
   ```
   Edit `.env` with your configuration:
   - `DATABASE_URL`: PostgreSQL connection string
   - `JWT_SECRET`: Secure JWT secret key
   - `PORT`: 3000 (default)

4. **Start the database**
   ```bash
   # From project root
   docker-compose up -d
   ```

5. **Run database migrations**
   ```bash
   npx prisma migrate dev
   ```

6. **Generate Prisma client**
   ```bash
   npx prisma generate
   ```

## Running the Application

### Development
```bash
npm run start:dev
```
The API will be available at `http://localhost:3000`

### Production
```bash
npm run build
npm run start:prod
```

## API Endpoints

### Authentication
- `POST /auth/register` - User registration
- `POST /auth/login` - User login
- `POST /auth/logout` - User logout

### Savings Management
- `GET /savings/balance` - Get account balance
- `POST /savings/deposit` - Make a deposit
- `POST /savings/withdraw` - Make a withdrawal
- `GET /savings/transactions` - Get transaction history

### Device Management
- `POST /auth/verify-device` - Verify device for account access

## Database Schema

The client backend uses the shared database schema with the following key models:
- `User` - User accounts with personal information
- `Device` - Device verification for security
- `Transaction` - Personal financial transactions

## Transaction Types

- **DEPOSIT**: Adding money to savings account
- **WITHDRAWAL**: Removing money from savings account

## Security Features

- Password hashing with bcryptjs
- JWT token authentication
- Device verification for account security
- Rate limiting to prevent abuse
- Helmet for security headers

## Testing

```bash
# Run unit tests
npm run test

# Run e2e tests
npm run test:e2e

# Run tests with coverage
npm run test:cov
```

## Code Quality

```bash
# Lint code
npm run lint

# Format code
npm run format
```

## API Documentation

Once the server is running, visit `http://localhost:3000/api` for Swagger documentation.

## Environment Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `DATABASE_URL` | PostgreSQL connection string | Required |
| `JWT_SECRET` | JWT signing secret | Required |
| `PORT` | Server port | 3000 |

## Development Notes

- Uses TypeScript for type safety
- Implements class-validator for request validation
- Uses bcryptjs for password hashing
- Implements rate limiting and helmet for security
- Follows NestJS best practices and patterns
- Shares database schema with admin backend for consistency

## Error Handling

The API provides comprehensive error handling with appropriate HTTP status codes:
- 400: Bad Request (validation errors)
- 401: Unauthorized (authentication required)
- 403: Forbidden (insufficient permissions)
- 404: Not Found (resource doesn't exist)
- 429: Too Many Requests (rate limited)
- 500: Internal Server Error (server errors)

## Data Validation

All API endpoints use class-validator decorators for input validation:
- Email format validation
- Password strength requirements
- Numeric value validation for amounts
- Required field validation
