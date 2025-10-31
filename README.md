# Credit Jambo Elite - Client Portal

User-facing application for the Credit Jambo Elite savings platform. Provides individuals with secure access to manage their personal savings accounts and financial transactions.

## What It Does

The Client Portal enables users to:
- **Manage Savings**: View balance, make deposits and withdrawals
- **Track Transactions**: Complete history with search and filtering
- **Secure Access**: Device verification and multi-factor authentication
- **Account Control**: Profile management and security settings
- **24/7 Availability**: Round-the-clock access to savings accounts

## Architecture

**Backend** (`./backend/`) - NestJS API on port 3000  
**Frontend** (`./frontend/`) - Next.js application on port 4000

## Quick Start

1. Start database: `docker-compose up -d` (from project root)
2. Setup backend:
   ```bash
   cd Client/backend
   cp .env.example .env
   npm install
   npx prisma migrate dev
   npm run start:dev
   ```
3. Setup frontend:
   ```bash
   cd Client/frontend
   cp .env.example .env.local
   npm install
   npm run dev
   ```
4. Access: http://localhost:4000

## Key Features

- User registration and authentication
- Real-time balance viewing
- Secure deposit and withdrawal operations
- Comprehensive transaction history
- Device verification for security
- Mobile-responsive design
- Progressive Web App (PWA) capabilities

For detailed setup instructions, see:
- [Backend README](./backend/README.md)
- [Frontend README](./frontend/README.md)