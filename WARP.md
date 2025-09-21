# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Development Commands

### Starting Development

```bash
npm run dev
```

Uses Node.js watch mode to automatically restart the server on file changes.

### Code Quality

```bash
# Lint code
npm run lint

# Fix linting issues automatically
npm run lint:fix

# Format code with Prettier
npm run format

# Check code formatting
npm run format:check
```

### Database Operations

```bash
# Generate new migration files from schema changes
npm run db:generate

# Apply migrations to database
npm run db:migrate

# Open Drizzle Studio (database GUI)
npm run db:studio
```

## Architecture Overview

### Project Structure

This is a Node.js Express API using ES modules with a modular architecture organized by concerns:

- **Models** (`src/models/`): Drizzle ORM schema definitions
- **Controllers** (`src/controllers/`): Request handling and response logic
- **Services** (`src/services/`): Business logic and data operations
- **Routes** (`src/routes/`): API endpoint definitions
- **Validations** (`src/validations/`): Zod schema validation
- **Utils** (`src/utils/`): Shared utility functions
- **Config** (`src/config/`): Application configuration (database, logging)

### Key Technologies

- **Runtime**: Node.js with ES modules
- **Framework**: Express.js 5.x
- **Database**: PostgreSQL via Neon serverless
- **ORM**: Drizzle ORM with drizzle-kit for migrations
- **Validation**: Zod schemas
- **Authentication**: JWT tokens with httpOnly cookies
- **Logging**: Winston with file and console transports
- **Security**: Helmet, CORS, bcrypt password hashing

### Import Path Mapping

The project uses Node.js import maps for clean imports:

- `#config/*` → `./src/config/*`
- `#controllers/*` → `./src/controllers/*`
- `#middleware/*` → `./src/middleware/*`
- `#models/*` → `./src/models/*`
- `#routes/*` → `./src/routes/*`
- `#services/*` → `./src/services/*`
- `#utils/*` → `./src/utils/*`
- `#validations/*` → `./src/validations/*`

### Database Architecture

- Uses Drizzle ORM with PostgreSQL
- Database connection via Neon serverless (@neondatabase/serverless)
- Schema files in `src/models/` define table structures
- Migrations generated in `drizzle/` directory
- Configuration in `drizzle.config.js`

### Authentication Flow

- User registration with validation, password hashing, and JWT generation
- JWT stored in httpOnly cookies for security
- Role-based access control (user/admin roles)
- Validation using Zod schemas before processing

### Logging Strategy

- Winston logger configured for different environments
- File logging to `logs/error.log` and `logs/combined.log`
- Console logging in development
- Request logging via Morgan middleware

## Environment Configuration

Required environment variables:

- `DATABASE_URL`: PostgreSQL connection string for Neon
- `JWT_SECRET`: Secret key for JWT token signing
- `NODE_ENV`: Environment (development/production)
- `PORT`: Server port (defaults to 3000)
- `LOG_LEVEL`: Logging level (defaults to 'info')

## Development Guidelines

### Code Style

- ES modules syntax (import/export)
- ESLint configuration with 2-space indentation, single quotes, semicolons required
- Prettier for consistent formatting
- Prefer arrow functions and const declarations

### Error Handling

- Controllers use try-catch blocks with next() for error propagation
- Service layer throws errors that controllers handle
- Winston logging for error tracking
- Structured error responses with validation details

### Database Operations

- Use Drizzle ORM query builder
- Model definitions use pgTable with proper constraints
- Always use parameterized queries (built into Drizzle)
- Check for existing records before creating duplicates

### Security Practices

- Passwords hashed with bcrypt (saltRounds: 10)
- JWT tokens with 1-day expiration
- httpOnly cookies with secure settings in production
- Input validation with Zod schemas
- Helmet middleware for security headers
