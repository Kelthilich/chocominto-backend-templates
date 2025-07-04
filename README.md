# Chocominto NestJS Backend Templates

🚀 **Ready-to-use NestJS backend templates** with modern technology stacks for rapid development and deployment.

## 🎯 Overview

This repository provides battle-tested NestJS templates with different database and deployment configurations. Each template uses the latest NestJS CLI to ensure up-to-date dependencies and best practices.

## 📦 Available Templates

| Template | Database | ORM/ODM | Deployment | Use Case |
|----------|----------|---------|------------|----------|
| `nestjs-postgresql-prisma-docker` | PostgreSQL 16 | Prisma | Docker | Production-ready with containers |
| `nestjs-postgresql-prisma-local` | PostgreSQL 16 | Prisma | Local | Development without Docker |
| `nestjs-mongodb-mongoose-docker` | MongoDB | Mongoose | Docker | Document-based apps with containers |
| `nestjs-mongodb-mongoose-local` | MongoDB | Mongoose | Local | Document-based apps, local development |

## 🏗️ Template Features

### Common Features (All Templates)
- ✅ **Latest NestJS** - Generated with `@nestjs/cli`
- ✅ **Redis 7.2** - Caching and session management
- ✅ **TypeScript** - Full type safety
- ✅ **Environment Configuration** - Proper `.env` handling
- ✅ **Modern Architecture** - Clean, scalable project structure

### PostgreSQL + Prisma Templates
- ✅ **Type-safe Database Access** - Prisma Client with full TypeScript support
- ✅ **Database Migrations** - Version-controlled schema changes
- ✅ **Advanced Querying** - Relations, transactions, and complex queries
- ✅ **Database Introspection** - Auto-generated types from schema

### MongoDB + Mongoose Templates
- ✅ **Flexible Document Structure** - Schema-less or schema-based approach
- ✅ **Rich Query API** - Powerful querying and aggregation
- ✅ **Middleware Support** - Pre/post hooks and validation
- ✅ **Document Relationships** - Population and references

## 🚀 Quick Start

### Prerequisites
- **Node.js 22 LTS** or higher
- **Git** installed
- **Docker** (for Docker templates)
- **Local Database** (for local templates)

### Using a Template

1. **Clone this repository**
   ```bash
   git clone https://github.com/yourusername/chocominto-backend-templates.git
   cd chocominto-backend-templates
   ```

2. **Choose your template**
   - Browse the `templates/` directory
   - Read the specific template's README for setup instructions

3. **Follow template-specific instructions**
   - Each template has its own README with detailed setup steps
   - Docker templates include `docker-compose.yml` for easy deployment
   - Local templates provide local development setup

## 📚 Documentation

- [Deployment Guide](./docs/deployment-guide.md) - Production deployment strategies
- [Common Patterns](./docs/common-patterns.md) - Best practices and examples

## 🛠️ Development Requirements

### For Docker Templates
- Docker Desktop or Docker Engine
- Docker Compose

### For Local Templates
- **PostgreSQL templates**: PostgreSQL 16+ and Redis 7.2+
- **MongoDB templates**: MongoDB 6.0+ and Redis 7.2+

## 🎨 Template Structure

Each template contains:
- **README.md** - Template-specific setup instructions
- **docker-compose.yml** - Docker configuration (Docker templates only)
- **Dockerfile** - Container setup (Docker templates only)
- **.env.template** - Environment variables template

## 🔧 Customization

These templates are designed to be starting points. After generating your project:

1. **Update project details** in `package.json`
2. **Configure environment variables** in `.env`
3. **Modify database schemas** as needed
4. **Add your business logic** in the generated NestJS structure

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](./CONTRIBUTING.md) for details.

## 📄 Licensing

### Template Repository License
This template repository is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

### Generated Project Licensing
**Important**: Projects generated from these templates are yours to license as you see fit. The templates themselves do not include LICENSE files, giving you complete freedom to choose your own licensing strategy.

Consider adding a LICENSE file to your generated project based on your needs:
- [Choose a License](https://choosealicense.com/) - Interactive license selector
- [GitHub License Guide](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/licensing-a-repository) - Detailed licensing guide

### Common License Options
- **MIT** - Simple and permissive
- **Apache 2.0** - Permissive with patent protection
- **GPL v3** - Copyleft license
- **Proprietary** - For commercial/private projects

The choice is entirely yours! 🎯

## 🔗 Links

- [NestJS Documentation](https://docs.nestjs.com/)
- [Prisma Documentation](https://www.prisma.io/docs)
- [Mongoose Documentation](https://mongoosejs.com/)
- [Docker Documentation](https://docs.docker.com/)

---

⭐ **Found this useful?** Give it a star and help others discover these templates!