<p align="center">
  <img src="https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white" />
  <img src="https://img.shields.io/badge/Express.js-404D59?style=for-the-badge&logo=express&logoColor=white" />
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" />
  <img src="https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white" />
  <img src="https://img.shields.io/badge/Drizzle-C5F74F?style=for-the-badge&logo=drizzle&logoColor=black" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/JWT-black?style=for-the-badge&logo=JSON%20web%20tokens" />
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" />
  <img src="https://img.shields.io/badge/ESLint-4B3263?style=for-the-badge&logo=eslint&logoColor=white" />
  <img src="https://img.shields.io/badge/Prettier-F7B93E?style=for-the-badge&logo=prettier&logoColor=black" />
  <img src="https://img.shields.io/badge/Jest-323330?style=for-the-badge&logo=Jest&logoColor=white" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Winston-231F20?style=for-the-badge&logo=winston&logoColor=white" />
  <img src="https://img.shields.io/badge/Zod-3E67B1?style=for-the-badge&logo=zod&logoColor=white" />
  <img src="https://img.shields.io/badge/bcrypt-5A29E4?style=for-the-badge&logo=npm&logoColor=white" />
  <img src="https://img.shields.io/badge/Helmet.js-000000?style=for-the-badge&logo=helmetjs&logoColor=white" />
  <img src="https://img.shields.io/badge/CORS-FF6B6B?style=for-the-badge&logo=cors&logoColor=white" />
</p>

# Acquisitions API

A secure, production-ready Node.js REST API for user authentication and management, built with modern technologies and enterprise-grade security features.

## 🚀 Features

- **Secure Authentication**: JWT-based authentication with HTTP-only cookies
- **Role-Based Access Control**: Admin and user roles with proper authorization
- **Advanced Security**: Arcjet-powered bot detection, rate limiting, and threat protection
- **Modern Architecture**: Clean layered architecture with separation of concerns
- **Type-Safe Database**: Drizzle ORM with PostgreSQL and schema migrations
- **Input Validation**: Comprehensive request validation using Zod
- **Structured Logging**: Winston logger with multiple transports
- **Code Quality**: ESLint, Prettier, and automated testing
- **Production Ready**: Docker support, health checks, and monitoring

## 🛠️ Tech Stack

### **Core Framework**
- **Node.js 20+** - JavaScript runtime with ES modules
- **Express.js 5.1.0** - Fast, unopinionated web framework
- **ES Modules** - Modern JavaScript module system

### **Database & ORM**
- **Neon Database** - Serverless PostgreSQL database
- **Drizzle ORM 0.44.5** - Type-safe database toolkit
- **Drizzle Kit** - Database migrations and schema management

### **Security & Authentication**
- **Arcjet 1.0.0** - Advanced security platform
  - Bot detection and prevention
  - Rate limiting (role-based limits)
  - Shield protection against attacks
- **bcrypt 6.0.0** - Password hashing
- **jsonwebtoken 9.0.2** - JWT token management
- **Helmet 8.1.0** - Security headers middleware
- **CORS 2.8.5** - Cross-origin resource sharing

### **Validation & Utilities**
- **Zod 4.1.9** - Runtime type validation and parsing
- **Winston 3.17.0** - Logging framework
- **Morgan 1.10.1** - HTTP request logging
- **cookie-parser 1.4.7** - Cookie parsing middleware
- **dotenv 17.2.2** - Environment variable management

### **Development Tools**
- **ESLint 9.35.0** - Code linting and style checking
- **Prettier 3.6.2** - Code formatting
- **Jest 30.1.3** - Testing framework
- **Supertest 7.1.0** - HTTP integration testing
- **Node --watch** - Development hot reload

## 📁 Project Structure

```
acquisitions/
├── src/
│   ├── config/           # Configuration modules
│   │   ├── database.js   # Database connection setup
│   │   ├── logger.js     # Winston logging configuration
│   │   └── arcjet.js     # Security middleware configuration
│   ├── controllers/      # Request handlers
│   │   ├── auth.controller.js    # Authentication endpoints
│   │   └── users.controller.js   # User management endpoints
│   ├── middleware/       # Express middleware
│   │   ├── auth.middleware.js    # JWT authentication
│   │   └── security.middleware.js # Arcjet security
│   ├── models/          # Database schemas
│   │   └── user.model.js # User table schema
│   ├── routes/          # API route definitions
│   │   ├── auth.routes.js    # Authentication routes
│   │   └── users.routes.js   # User management routes
│   ├── services/        # Business logic layer
│   │   ├── auth.service.js   # Authentication services
│   │   └── users.service.js  # User management services
│   ├── utils/           # Helper utilities
│   │   ├── jwt.js       # JWT token utilities
│   │   ├── cookies.js   # Cookie management
│   │   └── format.js    # Error formatting
│   ├── validations/     # Input validation schemas
│   │   ├── auth.validation.js    # Auth input validation
│   │   └── users.validation.js   # User input validation
│   ├── app.js           # Express application setup
│   ├── server.js        # Server startup
│   └── index.js         # Application entry point
├── drizzle/             # Database migrations
├── tests/               # Test files
├── logs/                # Application logs
└── package.json         # Dependencies and scripts
```

## 🔧 Installation & Setup

### Prerequisites
- **Node.js 20+**
- **npm** or **yarn**
- **PostgreSQL** (or Neon Database account)

### 1. Clone the Repository
```bash
git clone https://github.com/nemanjaASE/acquisitions.git
cd acquisitions
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Environment Configuration
Create a `.env` file in the root directory:

```env
# Server Configuration
PORT=3000
NODE_ENV=development
LOG_LEVEL=info

# Database Configuration
DATABASE_URL=your_neon_database_url_here

# JWT Configuration
JWT_SECRET=your_super_secret_jwt_key_change_in_production

# Arcjet Configuration
ARCJET_KEY=your_arcjet_api_key_here
```

### 4. Database Setup
```bash
# Generate migration files
npm run db:generate

# Run migrations
npm run db:migrate

# Optional: Open Drizzle Studio for database management
npm run db:studio
```

### 5. Start Development Server
```bash
npm run dev
```

The API will be available at `http://localhost:3000`

## 📚 API Endpoints

### Health & Status
- `GET /` - Welcome message
- `GET /health` - Health check endpoint
- `GET /api` - API status

### Authentication
- `POST /api/auth/sign-up` - User registration
- `POST /api/auth/sign-in` - User login
- `POST /api/auth/sign-out` - User logout

### User Management
- `GET /api/users` - Get all users (admin only)
- `GET /api/users/:id` - Get user by ID (authenticated users)
- `PUT /api/users/:id` - Update user (own profile or admin)
- `DELETE /api/users/:id` - Delete user (admin only)

## 🔐 Security Features

### Rate Limiting
- **Guest users**: 5 requests per minute
- **Authenticated users**: 10 requests per minute  
- **Admin users**: 20 requests per minute

### Security Middleware
- **Helmet**: Sets security headers
- **CORS**: Configures cross-origin requests
- **Arcjet Shield**: Protects against common attacks
- **Bot Detection**: Automatically blocks malicious bots
- **Input Validation**: All requests validated with Zod schemas

### Authentication
- **JWT Tokens**: Secure token-based authentication
- **HTTP-Only Cookies**: Prevents XSS attacks
- **Password Hashing**: bcrypt with salt rounds
- **Role-Based Access**: Admin and user role authorization

## 🧪 Testing

```bash
# Run all tests
npm test

# Run with coverage
npm run test:coverage

# Lint code
npm run lint

# Format code
npm run format
```

## 📋 Available Scripts

```bash
npm run dev          # Start development server with hot reload
npm start            # Start production server
npm run lint         # Run ESLint
npm run lint:fix     # Fix ESLint errors automatically
npm run format       # Format code with Prettier
npm run format:check # Check code formatting
npm run db:generate  # Generate database migrations
npm run db:migrate   # Run database migrations
npm run db:studio    # Open Drizzle Studio
npm test             # Run tests
```

## 🌟 Key Features Explained

### **Layered Architecture**
The application follows a clean layered architecture pattern:
- **Routes**: API endpoint definitions
- **Controllers**: Request/response handling
- **Services**: Business logic implementation
- **Models**: Database schema definitions
- **Utils**: Reusable helper functions

### **Security-First Design**
- Arcjet integration provides enterprise-grade security
- Role-based rate limiting prevents abuse
- JWT authentication with secure cookie storage
- Comprehensive input validation prevents injection attacks

### **Type Safety**
- Zod schemas ensure runtime type validation
- Drizzle ORM provides compile-time type safety
- Modern ES modules with import/export syntax

### **Monitoring & Observability**
- Structured logging with Winston
- Request logging with Morgan
- Health check endpoints for monitoring
- Error handling with proper HTTP status codes

## 🚀 Deployment

### Environment Variables for Production
```env
NODE_ENV=production
PORT=3000
DATABASE_URL=your_production_database_url
JWT_SECRET=your_production_jwt_secret
ARCJET_KEY=your_production_arcjet_key
LOG_LEVEL=warn
```

### Docker Support
The application is Docker-ready. Build and run:

```bash
# Build image
docker build -t acquisitions-api .

# Run container
docker run -p 3000:3000 --env-file .env acquisitions-api
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the ISC License.

## 📞 Support

For issues and questions, please open an issue on the [GitHub repository](https://github.com/nemanjaASE/acquisitions/issues).

---

**Built with ❤️ using modern Node.js technologies**
