# NestJS + PostgreSQL + Prisma + Local Template

🏠 **Local development setup** for NestJS backend with PostgreSQL, Prisma, and Redis running locally.

## 🎯 What's Included

- **NestJS** - Modern Node.js framework
- **PostgreSQL 16** - Robust relational database (local installation)
- **Prisma** - Type-safe database toolkit
- **Redis 7.2** - In-memory caching and sessions (local installation)
- **Local Development** - Fast development without Docker overhead

## 🚀 Quick Start

### Prerequisites
- Node.js 22 LTS
- PostgreSQL 16+ installed locally
- Redis 7.2+ installed locally

### Local Database Setup

#### PostgreSQL Setup
```bash
# Ubuntu/Debian
sudo apt update
sudo apt install postgresql postgresql-contrib

# macOS (using Homebrew)
brew install postgresql@16
brew services start postgresql@16

# Windows (using Chocolatey)
choco install postgresql
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
   npm install prisma @prisma/client redis @types/redis
   npm install -D prisma
   ```

4. **Configure environment**
   ```bash
   cp .env.template .env
   # Edit .env with your local database configuration
   ```

5. **Setup local database**
   ```bash
   # Create database
   createdb your_database_name

   # Or using PostgreSQL CLI
   psql -U postgres -c "CREATE DATABASE your_database_name;"
   ```

6. **Start your application**
   ```bash
   npm run start:dev
   ```

## 📝 Environment Variables

Copy `.env.template` to `.env` and configure for local development:

```env
# Database (Local PostgreSQL)
DATABASE_URL="postgresql://postgres:your_password@localhost:5432/your_database_name"

# Redis (Local Redis)
REDIS_HOST=localhost
REDIS_PORT=6379

# Application
PORT=3000
NODE_ENV=development
```

## 🔧 Database Setup

### Prisma Setup (To be implemented in future steps)
```bash
# Initialize Prisma
npx prisma init

# Generate Prisma client
npx prisma generate

# Run migrations
npx prisma migrate dev --name init

# View database in Prisma Studio
npx prisma studio
```

## 🚀 Development Workflow

### Starting Development
```bash
# Start PostgreSQL (if not auto-started)
sudo systemctl start postgresql  # Linux
brew services start postgresql@16  # macOS

# Start Redis (if not auto-started)
sudo systemctl start redis  # Linux
brew services start redis  # macOS

# Start your NestJS app
npm run start:dev
```

### Database Management
```bash
# View data in Prisma Studio
npx prisma studio

# Reset database
npx prisma migrate reset

# Apply new migrations
npx prisma migrate dev
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

1. **Configure Prisma schema** - Define your data models
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
- [Prisma Documentation](https://www.prisma.io/docs)
- [PostgreSQL Documentation](https://www.postgresql.org/docs/)
- [Redis Documentation](https://redis.io/docs/)

## 🆘 Troubleshooting

### Database Connection Issues
- Check if PostgreSQL is running: `pg_isready`
- Verify connection string in `.env`
- Check PostgreSQL logs: `sudo journalctl -u postgresql`

### Redis Connection Issues
- Check if Redis is running: `redis-cli ping`
- Verify Redis configuration
- Check Redis logs: `sudo journalctl -u redis`

### Permission Issues
- Ensure your user has access to PostgreSQL
- Check database permissions: `\du` in psql
- Verify Redis permissions

---

📝 **Note**: This template provides the foundation. Database schemas, authentication, and business logic will be added in future implementation steps.
