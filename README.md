# 🚀 CI/CD NextApp : Monorepo
<div align="center">
  <h3>Production-ready Next.js monorepo with automated CI/CD pipeline using Turborepo</h3>
  
  ![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white)
  ![Turborepo](https://img.shields.io/badge/Turborepo-EF4444?style=for-the-badge&logo=turborepo&logoColor=white)
  ![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
  ![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
  ![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
  ![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)
</div>

------

## 🌟 Overview

CI/CD NextApp is a modern, enterprise-grade monorepo built with Turborepo that demonstrates best practices for building, testing, and deploying Next.js applications at scale. This project showcases advanced CI/CD pipelines, remote caching, and automated deployment workflows that can handle multiple applications and shared packages efficiently.

**Perfect for teams building scalable web applications with modern DevOps practices.**

## ✨ Key Features

### 🏗️ **Monorepo Architecture**
- **Turborepo Integration** - Lightning-fast builds with intelligent caching
- **Multiple Applications** - Independent Next.js apps (`web` & `docs`)
- **Shared Packages** - Reusable UI components and configurations
- **Type Safety** - 100% TypeScript across all packages

### 🚀 **CI/CD Pipeline**
- **GitHub Actions** - Automated testing, building, and deployment
- **Parallel Builds** - Concurrent processing of multiple apps
- **Remote Caching** - Shared build cache across team and CI/CD
- **Automated Testing** - Unit, integration, and E2E testing
- **Code Quality** - ESLint, Prettier, and TypeScript checks!

### 📦 **Package Management**
- **PNPM Workspaces** - Efficient dependency management
- **Shared Dependencies** - Optimized package installation
- **Version Management** - Coordinated versioning across packages
- **Dependency Updates** - Automated dependency updates

### 🔧 **Developer Experience**
- **Hot Reload** - Fast development with instant updates
- **Code Generation** - Automated component and page scaffolding
- **VS Code Integration** - Pre-configured workspace settings
- **Git Hooks** - Pre-commit linting and formatting

## 📁 Project Structure

```
CI-CD-NextApp/
├── apps/
│   ├── docs/              # Documentation Next.js app
│   │   ├── app/           # App router pages
│   │   ├── components/    # App-specific components
│   │   ├── public/        # Static assets
│   │   ├── package.json   # App dependencies
│   │   └── next.config.js # Next.js configuration
│   └── web/               # Main web application
│       ├── app/           # App router pages
│       ├── components/    # App-specific components
│       ├── lib/           # Utilities and helpers
│       ├── public/        # Static assets
│       └── package.json   # App dependencies
├── packages/
│   ├── ui/                # Shared UI component library
│   │   ├── src/           # React components
│   │   ├── package.json   # Package configuration
│   │   └── tsconfig.json  # TypeScript config
│   ├── eslint-config/     # Shared ESLint configurations
│   │   └── index.js       # ESLint rules
│   └── typescript-config/ # Shared TypeScript configurations
│       ├── base.json      # Base TS config
│       ├── nextjs.json    # Next.js specific config
│       └── react.json     # React specific config
├── .github/
│   └── workflows/         # GitHub Actions workflows
│       ├── ci.yml         # Continuous integration
│       ├── cd.yml         # Continuous deployment
│       └── pr-check.yml   # Pull request checks
├── docker/                # Docker configurations
│   ├── Dockerfile.web     # Web app container
│   ├── Dockerfile.docs    # Docs app container
│   └── docker-compose.yml # Multi-container setup
├── scripts/               # Build and deployment scripts
├── turbo.json            # Turborepo configuration
├── package.json          # Root package configuration
└── pnpm-workspace.yaml   # PNPM workspace configuration
```

## 🏗️ Architecture & Workflow

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Developer     │    │   GitHub        │    │   CI/CD         │
│                 │    │   Repository    │    │   Pipeline      │
│   Local Dev     │───►│                 │───►│                 │
│   git push      │    │   Pull Request  │    │   Build & Test  │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │                       │
         │                       │                       ▼
         │                       │              ┌─────────────────┐
         │                       │              │   Vercel        │
         │                       │              │   Deployment    │
         │                       │              │                 │
         │                       │              │   web.app.com   │
         │                       │              │   docs.app.com  │
         │                       │              └─────────────────┘
         │                       │
         ▼                       ▼
┌─────────────────┐    ┌─────────────────┐
│   Turborepo     │    │   Remote Cache  │
│   Local Cache   │    │   (Vercel)      │
│                 │    │                 │
│   Fast Builds   │◄──►│   Shared Cache  │
└─────────────────┘    └─────────────────┘
```

## 🚀 Quick Start

### Prerequisites

- Node.js (v18 or higher)
- PNPM (recommended) or npm
- Git
- Docker (for containerized deployment)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Samriddhi3901/CI-CD-NextApp.git
   cd CI-CD-NextApp
   ```

2. **Install dependencies**
   ```bash
   pnpm install
   ```

3. **Start development servers**
   ```bash
   # Start all applications
   pnpm dev
   
   # Or start specific applications
   pnpm dev --filter=web
   pnpm dev --filter=docs
   ```

4. **Access the applications**
   - Web App: [http://localhost:3000](http://localhost:3000)
   - Docs App: [http://localhost:3001](http://localhost:3001)

### Build for Production

```bash
# Build all applications
pnpm build

# Build specific application
pnpm build --filter=web

# Build with remote caching
npx turbo build --remote-cache
```

## 🛠️ Available Scripts

### Development
```bash
pnpm dev          # Start all apps in development mode
pnpm dev:web      # Start only web app
pnpm dev:docs     # Start only docs app
pnpm clean        # Clean all build artifacts
```

### Building
```bash
pnpm build        # Build all applications
pnpm build:web    # Build web application
pnpm build:docs   # Build documentation
```

### Testing
```bash
pnpm test         # Run all tests
pnpm test:unit    # Run unit tests
pnpm test:e2e     # Run end-to-end tests
pnpm test:watch   # Run tests in watch mode
```

### Code Quality
```bash
pnpm lint         # Lint all packages
pnpm lint:fix     # Fix linting issues
pnpm format       # Format code with Prettier
pnpm type-check   # Run TypeScript type checking
```

## 🔄 CI/CD Pipeline

### GitHub Actions Workflows

#### 1. **Continuous Integration** (`.github/workflows/ci.yml`)
```yaml
name: CI Pipeline
on:
  pull_request:
  push:
    branches: [main, develop]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: pnpm/action-setup@v2
        with:
          version: 8
      - uses: actions/setup-node@v4
        with:
          node-version: 18
          cache: 'pnpm'
      
      - run: pnpm install --frozen-lockfile
      - run: pnpm lint
      - run: pnpm type-check
      - run: pnpm test
      - run: pnpm build
```

#### 2. **Continuous Deployment** (`.github/workflows/cd.yml`)
```yaml
name: CD Pipeline
on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Deploy to Vercel
        uses: amondnet/vercel-action@v25
        with:
          vercel-token: ${{ secrets.VERCEL_TOKEN }}
          vercel-org-id: ${{ secrets.VERCEL_ORG_ID }}
          vercel-project-id: ${{ secrets.VERCEL_PROJECT_ID }}
```

### Pipeline Features

- **Parallel Execution** - Multiple jobs run concurrently
- **Cache Optimization** - Dependencies and build artifacts cached
- **Quality Gates** - Automated code quality checks
- **Deployment Automation** - Zero-touch production deployment
- **Rollback Support** - Quick rollback to previous versions

## 📦 Turborepo Configuration

### `turbo.json`
```json
{
  "$schema": "https://turbo.build/schema.json",
  "pipeline": {
    "build": {
      "dependsOn": ["^build"],
      "outputs": [".next/**", "dist/**"]
    },
    "lint": {
      "dependsOn": ["^lint"]
    },
    "dev": {
      "cache": false,
      "persistent": true
    }
  }
}
```

### Remote Caching Setup

1. **Login to Vercel**
   ```bash
   npx turbo login
   ```

2. **Link to Remote Cache**
   ```bash
   npx turbo link
   ```

3. **Build with Remote Cache**
   ```bash
   npx turbo build --remote-cache
   ```

## 🐳 Docker Deployment

### Multi-stage Docker Build

```dockerfile
# Dockerfile.web
FROM node:18-alpine AS base
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production

FROM base AS builder
COPY . .
RUN npm run build

FROM node:18-alpine AS runner
WORKDIR /app
COPY --from=builder /app/.next ./.next
COPY --from=builder /app/public ./public
COPY --from=base /app/node_modules ./node_modules
EXPOSE 3000
CMD ["npm", "start"]
```

### Docker Compose
```yaml
version: '3.8'
services:
  web:
    build:
      context: .
      dockerfile: docker/Dockerfile.web
    ports:
      - "3000:3000"
    environment:
      - NODE_ENV=production

  docs:
    build:
      context: .
      dockerfile: docker/Dockerfile.docs
    ports:
      - "3001:3000"
    environment:
      - NODE_ENV=production
```

## 🔧 Environment Configuration

### Local Development (`.env.local`)
```env
# Application
NEXT_PUBLIC_APP_URL=http://localhost:3000
NEXT_PUBLIC_API_URL=http://localhost:3001/api

# Analytics (optional)
NEXT_PUBLIC_GA_ID=GA_MEASUREMENT_ID

# Feature Flags
NEXT_PUBLIC_FEATURE_FLAGS=true
```

### Production (Vercel)
```env
# Set these in Vercel dashboard
NEXT_PUBLIC_APP_URL=https://your-app.vercel.app
NEXT_PUBLIC_API_URL=https://your-api.vercel.app
DATABASE_URL=postgresql://...
REDIS_URL=redis://...
```

## 📊 Performance Monitoring

### Build Analytics
- **Bundle Size** - Tracked with `@next/bundle-analyzer`
- **Build Time** - Monitored with Turborepo metrics
- **Cache Hit Rate** - Remote cache performance
