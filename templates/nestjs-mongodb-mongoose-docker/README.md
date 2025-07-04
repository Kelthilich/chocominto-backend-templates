# NestJS + MongoDB + Mongoose + Docker Template

🐳 **Production-ready NestJS backend** with MongoDB, Mongoose, and Redis running in Docker containers.

## 🎯 What's Included

- **NestJS** - Modern Node.js framework
- **MongoDB 6.0** - NoSQL document database
- **Mongoose** - Elegant MongoDB object modeling
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
   npm install mongoose @nestjs/mongoose redis @types/redis
   npm install -D @types/mongoose
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

- **MongoDB 6.0** - Main database (Port: 27017)
- **Redis 7.2** - Cache and sessions (Port: 6379)
- **Mongo Express** - Database management UI (Port: 8081)

## 📝 Environment Variables

Copy `.env.template` to `.env` and configure:

```env
# Database
MONGODB_URI="mongodb://username:password@localhost:27017/dbname"

# Redis
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

1. **Configure Mongoose schemas** - Define your data models
2. **Set up authentication** - JWT, Passport, or Auth0
3. **Add API documentation** - Swagger/OpenAPI
4. **Configure logging** - Winston or similar
5. **Add monitoring** - Health checks and metrics

## 💡 MongoDB Advantages

- **Flexible Schema** - Easy to adapt to changing requirements
- **Horizontal Scaling** - Built-in sharding support
- **Rich Query Language** - Powerful aggregation framework
- **JSON-like Documents** - Natural fit for JavaScript/TypeScript

## 🔗 Useful Resources

- [NestJS Documentation](https://docs.nestjs.com/)
- [Mongoose Documentation](https://mongoosejs.com/)
- [MongoDB Documentation](https://www.mongodb.com/docs/)
- [Docker Compose Documentation](https://docs.docker.com/compose/)

## 🆘 Troubleshooting

### Database Connection Issues
- Check if MongoDB container is running: `docker ps`
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
