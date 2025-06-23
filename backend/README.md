## Features

- **Supabase Integration**: Uses existing Supabase database and authentication
- **Authentication**: Supabase Auth integration (no JWT handling needed)
- **Listing Management**: Full CRUD operations for listings
- **Booking System**: Complete booking functionality
- **User Profiles**: Profile management
- **File Upload Support**: Ready for Cloudinary integration
- **Security**: Rate limiting, CORS, security headers
- **Validation**: Input validation and sanitization

## Technology Stack

- **Runtime**: Node.js
- **Framework**: Express.js
- **Database**: Supabase (PostgreSQL)
- **Authentication**: Supabase Auth
- **Validation**: express-validator
- **Security**: Helmet, CORS, Rate Limiting

## Prerequisites

- Node.js (v16 or higher)
- Existing Supabase project
- Access to Supabase service role key

## Installation

1. Navigate to the backend directory:
```bash
cd backend
```

2. Install dependencies:
```bash
npm install
```

3. Set up environment variables:
```bash
cp .env.example .env
# Edit .env with your Supabase configuration
```

4. Start the server:
```bash
# Development
npm run dev

# Production
npm start
```

## Environment Configuration

### Required Environment Variables

```env
# Supabase Configuration
SUPABASE_URL=https://bwusbjpwqrfbvvdzsegv.supabase.co
SUPABASE_ANON_KEY=your_anon_key_here
SUPABASE_SERVICE_ROLE_KEY=your_service_role_key_here

# Server Configuration
PORT=5000
NODE_ENV=development
FRONTEND_URL=http://localhost:3000
```

**Important**: You'll need to get your service role key from your Supabase dashboard under Settings > API.

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user with Supabase
- `POST /api/auth/login` - Login user with Supabase
- `POST /api/auth/logout` - Logout user
- `GET /api/auth/profile` - Get user profile (requires auth)

### Listings
- `GET /api/listings` - Get all listings (with filters)
- `GET /api/listings/popular` - Get popular listings
- `GET /api/listings/:id` - Get listing by ID
- `POST /api/listings` - Create new listing (requires auth)

### Bookings
- `POST /api/bookings` - Create booking (requires auth)
- `GET /api/bookings` - Get user bookings (requires auth)
- `GET /api/bookings/:id` - Get booking by ID (requires auth)

### Users
- `PUT /api/users/profile` - Update user profile (requires auth)
- `PATCH /api/users/host-status` - Toggle host status (requires auth)

## Integration with Frontend

To use this backend with your React frontend:

1. Update your frontend API calls to point to `http://localhost:5000/api`
2. Keep using Supabase auth on the frontend
3. Pass Supabase tokens to backend API calls
4. All existing functionality will work seamlessly

## Development Workflow

1. Start Supabase (already running)
2. Start backend: `npm run dev`
3. Start frontend: `npm start` (in main project)
4. Both will work together seamlessly