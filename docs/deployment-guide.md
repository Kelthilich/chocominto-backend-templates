# Deployment Guide

🚀 **Production deployment strategies** for Chocominto NestJS templates.

## 🎯 Overview

This guide covers deployment strategies for all template types, from simple VPS deployments to container orchestration platforms.

## 📋 Prerequisites

Before deploying any template, ensure you have:
- **Production environment** ready (VPS, cloud provider, etc.)
- **Domain name** configured (optional but recommended)
- **SSL certificate** for HTTPS (Let's Encrypt or commercial)
- **Environment variables** properly configured
- **Database** and Redis instances ready

## 🐳 Docker Template Deployments

### Simple Docker Deployment

For single-server deployments using Docker Compose:

```bash
# Clone your project
git clone <your-project-repo>
cd your-project

# Set up environment
cp .env.template .env.production
# Edit .env.production with production values

# Build and start services
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d

# Check status
docker-compose ps
```

### Container Orchestration

#### Kubernetes Deployment
```yaml
# To be implemented in future steps
# - Kubernetes manifests
# - Helm charts
# - Service mesh configuration
```

#### Docker Swarm
```bash
# To be implemented in future steps
# - Swarm initialization
# - Service deployment
# - Load balancing
```

## 🏠 Local Template Deployments

### VPS Deployment

For templates using local databases:

```bash
# Server setup
sudo apt update
sudo apt upgrade -y

# Install Node.js 22 LTS
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt install -y nodejs

# Install databases (PostgreSQL example)
sudo apt install postgresql postgresql-contrib redis-server

# Deploy application
git clone <your-project-repo>
cd your-project
npm ci --only=production
npm run build

# Set up process manager
sudo npm install -g pm2
pm2 start dist/main.js --name "your-app"
pm2 startup
pm2 save
```

## 🔧 Environment Configuration

### Production Environment Variables

Create a secure `.env.production` file:

```env
# Application
NODE_ENV=production
PORT=3000

# Database (use secure credentials)
DATABASE_URL="postgresql://secure_user:secure_password@db_host:5432/prod_db"

# Redis (use secure configuration)
REDIS_HOST=redis_host
REDIS_PORT=6379
REDIS_PASSWORD=secure_redis_password

# Security
JWT_SECRET=very-secure-jwt-secret-key
CORS_ORIGIN=https://yourdomain.com

# Logging
LOG_LEVEL=warn
```

## 🛡️ Security Best Practices

### Container Security
- Use non-root users in containers
- Scan images for vulnerabilities
- Use minimal base images (Alpine Linux)
- Keep containers updated

### Database Security
- Use strong passwords
- Enable SSL/TLS connections
- Configure proper firewall rules
- Regular backups

### Application Security
- Enable HTTPS only
- Configure CORS properly
- Use environment variables for secrets
- Implement rate limiting

## 📊 Monitoring and Logging

### Health Checks
```typescript
// To be implemented in future steps
// - Database connectivity checks
// - Redis connectivity checks
// - Application health endpoints
```

### Logging
```typescript
// To be implemented in future steps
// - Winston logger configuration
// - Log aggregation setup
// - Error tracking integration
```

## 🚀 CI/CD Pipeline

### GitHub Actions Example
```yaml
# To be implemented in future steps
# - Build and test pipeline
# - Docker image building
# - Deployment automation
```

### GitLab CI Example
```yaml
# To be implemented in future steps
# - Pipeline configuration
# - Environment-specific deployments
# - Rollback strategies
```

## 🔄 Backup and Recovery

### Database Backups
```bash
# PostgreSQL backup
pg_dump -h localhost -U username -d database_name > backup.sql

# MongoDB backup
mongodump --host localhost:27017 --db database_name --out /backup/location
```

### Redis Backups
```bash
# Redis backup
redis-cli SAVE
cp /var/lib/redis/dump.rdb /backup/location/
```

## 📈 Performance Optimization

### Database Optimization
- Configure connection pooling
- Set up read replicas
- Optimize queries and indexes
- Monitor slow queries

### Application Optimization
- Enable gzip compression
- Configure caching strategies
- Optimize bundle sizes
- Use CDN for static assets

## 🔗 Cloud Provider Specific Guides

### AWS Deployment
```bash
# To be implemented in future steps
# - ECS/EKS deployment
# - RDS setup
# - ElastiCache configuration
```

### Google Cloud Deployment
```bash
# To be implemented in future steps
# - Cloud Run deployment
# - Cloud SQL setup
# - Memorystore configuration
```

### Azure Deployment
```bash
# To be implemented in future steps
# - Container Instances
# - Azure Database
# - Azure Cache for Redis
```

## 🆘 Troubleshooting

### Common Issues
- Database connection failures
- Redis connectivity problems
- Port conflicts
- SSL certificate issues

### Debugging Commands
```bash
# Check application logs
docker-compose logs app

# Check database connectivity
docker-compose exec postgres psql -U username -d database_name

# Check Redis connectivity
docker-compose exec redis redis-cli ping
```

---

📝 **Note**: This guide will be expanded with specific deployment examples and configurations in future implementation steps.
