# AI Content Generation & Distribution Platform

> Transform a single creative brief into multi-format, persona-targeted content across channels with AI-powered generation, intelligent personalization, and automated optimization.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Node.js](https://img.shields.io/badge/node-%3E%3D18.0.0-brightgreen)](https://nodejs.org/)
[![Python](https://img.shields.io/badge/python-%3E%3D3.10-blue)](https://www.python.org/)
[![TypeScript](https://img.shields.io/badge/typescript-%3E%3D5.0-blue)](https://www.typescriptlang.org/)

## 🚀 Overview

This platform revolutionizes content creation by leveraging AI to generate, personalize, and optimize content across multiple channels. Built for marketers, content creators, and businesses who want to scale their content operations while maintaining quality and brand consistency.

### Key Features

- **🎨 Creative Studio**: Generate multi-format content from a single brief
- **👥 Personalization Engine**: Auto-create persona-targeted variants
- **📅 Smart Scheduler**: Optimize posting times across platforms
- **📊 Analytics & A/B Testing**: Measure performance and iterate automatically
- **✅ Content Safety**: Built-in moderation and brand policy enforcement
- **🔄 Human-in-the-Loop**: Approval workflows and governance controls

## 📋 Table of Contents

- [Demo](#-demo)
- [Quick Start](#-quick-start)
- [Features](#-features)
- [Architecture](#-architecture)
- [Installation](#-installation)
- [Configuration](#-configuration)
- [Usage](#-usage)
- [API Documentation](#-api-documentation)
- [Development](#-development)
- [Testing](#-testing)
- [Deployment](#-deployment)
- [Contributing](#-contributing)
- [License](#-license)

## 🎥 Demo

### Live Demo
[https://demo.contentplatform.ai](https://demo.contentplatform.ai)

### Video Walkthrough
[![Demo Video](https://img.youtube.com/vi/DEMO_VIDEO_ID/0.jpg)](https://www.youtube.com/watch?v=DEMO_VIDEO_ID)

### Screenshots

**Content Generation**
```
Brief → AI Generation → 3 Variants with Predictions
```

**Persona Personalization**
```
Base Content → Select Personas → Targeted Variants
```

**Analytics Dashboard**
```
Real-time Metrics → A/B Test Results → AI Suggestions
```

## ⚡ Quick Start

### Prerequisites

- Node.js 18+ and npm/yarn
- Python 3.10+
- PostgreSQL 15+
- Redis 7+
- Docker & Docker Compose (recommended)

### 5-Minute Setup

```bash
# Clone the repository
git clone https://github.com/yourusername/content-platform.git
cd content-platform

# Copy environment variables
cp .env.example .env

# Add your API keys to .env
# OPENAI_API_KEY=sk-...
# DATABASE_URL=postgresql://...

# Start with Docker Compose
docker-compose up -d

# Access the application
# Frontend: http://localhost:3000
# API: http://localhost:8000
# API Docs: http://localhost:8000/docs
```

That's it! 🎉

## ✨ Features

### Creative Studio

Generate multiple content formats from a single brief:

- **Social Posts**: Twitter/X, Instagram, LinkedIn, Facebook
- **Email**: Subject lines + body copy
- **Blog Content**: Intros, TL;DRs, outlines
- **Video Scripts**: Short-form content scripts
- **Image Prompts**: AI-ready image generation prompts

**Style Controls:**
- Tone (witty, professional, empathetic, urgent)
- Length (short, medium, long)
- Emoji density
- CTA style (soft, direct, urgent)

### Personalization Engine

Transform content for different audience segments:

- **Persona Targeting**: Early adopters, price-sensitive, enterprise, etc.
- **Contextual Adaptation**: Language, region, currency
- **Dynamic CTAs**: Persona-specific calls-to-action
- **Compliance**: Auto-adjust for regional regulations

### Distribution & Scheduler

- **Multi-Platform**: Schedule across all major social platforms
- **Smart Send**: AI-recommended optimal posting times
- **Auto-Formatting**: Platform-specific constraints (character limits, hashtags)
- **Bulk Scheduling**: Calendar view with drag-and-drop

### Analytics & Optimization

- **Real-time Metrics**: CTR, engagement, reach, conversions
- **A/B Testing**: Automated variant testing with early stopping
- **Performance Insights**: Persona-level analytics
- **AI Suggestions**: Automated content improvement recommendations

### Safety & Governance

- **Content Moderation**: Toxicity, hate speech, violence detection
- **Brand Policy**: Custom rule enforcement
- **Approval Workflows**: Multi-stage review process
- **Audit Logs**: Complete content history and provenance

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    Frontend (Next.js)                    │
│              React + TypeScript + Tailwind               │
└─────────────────────────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────┐
│              API Layer (FastAPI / Express)               │
│    Content Gen │ Personalization │ Scheduler │ Analytics│
└─────────────────────────────────────────────────────────┘
                            │
        ┌───────────────────┼───────────────────┐
        ▼                   ▼                   ▼
┌──────────────┐   ┌──────────────┐   ┌──────────────┐
│  LLM Layer   │   │  Vector DB   │   │  PostgreSQL  │
│  (OpenAI)    │   │   (FAISS)    │   │   + Redis    │
└──────────────┘   └──────────────┘   └──────────────┘
```

**Tech Stack:**
- **Frontend**: Next.js 14, React 18, TypeScript, Tailwind CSS
- **Backend**: FastAPI (Python) or Express (Node.js)
- **AI/ML**: OpenAI GPT-4, LangChain, FAISS
- **Database**: PostgreSQL, Redis
- **Infrastructure**: Docker, Kubernetes (optional)

See [design.md](./design.md) for detailed architecture.

## 📦 Installation

### Option 1: Docker Compose (Recommended)

```bash
# Clone and setup
git clone https://github.com/yourusername/content-platform.git
cd content-platform
cp .env.example .env

# Edit .env with your API keys
nano .env

# Start all services
docker-compose up -d

# Check status
docker-compose ps

# View logs
docker-compose logs -f
```

### Option 2: Manual Installation

#### Backend (Python/FastAPI)

```bash
cd backend
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt

# Run migrations
alembic upgrade head

# Start server
uvicorn main:app --reload --port 8000
```

#### Backend (Node.js/Express)

```bash
cd backend
npm install

# Run migrations
npx prisma migrate dev

# Start server
npm run dev
```

#### Frontend

```bash
cd frontend
npm install
npm run dev
```

#### Database Setup

```bash
# PostgreSQL
createdb content_platform

# Redis
redis-server
```

## ⚙️ Configuration

### Environment Variables

Create a `.env` file in the root directory:

```bash
# Application
NODE_ENV=development
PORT=3000
API_PORT=8000

# Database
DATABASE_URL=postgresql://user:password@localhost:5432/content_platform
REDIS_URL=redis://localhost:6379

# LLM APIs
OPENAI_API_KEY=sk-...
ANTHROPIC_API_KEY=sk-ant-...

# Vector Database
PINECONE_API_KEY=...
PINECONE_ENVIRONMENT=...

# Storage
AWS_ACCESS_KEY_ID=...
AWS_SECRET_ACCESS_KEY=...
S3_BUCKET_NAME=...

# Social Media APIs (Optional)
TWITTER_API_KEY=...
TWITTER_API_SECRET=...
TWITTER_ACCESS_TOKEN=...
TWITTER_ACCESS_SECRET=...

META_ACCESS_TOKEN=...
LINKEDIN_CLIENT_ID=...
LINKEDIN_CLIENT_SECRET=...

# Content Safety
PERSPECTIVE_API_KEY=...

# Security
JWT_SECRET=your-secret-key-here
ENCRYPTION_KEY=your-encryption-key-here

# Feature Flags
ENABLE_IMAGE_GENERATION=true
ENABLE_AB_TESTING=true
ENABLE_SMART_SEND=true
```

### Platform Configuration

Edit `config/platforms.json` for platform-specific settings:

```json
{
  "twitter": {
    "maxLength": 280,
    "imageAspect": "16:9",
    "hashtagLimit": 2,
    "enabled": true
  },
  "instagram": {
    "maxLength": 2200,
    "imageAspect": "1:1",
    "hashtagLimit": 30,
    "enabled": true
  }
}
```

## 🎯 Usage

### 1. Create a Campaign

```bash
curl -X POST http://localhost:8000/api/campaigns \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -d '{
    "name": "Product Launch",
    "goal": "awareness"
  }'
```

### 2. Generate Content

```bash
curl -X POST http://localhost:8000/api/generate/brief \
  -H "Content-Type: application/json" \
  -d '{
    "campaignId": "uuid",
    "targetAudience": "Urban professionals, 25-35",
    "keyMessage": "Eco-friendly water bottle",
    "tone": ["witty", "helpful"],
    "channels": ["twitter", "instagram"],
    "numVariants": 3
  }'
```

### 3. Personalize for Personas

```bash
curl -X POST http://localhost:8000/api/generate/personalize \
  -H "Content-Type: application/json" \
  -d '{
    "contentId": "uuid",
    "personaIds": ["early_adopters", "price_sensitive"]
  }'
```

### 4. Schedule Content

```bash
curl -X POST http://localhost:8000/api/schedule \
  -H "Content-Type: application/json" \
  -d '{
    "contentId": "uuid",
    "platform": "twitter",
    "useSmartSend": true
  }'
```

### Web Interface

1. **Navigate to** `http://localhost:3000`
2. **Login** with your credentials
3. **Create a brief** using the form
4. **Review generated variants**
5. **Personalize** for target personas
6. **Schedule** or publish immediately
7. **Monitor** performance in analytics

## 📚 API Documentation

### Interactive API Docs

- **Swagger UI**: http://localhost:8000/docs
- **ReDoc**: http://localhost:8000/redoc

### Key Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/login` | Authenticate user |
| GET | `/api/campaigns` | List campaigns |
| POST | `/api/generate/brief` | Generate content |
| POST | `/api/generate/personalize` | Personalize content |
| POST | `/api/schedule` | Schedule post |
| GET | `/api/analytics/content/:id` | Get analytics |
| POST | `/api/ab-tests` | Create A/B test |

See [API.md](./docs/API.md) for complete documentation.

## 🛠️ Development

### Project Structure

```
content-platform/
├── frontend/                # Next.js frontend
│   ├── src/
│   │   ├── app/            # App router pages
│   │   ├── components/     # React components
│   │   ├── lib/            # Utilities
│   │   └── styles/         # CSS/Tailwind
│   └── package.json
├── backend/                 # FastAPI/Express backend
│   ├── src/
│   │   ├── api/            # API routes
│   │   ├── services/       # Business logic
│   │   ├── models/         # Data models
│   │   └── utils/          # Utilities
│   └── requirements.txt
├── docs/                    # Documentation
├── scripts/                 # Utility scripts
├── docker-compose.yml
├── .env.example
└── README.md
```

### Development Workflow

```bash
# Create feature branch
git checkout -b feature/your-feature

# Make changes and test
npm run test
npm run lint

# Commit with conventional commits
git commit -m "feat: add persona selector component"

# Push and create PR
git push origin feature/your-feature
```

### Code Style

- **Frontend**: ESLint + Prettier
- **Backend**: Black (Python) / ESLint (Node.js)
- **Commits**: Conventional Commits

```bash
# Format code
npm run format

# Lint
npm run lint

# Type check
npm run type-check
```

## 🧪 Testing

### Run All Tests

```bash
# Frontend
cd frontend
npm test
npm run test:e2e

# Backend
cd backend
pytest
pytest --cov=src tests/
```

### Test Categories

**Unit Tests**
```bash
npm run test:unit
```

**Integration Tests**
```bash
npm run test:integration
```

**E2E Tests**
```bash
npm run test:e2e
```

### Test Coverage

```bash
npm run test:coverage
```

Target: 80%+ coverage

## 🚀 Deployment

### Production Deployment

#### Using Docker

```bash
# Build images
docker build -t contentplatform/frontend:latest ./frontend
docker build -t contentplatform/backend:latest ./backend

# Push to registry
docker push contentplatform/frontend:latest
docker push contentplatform/backend:latest

# Deploy
docker-compose -f docker-compose.prod.yml up -d
```

#### Using Kubernetes

```bash
# Apply configurations
kubectl apply -f k8s/namespace.yaml
kubectl apply -f k8s/secrets.yaml
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
kubectl apply -f k8s/ingress.yaml

# Check status
kubectl get pods -n content-platform
```

### Platform-Specific Deployment

**Vercel (Frontend)**
```bash
vercel --prod
```

**Railway (Backend)**
```bash
railway up
```

**AWS ECS**
```bash
aws ecs update-service --cluster content-platform --service api --force-new-deployment
```

### Environment Setup

1. **Staging**: `staging.contentplatform.ai`
2. **Production**: `app.contentplatform.ai`

### Monitoring

- **Uptime**: https://status.contentplatform.ai
- **Metrics**: Grafana dashboard
- **Logs**: CloudWatch / Datadog
- **Errors**: Sentry

## 📖 Documentation

- [Requirements](./requirements.md) - Detailed requirements and tech stack
- [Design Document](./design.md) - Architecture and design decisions
- [API Reference](./docs/API.md) - Complete API documentation
- [User Guide](./docs/USER_GUIDE.md) - End-user documentation
- [Contributing](./CONTRIBUTING.md) - Contribution guidelines
- [Changelog](./CHANGELOG.md) - Version history

## 🤝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](./CONTRIBUTING.md) for details.

### Quick Contribution Guide

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests
5. Submit a pull request

### Development Setup

```bash
# Fork and clone
git clone https://github.com/YOUR_USERNAME/content-platform.git

# Install dependencies
npm install

# Create branch
git checkout -b feature/amazing-feature

# Make changes and test
npm test

# Commit and push
git commit -m "feat: add amazing feature"
git push origin feature/amazing-feature
```

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

## 🙏 Acknowledgments

- [OpenAI](https://openai.com/) for GPT models
- [LangChain](https://langchain.com/) for LLM orchestration
- [Vercel](https://vercel.com/) for hosting platform
- [Next.js](https://nextjs.org/) team for the amazing framework
- Open-source community for incredible tools

## 📞 Support

- **Documentation**: https://docs.contentplatform.ai
- **Discord**: https://discord.gg/contentplatform
- **Email**: support@contentplatform.ai
- **Issues**: https://github.com/yourusername/content-platform/issues

## 🗺️ Roadmap

### Q1 2026
- [x] MVP Launch
- [x] Core content generation
- [x] Basic personalization
- [ ] Twitter/X integration
- [ ] Instagram integration

### Q2 2026
- [ ] Advanced A/B testing
- [ ] Image generation
- [ ] LinkedIn integration
- [ ] Team collaboration features

### Q3 2026
- [ ] Custom AI model fine-tuning
- [ ] Advanced analytics
- [ ] Multi-language support
- [ ] Mobile app

### Q4 2026
- [ ] Enterprise features
- [ ] White-label solution
- [ ] API marketplace
- [ ] Advanced automation

See [ROADMAP.md](./ROADMAP.md) for detailed plans.

## 📊 Stats

![GitHub stars](https://img.shields.io/github/stars/yourusername/content-platform?style=social)
![GitHub forks](https://img.shields.io/github/forks/yourusername/content-platform?style=social)
![GitHub issues](https://img.shields.io/github/issues/yourusername/content-platform)
![GitHub pull requests](https://img.shields.io/github/issues-pr/yourusername/content-platform)

---

**Built with ❤️ by the Content Platform Team**

[Website](https://contentplatform.ai) • [Documentation](https://docs.contentplatform.ai) • [Blog](https://blog.contentplatform.ai)
