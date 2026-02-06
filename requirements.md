# Requirements - AI Content Generation & Distribution Platform

## Project Overview
An AI-powered content generation and distribution platform that transforms a single creative brief into multi-format, persona-targeted content across channels with automated scheduling, A/B testing, and performance optimization.

## Core Product Pillars

### 1. Creative Studio (Generate & Transform)
- Single brief → multi-format outputs
- Style controls and variant generation
- Multi-channel content adaptation

### 2. Personalization Engine
- Persona-targeted content variants
- Contextual replacements and localization
- Historical engagement-based optimization

### 3. Distribution & Scheduler
- Unified cross-channel scheduling
- Platform-specific formatting
- Smart send time recommendations

### 4. Measure, Learn, Iterate
- Lightweight A/B experiments
- Early-signal analytics
- Automated performance-based rewrites

### 5. Human-in-the-Loop & Governance
- Approval workflows
- Content safety checks
- Audit logs and compliance

## Technology Stack

### Frontend
- **React 18+** - UI framework
- **Next.js 14+** - React framework with SSR/SSG
- **Tailwind CSS** - Utility-first styling
- **shadcn/ui** - Component library (optional)
- **React Query** - Data fetching and caching
- **Zustand** or **Redux Toolkit** - State management

### Backend
- **Node.js 18+** with **Express** OR **Python 3.10+** with **FastAPI**
- **TypeScript** (if Node.js) - Type safety
- **Pydantic** (if Python) - Data validation

### LLM & AI Layer
- **OpenAI API** (GPT-4/GPT-3.5-turbo) - Primary LLM
- **Anthropic Claude** - Alternative LLM
- **Hugging Face Transformers** - Local/open-source models
- **LangChain** - LLM orchestration and prompt management
- **tiktoken** - Token counting and management

### Vector Database & Embeddings
- **FAISS** - Local vector similarity search (MVP)
- **Pinecone** - Managed vector database (production)
- **Weaviate** - Alternative vector DB
- **OpenAI Embeddings** (text-embedding-ada-002) - Text embeddings
- **Sentence Transformers** - Open-source embeddings

### Content Safety & Moderation
- **OpenAI Moderation API** - Toxicity detection
- **Perspective API** - Google's toxicity scoring
- **detoxify** - Local toxicity detection
- **profanity-check** - Profanity filtering

### Database & Storage
- **PostgreSQL 15+** - Primary database
- **Prisma** or **SQLAlchemy** - ORM
- **Redis** - Caching and session management
- **AWS S3** or **Cloudflare R2** - Asset storage
- **MinIO** - Self-hosted S3-compatible storage (dev)

### Analytics & Experimentation
- **Mixpanel** or **Amplitude** - Product analytics
- **PostHog** - Open-source analytics
- **Custom event tracking** - Lightweight ingestion
- **pandas** - Data analysis
- **scikit-learn** - ML for ranking/scoring

### Social Media APIs
- **Twitter/X API v2** - Twitter integration
- **Meta Graph API** - Facebook/Instagram
- **LinkedIn API** - LinkedIn posting
- **Buffer API** or **Hootsuite API** - Multi-platform scheduling

### Image Generation
- **DALL-E 3** - OpenAI image generation
- **Stable Diffusion** - Open-source image generation
- **Midjourney API** - High-quality images (if available)
- **Replicate** - Model hosting platform

### DevOps & Infrastructure
- **Docker** - Containerization
- **Docker Compose** - Local orchestration
- **Kubernetes** - Production orchestration (optional)
- **GitHub Actions** or **GitLab CI** - CI/CD
- **Vercel** or **Netlify** - Frontend deployment
- **Railway** or **Render** - Backend deployment

### Monitoring & Logging
- **Sentry** - Error tracking
- **LogRocket** - Session replay
- **Winston** or **Pino** (Node) / **loguru** (Python) - Logging
- **Prometheus** + **Grafana** - Metrics (production)

## MVP Dependencies (Hackathon-Ready)

### Frontend (React + Next.js)
```json
{
  "dependencies": {
    "next": "^14.0.0",
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "tailwindcss": "^3.3.0",
    "@tanstack/react-query": "^5.0.0",
    "zustand": "^4.4.0",
    "axios": "^1.6.0",
    "react-hook-form": "^7.48.0",
    "zod": "^3.22.0",
    "date-fns": "^2.30.0",
    "lucide-react": "^0.294.0"
  }
}
```

### Backend (FastAPI - Python)
```txt
fastapi==0.104.1
uvicorn[standard]==0.24.0
pydantic==2.5.0
python-dotenv==1.0.0
openai==1.3.0
langchain==0.0.340
faiss-cpu==1.7.4
sentence-transformers==2.2.2
sqlalchemy==2.0.23
psycopg2-binary==2.9.9
redis==5.0.1
pandas==2.1.3
scikit-learn==1.3.2
numpy==1.26.2
python-multipart==0.0.6
httpx==0.25.2
tiktoken==0.5.1
detoxify==0.5.1
```

### Backend (Express - Node.js)
```json
{
  "dependencies": {
    "express": "^4.18.0",
    "typescript": "^5.3.0",
    "openai": "^4.20.0",
    "langchain": "^0.0.200",
    "@pinecone-database/pinecone": "^1.1.0",
    "prisma": "^5.7.0",
    "@prisma/client": "^5.7.0",
    "redis": "^4.6.0",
    "zod": "^3.22.0",
    "dotenv": "^16.3.0",
    "cors": "^2.8.5",
    "helmet": "^7.1.0",
    "express-rate-limit": "^7.1.0",
    "winston": "^3.11.0"
  }
}
```

## Installation & Setup

### Prerequisites
- **Node.js 18+** and **npm/yarn/pnpm**
- **Python 3.10+** and **pip**
- **PostgreSQL 15+**
- **Redis 7+**
- **Docker** and **Docker Compose** (recommended)

### Environment Variables
Create a `.env` file:
```bash
# LLM APIs
OPENAI_API_KEY=sk-...
ANTHROPIC_API_KEY=sk-ant-...

# Database
DATABASE_URL=postgresql://user:password@localhost:5432/content_platform
REDIS_URL=redis://localhost:6379

# Vector DB
PINECONE_API_KEY=...
PINECONE_ENVIRONMENT=...

# Storage
AWS_ACCESS_KEY_ID=...
AWS_SECRET_ACCESS_KEY=...
S3_BUCKET_NAME=...

# Social APIs (optional for MVP)
TWITTER_API_KEY=...
TWITTER_API_SECRET=...
META_ACCESS_TOKEN=...

# Content Safety
PERSPECTIVE_API_KEY=...

# App Config
NODE_ENV=development
PORT=3000
API_PORT=8000
JWT_SECRET=...
```

### Quick Start (Docker Compose)
```bash
# Clone repository
git clone <repo-url>
cd content-platform

# Start all services
docker-compose up -d

# Frontend will be at http://localhost:3000
# Backend API at http://localhost:8000
```

### Manual Setup

#### Frontend
```bash
cd frontend
npm install
npm run dev
```

#### Backend (Python/FastAPI)
```bash
cd backend
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
uvicorn main:app --reload --port 8000
```

#### Backend (Node.js/Express)
```bash
cd backend
npm install
npm run dev
```

#### Database Setup
```bash
# Run migrations
npx prisma migrate dev  # Node.js
# OR
alembic upgrade head    # Python

# Seed initial data
npm run seed  # or python seed.py
```

## Architecture Overview

### High-Level Components

```
┌─────────────────────────────────────────────────────────┐
│                     Frontend (Next.js)                   │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌─────────┐ │
│  │  Brief   │  │ Persona  │  │ Schedule │  │Analytics│ │
│  │  Form    │  │ Variants │  │   UI     │  │  View   │ │
│  └──────────┘  └──────────┘  └──────────┘  └─────────┘ │
└─────────────────────────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────┐
│                  API Layer (Express/FastAPI)             │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌─────────┐ │
│  │ Content  │  │Personali-│  │Scheduler │  │Analytics│ │
│  │Generator │  │  zation  │  │  Engine  │  │ Engine  │ │
│  └──────────┘  └──────────┘  └──────────┘  └─────────┘ │
└─────────────────────────────────────────────────────────┘
                            │
        ┌───────────────────┼───────────────────┐
        ▼                   ▼                   ▼
┌──────────────┐   ┌──────────────┐   ┌──────────────┐
│  LLM Layer   │   │  Vector DB   │   │  PostgreSQL  │
│  (OpenAI)    │   │   (FAISS)    │   │   + Redis    │
└──────────────┘   └──────────────┘   └──────────────┘
```

### Data Flow

1. **Content Generation**
   - User submits brief → API validates → LLM generates variants → Store in DB
   
2. **Personalization**
   - Select variant → Fetch persona profiles → LLM transforms → Return personalized versions
   
3. **Scheduling**
   - Select variants → Choose channels → Calculate optimal times → Queue for distribution
   
4. **Analytics**
   - Track engagement → Calculate metrics → Identify low performers → Generate suggestions

## Core Features & Implementation

### 1. Creative Studio

#### Content Generation Pipeline
```python
# Prompt template structure
system_prompt = """
You are a creative content generator for {brand_name}.
Brand voice: {brand_voice}
Safety constraints: {safety_rules}
"""

user_prompt = """
Create {format} content for:
- Target audience: {audience}
- Goal: {goal}
- Tone: {tone}
- Key message: {message}
- Platform: {platform}

Generate {num_variants} distinct variants.
"""
```

#### Output Formats
- Social posts (Twitter/X, Instagram, LinkedIn, Threads)
- Email (subject + body)
- Blog intro + TL;DR
- Video script (short-form)
- Carousel copy
- Image generation prompts

#### Style Controls
- Tone: professional, witty, empathetic, urgent, educational
- Length: short (50-100 chars), medium (100-200), long (200-280)
- Emoji density: none, light, moderate, heavy
- CTA style: soft, direct, urgent

### 2. Personalization Engine

#### Persona Definitions
```json
{
  "early_adopters": {
    "description": "Tech-savvy, innovation-focused, willing to pay premium",
    "tone_adjustments": "emphasize novelty, use tech jargon",
    "cta_style": "exclusive access, limited availability"
  },
  "price_sensitive": {
    "description": "Budget-conscious, value-seeking, comparison shoppers",
    "tone_adjustments": "highlight savings, ROI, discounts",
    "cta_style": "limited-time offer, price anchoring"
  },
  "enterprise": {
    "description": "B2B decision makers, ROI-focused, risk-averse",
    "tone_adjustments": "professional, data-driven, security-focused",
    "cta_style": "schedule demo, request proposal"
  }
}
```

#### Personalization Features
- Contextual replacements (language, region, currency)
- Persona-specific CTAs
- Compliance-safe phrasing
- Cultural adaptation

### 3. Distribution & Scheduler

#### Platform Constraints
```javascript
const platformConstraints = {
  twitter: { maxLength: 280, imageAspect: "16:9", hashtagLimit: 2 },
  instagram: { maxLength: 2200, imageAspect: "1:1", hashtagLimit: 30 },
  linkedin: { maxLength: 3000, imageAspect: "1.91:1", hashtagLimit: 5 },
  facebook: { maxLength: 63206, imageAspect: "1.91:1", hashtagLimit: 10 }
};
```

#### Smart Send Algorithm
```python
def calculate_optimal_send_time(
    historical_engagement: pd.DataFrame,
    target_audience: str,
    timezone: str
) -> datetime:
    # Analyze historical CTR by hour/day
    # Weight by audience activity patterns
    # Return top 3 recommended time slots
    pass
```

### 4. Analytics & Optimization

#### Metrics Tracked
- Click-through rate (CTR)
- Engagement rate (likes, shares, comments)
- Conversion rate
- Reach and impressions
- Persona-specific performance

#### A/B Testing
```python
class ABTest:
    def __init__(self, variants: List[Content], split: List[float]):
        self.variants = variants
        self.split = split  # e.g., [0.5, 0.5] for 50/50
        
    def early_stopping_check(self, confidence: float = 0.95) -> Optional[Content]:
        # Frequentist approach: check if one variant significantly outperforms
        # Return winner if statistical significance reached
        pass
```

#### Automated Suggestions
- Weak CTA → Suggest stronger action verbs
- Low engagement → Recommend emoji addition
- Poor CTR → Suggest headline rewrite
- Platform mismatch → Adjust length/format

### 5. Content Safety & Governance

#### Safety Checks
```python
async def content_safety_check(text: str) -> SafetyResult:
    # Check 1: OpenAI Moderation API
    moderation = await openai.moderations.create(input=text)
    
    # Check 2: Perspective API (toxicity)
    toxicity_score = await perspective_api.analyze(text)
    
    # Check 3: Custom brand policy rules
    policy_violations = check_brand_policy(text)
    
    return SafetyResult(
        is_safe=all_checks_passed,
        violations=[...],
        suggestions=[...]
    )
```

#### Approval Workflow
1. Content generated → Auto safety check
2. If flagged → Require human review
3. Approved → Ready for scheduling
4. Rejected → Log reason + suggest edits

#### Audit Trail
- Track all generated content
- Log model version and prompt used
- Record human edits and approvals
- Maintain compliance documentation

## MVP Demo Flow (4 Screens)

### Screen 1: Brief → Generate
**Input Fields:**
- Campaign goal (dropdown)
- Target audience (text + persona tags)
- Key message (textarea)
- Tone (multi-select)
- Channels (checkboxes)

**Output:**
- 3 social post variants
- 2 image prompts
- 1 email subject + body
- Side-by-side comparison

### Screen 2: Persona Variants
**Input:**
- Select base variant (from Screen 1)
- Choose personas (checkboxes)

**Output:**
- Side-by-side persona-targeted versions
- Highlight differences (color-coded)
- Edit capability

### Screen 3: Schedule & Experiment
**Input:**
- Select variants for A/B test
- Choose channels
- Set split ratio
- Pick send time (or use "Smart Send")

**Output:**
- Calendar view with scheduled posts
- A/B test configuration summary
- Confirmation modal

### Screen 4: Analytics & Suggestions
**Display:**
- Early metrics (simulated CTR, engagement)
- Variant performance comparison
- Automated suggestion card
- "Apply Rewrite" button

**Actions:**
- Accept suggestion → Regenerate improved copy
- Dismiss → Keep original
- Manual edit

## Sample Prompts & Outputs

### Example 1: Product Launch

**Brief:**
```
Product: EcoSip water bottle
Target: India, urban young professionals (25-35)
Goal: Drive preorders
Tone: Witty + helpful
Channels: Twitter, Instagram
```

**Generated Variants:**

**Variant A (Witty):**
```
Thirsty for something smarter? 💧 Meet the EcoSip — keeps water cool for 24h 
and your conscience lighter. Preorder now & get 10% off. #EcoSip #SustainableLiving
```

**Variant B (Educational):**
```
Did you know? Single-use plastic bottles take 450 years to decompose. 
EcoSip is your reusable solution — 24h cold retention, BPA-free, 
and planet-friendly. Preorder today! 🌍 #EcoSip
```

**Variant C (Empathetic):**
```
We get it — staying hydrated shouldn't harm the planet. That's why we created 
EcoSip: sustainable, stylish, and keeps drinks cold all day. Join the movement. 
Preorder now! 💚 #EcoSip
```

**Persona-Personalized (Price-Sensitive):**
```
Save ₹300 on hydration that lasts! EcoSip keeps your drink cold for 24h — 
preorder today and grab the early-bird discount. Limited stock! 
#EcoSip #SmartShopping
```

**Persona-Personalized (Early Adopters):**
```
Be among the first to own India's smartest water bottle. EcoSip features 
triple-layer insulation tech + sustainable materials. Exclusive preorder 
access ends soon! 🚀 #EcoSip #Innovation
```

### Example 2: SaaS Product

**Brief:**
```
Product: TaskFlow (project management tool)
Target: US, small business owners
Goal: Free trial signups
Tone: Professional + helpful
Channels: LinkedIn, Email
```

**LinkedIn Post:**
```
Tired of juggling multiple tools for project management? TaskFlow brings 
everything together — tasks, timelines, team chat, and reporting in one 
intuitive platform. Try it free for 14 days. No credit card required. 
#ProjectManagement #Productivity
```

**Email Subject:**
```
Simplify project management in 5 minutes
```

**Email Body:**
```
Hi [Name],

Managing projects shouldn't feel like a project itself.

TaskFlow helps small teams stay organized with:
✓ Visual task boards
✓ Automated reminders
✓ Real-time collaboration
✓ One-click reporting

Start your free 14-day trial today — no credit card needed.

[CTA Button: Start Free Trial]

Best,
The TaskFlow Team
```

## Data Requirements

### Seed Data (for MVP)
1. **Brand Voice Examples** (50-200 samples)
   - CSV format: `text, tone, platform, engagement_score`
   - Used for RAG and style matching

2. **Persona Profiles** (5-10 personas)
   - JSON format with descriptions and preferences

3. **Historical Performance Data** (simulated for demo)
   - CSV: `content_id, platform, ctr, engagement_rate, persona`

4. **Platform Constraints** (configuration)
   - JSON with character limits, image specs, hashtag rules

### Sample Data Structure

**brand_content.csv:**
```csv
text,tone,platform,engagement_score,created_at
"Excited to announce our new feature!",professional,linkedin,0.045,2024-01-15
"Weekend vibes 🌴",casual,instagram,0.082,2024-01-14
```

**personas.json:**
```json
[
  {
    "id": "early_adopters",
    "name": "Early Adopters",
    "description": "Tech-savvy innovators",
    "preferences": {
      "tone": ["witty", "technical"],
      "cta_style": "exclusive",
      "emoji_density": "light"
    }
  }
]
```

## System Requirements

### Development
- **CPU**: 4+ cores
- **RAM**: 8GB minimum, 16GB recommended
- **Storage**: 10GB free space
- **OS**: Windows 10+, macOS 12+, Linux (Ubuntu 20.04+)

### Production
- **CPU**: 8+ cores
- **RAM**: 16GB minimum, 32GB recommended
- **Storage**: 50GB+ SSD
- **Network**: 100Mbps+ bandwidth

## Security & Compliance

### API Key Management
- Store all keys in environment variables
- Use secret management service (AWS Secrets Manager, HashiCorp Vault)
- Rotate keys regularly
- Never commit keys to version control

### Data Privacy
- Encrypt sensitive data at rest (AES-256)
- Use HTTPS/TLS for all communications
- Implement GDPR-compliant data deletion
- Maintain audit logs for 90+ days

### Content Safety
- Pre-generation safety checks
- Post-generation moderation
- Human review for sensitive topics
- Compliance with platform policies

### Rate Limiting
```javascript
// Example rate limit configuration
const rateLimits = {
  generation: { requests: 100, window: '1h' },
  api: { requests: 1000, window: '15m' },
  llm: { tokens: 100000, window: '1d' }
};
```

## Testing Strategy

### Unit Tests
- Component testing (React Testing Library)
- API endpoint testing (Jest/Pytest)
- Utility function testing

### Integration Tests
- LLM integration tests (with mocked responses)
- Database operations
- API workflows

### E2E Tests
- User flows (Playwright/Cypress)
- Critical paths: brief → generate → schedule

### Load Testing
- API performance (k6, Locust)
- Concurrent user simulation
- LLM rate limit handling

## Deployment

### Development
```bash
docker-compose up -d
```

### Staging
```bash
# Deploy to staging environment
./scripts/deploy-staging.sh
```

### Production
```bash
# Deploy to production (with approval)
./scripts/deploy-production.sh
```

### Environment-Specific Configs
- **Development**: Local DB, mock APIs, verbose logging
- **Staging**: Cloud DB, real APIs, moderate logging
- **Production**: Replicated DB, real APIs, error-only logging

## Monitoring & Observability

### Key Metrics
- API response time (p50, p95, p99)
- LLM generation latency
- Error rates by endpoint
- User engagement metrics
- Cost per generation

### Alerts
- API downtime
- High error rate (>5%)
- LLM quota exceeded
- Database connection issues

### Dashboards
- Real-time system health
- User activity metrics
- Content performance analytics
- Cost tracking

## Cost Estimation (MVP)

### LLM Costs (OpenAI)
- GPT-4: ~$0.03 per generation (3 variants)
- GPT-3.5-turbo: ~$0.002 per generation
- Embeddings: ~$0.0001 per document

### Infrastructure (Monthly)
- **Hosting**: $50-100 (Vercel + Railway)
- **Database**: $25-50 (managed PostgreSQL)
- **Vector DB**: $0-70 (FAISS free, Pinecone starter)
- **Storage**: $5-20 (S3/R2)
- **Total**: ~$100-250/month for MVP

### Scaling Costs (1000 users)
- **LLM**: $500-1000/month
- **Infrastructure**: $200-500/month
- **Total**: ~$700-1500/month

## Roadmap

### Phase 1: MVP (Hackathon - 48 hours)
- ✅ Basic content generation (3 variants)
- ✅ Persona personalization (2 personas)
- ✅ Simple scheduler UI
- ✅ Simulated analytics
- ✅ Approval workflow

### Phase 2: Beta (2-4 weeks)
- Real social media integrations
- Advanced A/B testing
- Image generation
- Brand voice RAG
- User authentication

### Phase 3: Production (2-3 months)
- Multi-tenant support
- Advanced analytics
- Custom persona builder
- Workflow automation
- Team collaboration

### Phase 4: Scale (6+ months)
- Enterprise features
- White-label solution
- Advanced AI models
- Predictive analytics
- API for developers

## Contributing

### Code Style
- **Frontend**: ESLint + Prettier
- **Backend**: Black (Python) / ESLint (Node)
- **Commits**: Conventional Commits

### Pull Request Process
1. Create feature branch
2. Write tests
3. Update documentation
4. Submit PR with description
5. Pass CI checks
6. Get 2 approvals
7. Merge to main

## Support & Resources

### Documentation
- API docs: `/docs/api`
- User guide: `/docs/user-guide`
- Architecture: `/docs/architecture`

### Community
- Discord: [link]
- GitHub Discussions: [link]
- Email: support@contentplatform.ai

### Learning Resources
- LangChain docs: https://docs.langchain.com
- OpenAI API: https://platform.openai.com/docs
- Next.js: https://nextjs.org/docs
- FastAPI: https://fastapi.tiangolo.com

## License
MIT License - See LICENSE file for details

## Acknowledgments
- OpenAI for GPT models
- Vercel for hosting platform
- Open-source community for amazing tools
