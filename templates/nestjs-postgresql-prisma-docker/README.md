# NestJS + PostgreSQL + Prisma + Docker Template

🐳 **Production-ready NestJS backend** with PostgreSQL, Prisma, and Redis running in Docker containers.

## 🎯 What's Included

- **NestJS** - Modern Node.js framework
- **PostgreSQL 16** - Robust relational database
- **Prisma** - Type-safe database toolkit
- **Redis 7.2** - In-memory caching and sessions
- **Docker & Docker Compose** - Containerized development and deployment

## 🚀 Quick Start

### Prerequisites
- Node.js 22 LTS
- Docker Desktop or Docker Engine
- Docker Compose

### Setup Instructions

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
   # Edit .env with your specific configuration
   ```

5. **Start the development environment**
   ```bash
   docker-compose up -d
   npm run start:dev
   ```

## 🐳 Docker Services

The `docker-compose.yml` includes:

- **PostgreSQL 16** - Main database (Port: 5432)
- **Redis 7.2** - Cache and sessions (Port: 6379)
- **Adminer** - Database management UI (Port: 8080)

## 📝 Environment Variables

Copy `.env.template` to `.env` and configure:

```env
# Database
DATABASE_URL="postgresql://username:password@localhost:5432/dbname"

# Redis
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
```

## 🚀 Deployment

### Development
```bash
docker-compose up -d
npm run start:dev
```

### Production
```bash
docker-compose -f docker-compose.prod.yml up -d
npm run build
npm run start:prod
```

## 🛠️ Available Scripts

| Script | Description |
|--------|-------------|
| `npm run start:dev` | Start development server |
| `npm run build` | Build for production |
| `npm run start:prod` | Start production server |
| `npm run test` | Run tests |
| `npm run test:e2e` | Run end-to-end tests |

## 📚 Next Steps

1. **Configure Prisma schema** - Define your data models
2. **Set up authentication** - JWT, Passport, or Auth0
3. **Add API documentation** - Swagger/OpenAPI
4. **Configure logging** - Winston or similar
5. **Add monitoring** - Health checks and metrics

## 🔗 Useful Resources

- [NestJS Documentation](https://docs.nestjs.com/)
- [Prisma Documentation](https://www.prisma.io/docs)
- [Docker Compose Documentation](https://docs.docker.com/compose/)
- [PostgreSQL Documentation](https://www.postgresql.org/docs/)

## 🆘 Troubleshooting

### Database Connection Issues
- Check if PostgreSQL container is running: `docker ps`
- Verify environment variables in `.env`
- Ensure ports are not conflicting

### Redis Connection Issues
- Check Redis container status: `docker-compose logs redis`
- Verify Redis configuration in your NestJS app

### Docker Issues
- Clean up containers: `docker-compose down -v`
- Rebuild images: `docker-compose up --build`

---

📝 **Note**: This template provides the foundation. Database schemas, authentication, and business logic will be added in future implementation steps.
