# Client Frontend

Next.js React application for the Credit Jambo Elite client portal, providing a user-friendly interface for managing personal savings accounts and financial transactions.

## Features

- User registration and login
- Personal dashboard with account overview
- Savings account management
- Transaction history and tracking
- Device verification for security
- Responsive mobile-first design
- Real-time balance updates

## Prerequisites

- Node.js (v18 or higher)
- Client backend API running (localhost:3000)

## Installation

1. **Navigate to the client frontend directory**
   ```bash
   cd Client/frontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Setup environment variables**
   ```bash
   cp .env.example .env.local
   ```
   Edit `.env.local`:
   ```
   NEXT_PUBLIC_API_URL=http://localhost:3000
   ```

## Running the Application

### Development
```bash
npm run dev
```
The application will be available at `http://localhost:4000`

### Production
```bash
npm run build
npm run start
```

## Project Structure

```
Client/frontend/
├── app/                    # Next.js app router pages
│   ├── dashboard/         # User dashboard
│   ├── login/            # User login page
│   ├── register/         # User registration page
│   ├── savings/          # Savings management pages
│   └── transactions/     # Transaction history pages
├── components/           # Reusable React components
│   ├── ui/              # UI components (buttons, forms, etc.)
│   ├── layout/          # Layout components
│   └── forms/           # Form components
├── lib/                 # Utility functions and API clients
├── hooks/               # Custom React hooks
├── public/              # Static assets
└── styles/              # Global styles and CSS
```

## Key Features

### Authentication
- User registration with email verification
- Secure login with JWT authentication
- Password reset functionality
- Device verification for account security

### Dashboard
- Account balance overview
- Recent transactions summary
- Quick action buttons (deposit/withdraw)
- Account statistics and insights

### Savings Management
- View current balance
- Make deposits to savings account
- Withdraw funds from account
- Transaction limits and validation

### Transaction History
- Complete transaction history
- Filter by date and type
- Search functionality
- Export transaction data

### Security Features
- Device verification on login
- Session management
- Secure API communication
- Input validation and sanitization

## API Integration

The frontend communicates with the Client Backend API:

- **Base URL**: `http://localhost:3000`
- **Authentication**: JWT tokens stored in localStorage
- **Data Fetching**: SWR for efficient data fetching and caching
- **Real-time Updates**: Optimistic updates for better UX

## Styling and UI

- **Tailwind CSS**: Utility-first CSS framework
- **Responsive Design**: Mobile-first approach
- **Component Library**: Reusable UI components
- **Dark/Light Theme**: Theme switching capability
- **Accessibility**: WCAG compliant components

## Development Guidelines

### Code Organization
- **TypeScript**: Full type safety throughout the application
- **Component Structure**: Atomic design principles
- **State Management**: React hooks with SWR for server state
- **Routing**: Next.js App Router with protected routes

### Performance
- **Code Splitting**: Automatic route-based splitting
- **Image Optimization**: Next.js Image component
- **Caching**: SWR for intelligent caching
- **Bundle Analysis**: Webpack bundle analyzer

### Security
- **Input Validation**: Client and server-side validation
- **XSS Protection**: Sanitized user inputs
- **CSRF Protection**: Secure API endpoints
- **Secure Storage**: Encrypted local storage for sensitive data

## Environment Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `NEXT_PUBLIC_API_URL` | Client backend API URL | http://localhost:3000 |

## Building for Production

```bash
npm run build
npm run start
```

The production build includes:
- Code minification and optimization
- Image optimization
- CSS extraction and minification
- Service worker for caching (if configured)

## Testing

```bash
npm run test
npm run test:watch
```

## Deployment

### Vercel (Recommended)
1. Connect your GitHub repository to Vercel
2. Set environment variables in Vercel dashboard
3. Deploy automatically on push

### Other Platforms
The application can be deployed to:
- Netlify
- AWS Amplify
- DigitalOcean App Platform
- Any Node.js hosting service

## Browser Support

- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

## Progressive Web App (PWA)

The application is configured as a PWA with:
- Service worker for offline functionality
- Web app manifest
- Install prompt
- Offline page

## Contributing

### Development Workflow
1. Create feature branch from `main`
2. Follow conventional commit messages
3. Write tests for new features
4. Ensure all tests pass
5. Create pull request with description

### Code Style
- ESLint configuration for code quality
- Prettier for consistent formatting
- Husky for pre-commit hooks
- Commitlint for commit message standards

### Testing Strategy
- Unit tests for components and utilities
- Integration tests for API calls
- E2E tests for critical user flows
- Visual regression tests (optional)

## Troubleshooting

### Common Issues

**API Connection Issues**
- Verify backend is running on correct port
- Check environment variables
- Ensure CORS is properly configured

**Authentication Problems**
- Clear localStorage and cookies
- Verify JWT token validity
- Check device verification status

**Build Errors**
- Clear `.next` folder and rebuild
- Check Node.js version compatibility
- Verify all dependencies are installed

### Performance Optimization

- Use React DevTools Profiler to identify bottlenecks
- Implement lazy loading for heavy components
- Optimize images and assets
- Monitor bundle size with `npm run analyze`

## Support

For support and questions:
- Check the troubleshooting section above
- Review the API documentation
- Check GitHub issues for similar problems
- Create a new issue with detailed information
