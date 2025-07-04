# NestJS + MongoDB + Mongoose + Local Template

🏠 **Local development setup** for NestJS backend with MongoDB, Mongoose, and Redis running locally.

## 🎯 What's Included

- **NestJS** - Modern Node.js framework
- **MongoDB 6.0** - NoSQL document database (local installation)
- **Mongoose** - Elegant MongoDB object modeling
- **Redis 7.2** - In-memory caching and sessions (local installation)
- **Local Development** - Fast development without Docker overhead

## 🚀 Quick Start

### Prerequisites
- Node.js 22 LTS
- MongoDB 6.0+ installed locally
- Redis 7.2+ installed locally

### Local Database Setup

#### MongoDB Setup
```bash
# Ubuntu/Debian
sudo apt update
sudo apt install mongodb

# macOS (using Homebrew)
brew tap mongodb/brew
brew install mongodb-community@6.0
brew services start mongodb-community@6.0

# Windows (using Chocolatey)
choco install mongodb
```

#### Redis Setup
```bash
# Ubuntu/Debian
sudo apt install redis-server

# macOS (using Homebrew)
brew install redis
brew services start redis

# Windows (using Chocolatey)
choco install redis-64
```

### Project Setup

1. **Create your NestJS project**
   ```bash
   npx @nestjs/cli new your-project-name
   cd your-project-name
   ```

2. **Copy template files**
   ```bash
   # Copy all files from this template directory to your project root
   cp /path/to/template/* ./
   ```

3. **Install additional dependencies**
   ```bash
   npm install mongoose @nestjs/mongoose redis @types/redis
   npm install -D @types/mongoose
   ```

4. **Configure environment**
   ```bash
   cp .env.template .env
   # Edit .env with your local database configuration
   ```

5. **Start your application**
   ```bash
   npm run start:dev
   ```

## 📝 Environment Variables

Copy `.env.template` to `.env` and configure for local development:

```env
# Database (Local MongoDB)
MONGODB_URI="mongodb://localhost:27017/your_database_name"

# Redis (Local Redis)
REDIS_HOST=localhost
REDIS_PORT=6379

# Application
PORT=3000
NODE_ENV=development
```

## 🔧 Database Setup

### Mongoose Setup (To be implemented in future steps)
```bash
# Mongoose models and schemas will be configured in future steps
# Connection setup and basic CRUD operations
```

## 🚀 Development Workflow

### Starting Development
```bash
# Start MongoDB (if not auto-started)
sudo systemctl start mongod  # Linux
brew services start mongodb-community@6.0  # macOS

# Start Redis (if not auto-started)
sudo systemctl start redis  # Linux
brew services start redis  # macOS

# Start your NestJS app
npm run start:dev
```

### Database Management
```bash
# Connect to MongoDB shell
mongosh

# Or using MongoDB Compass (GUI tool)
# Download from: https://www.mongodb.com/products/compass
```

## 🛠️ Available Scripts

| Script | Description |
|--------|-------------|
| `npm run start:dev` | Start development server with hot reload |
| `npm run build` | Build for production |
| `npm run start:prod` | Start production server |
| `npm run test` | Run unit tests |
| `npm run test:e2e` | Run end-to-end tests |

## 📚 Next Steps

1. **Configure Mongoose schemas** - Define your data models
2. **Set up authentication** - JWT, Passport, or Auth0
3. **Add API documentation** - Swagger/OpenAPI
4. **Configure logging** - Winston or similar
5. **Add monitoring** - Health checks and metrics

## 💡 Advantages of Local Development

- **Faster startup** - No Docker container overhead
- **Native debugging** - Direct access to database and Redis
- **Better IDE integration** - Native database connections
- **Easier troubleshooting** - Direct access to logs and processes

## 🔗 Useful Resources

- [NestJS Documentation](https://docs.nestjs.com/)
- [Mongoose Documentation](https://mongoosejs.com/)
- [MongoDB Documentation](https://www.mongodb.com/docs/)
- [Redis Documentation](https://redis.io/docs/)

## 🆘 Troubleshooting

### Database Connection Issues
- Check if MongoDB is running: `sudo systemctl status mongod`
- Verify connection string in `.env`
- Check MongoDB logs: `sudo journalctl -u mongod`

### Redis Connection Issues
- Check if Redis is running: `redis-cli ping`
- Verify Redis configuration
- Check Redis logs: `sudo journalctl -u redis`

### Permission Issues
- Ensure MongoDB has proper permissions: `sudo chown -R mongodb:mongodb /var/lib/mongodb`
- Check MongoDB configuration: `/etc/mongod.conf`

---

📝 **Note**: This template provides the foundation. Database schemas, authentication, and business logic will be added in future implementation steps.
