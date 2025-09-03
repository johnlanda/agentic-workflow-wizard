# Project Configuration - Application Development with Claude Code

## 🏗️ Architecture Overview

This project follows a modern cloud-native architecture:
- **Frontend**: Next.js 14+ with TypeScript, React, and shadcn/ui components
- **Backend**: Golang microservices with RESTful APIs
- **Database**: PostgreSQL 14+ with Redis caching layer
- **Infrastructure**: Cloud-agnostic with Terraform IaC
- **CI/CD**: GitHub Actions for automated testing and deployment
- **Monitoring**: Prometheus + Grafana for observability

## 📁 Repository Structure

```
/
├── frontend/                 # Next.js application
│   ├── app/                 # App router pages
│   ├── components/          # React components
│   ├── lib/                 # Utilities and helpers
│   └── tests/              # Frontend tests
├── backend/                 # Golang services
│   ├── cmd/                # Application entrypoints
│   ├── internal/           # Private application code
│   ├── pkg/                # Public packages
│   └── tests/              # Backend tests
├── infrastructure/          # IaC templates
│   ├── terraform/          # Terraform modules
│   └── kubernetes/         # K8s manifests
├── .github/                # GitHub Actions workflows
│   ├── workflows/          # CI/CD pipelines
│   └── actions/            # Custom actions
├── database/               # Database schemas
│   ├── migrations/         # Migration scripts
│   └── seeds/              # Seed data
├── docs/                   # Documentation
│   ├── api/                # API documentation
│   ├── architecture/       # Architecture diagrams
│   └── guides/             # User guides
└── .claude/                # Claude subagent configurations
    ├── subagents/          # Specialized agents
    └── CLAUDE.md           # This file
```

## 🤖 Subagent Usage Guide

### Available Subagents

| Subagent | Purpose | When to Use |
|----------|---------|-------------|
| `requirements-analyst` | Requirements gathering | Analyzing needs, asking clarifying questions, defining specs |
| `cloud-architect` | Infrastructure design and IaC | Setting up cloud resources, designing architecture |
| `frontend-engineer` | React/Next.js development | Building UI components, implementing features |
| `ux-designer` | UX/UI design and specifications | Creating designs, defining interactions |
| `backend-engineer` | Golang service development | Building APIs, implementing business logic |
| `frontend-tester` | Frontend testing | Writing React tests, E2E tests |
| `backend-tester` | Backend testing | Writing Go tests, integration tests |
| `documentation-writer` | Technical documentation | Creating docs, API specs, guides |
| `ci-cd-engineer` | Pipeline development | Setting up CI/CD, deployments |
| `database-architect` | Database design | Schema design, query optimization |
| `security-reviewer` | Security analysis | Code reviews, vulnerability assessment |

### Automatic Delegation

Claude will automatically delegate to the appropriate subagent based on your task description. For example:
- "Design the database schema" → `database-architect`
- "Create a React component" → `frontend-engineer`
- "Review code for security issues" → `security-reviewer`

### Manual Invocation

You can explicitly invoke a specific subagent using the Task tool or by mentioning them directly:
- "Use @frontend-engineer to create a dashboard component"
- "Have @security-reviewer check this authentication flow"

## 🔄 Common Workflows

### Intelligent Workflow Orchestration

**Important**: Subagents are intelligently invoked based on task relevance. The system will:
- **Skip irrelevant subagents** automatically (e.g., skip frontend-engineer for backend-only tasks)
- **Detect task type** from requirements and activate only necessary subagents
- **Adapt workflow** based on the specific needs identified during requirements analysis
- **Optimize for efficiency** by running independent subagents in parallel when possible

### 1. Feature Development Workflow (Adaptive)

```mermaid
graph LR
    A[Requirements Analysis] --> B{Task Type?}
    B -->|UI Required| C[UX Design]
    B -->|API Only| D[Backend Dev]
    B -->|Full Stack| C
    C --> E[Frontend Dev]
    C --> D
    E --> F[Frontend Tests]
    D --> G[Backend Tests]
    F --> H[Integration]
    G --> H
    H --> I{Security Critical?}
    I -->|Yes| J[Security Review]
    I -->|No| K[Documentation]
    J --> K
    K --> L{Deployment Needed?}
    L -->|Yes| M[Deployment]
    L -->|No| N[Complete]
```

**Conditional Steps:**
1. **Always starts** with `@requirements-analyst` to determine scope
2. **UX Design** - Only if UI/UX components are needed
3. **Frontend Development** - Only if client-side work required
4. **Backend Development** - Only if server-side work required
5. **Testing** - Only for components that were developed
6. **Security Review** - Mandatory for auth, payments, PII; optional otherwise
7. **Documentation** - Always executed but scope varies
8. **Deployment** - Only if changes need to be deployed

**Example Scenarios:**

#### Scenario A: API-Only Task
```
User: "Create a REST endpoint for fetching user statistics"
Activated Subagents:
✅ requirements-analyst
⏭️ ux-designer (skipped - no UI)
⏭️ frontend-engineer (skipped - no frontend)
✅ backend-engineer
⏭️ frontend-tester (skipped - no frontend)
✅ backend-tester
✅ documentation-writer
✅ ci-cd-engineer (if auto-deploy enabled)
```

#### Scenario B: UI Component Only
```
User: "Create a data visualization dashboard component"
Activated Subagents:
✅ requirements-analyst
✅ ux-designer
✅ frontend-engineer
⏭️ backend-engineer (skipped - no backend)
✅ frontend-tester
⏭️ backend-tester (skipped - no backend)
✅ documentation-writer
```

#### Scenario C: Database Optimization
```
User: "Optimize the product search query performance"
Activated Subagents:
✅ requirements-analyst
⏭️ ux-designer (skipped - no UI impact)
⏭️ frontend-engineer (skipped - database only)
✅ database-architect
✅ backend-engineer (for query updates)
✅ backend-tester
⏭️ security-reviewer (skipped - no security changes)
✅ documentation-writer
```

**Note**: The requirements-analyst will proactively ask clarifying questions to ensure all edge cases, acceptance criteria, and success metrics are defined before development begins.

### 2. Infrastructure Changes Workflow

```mermaid
graph LR
    A[Requirements] --> B[Architecture Design]
    B --> C[Security Review]
    C --> D[IaC Implementation]
    D --> E[Testing]
    E --> F[Documentation]
    F --> G[Deployment]
```

**Steps:**
1. Design with `@cloud-architect`
2. Review design with `@security-reviewer`
3. Implement infrastructure as code
4. Test in staging environment
5. Document changes
6. Deploy with `@ci-cd-engineer`

### 3. Database Migration Workflow

```mermaid
graph LR
    A[Schema Design] --> B[Migration Script]
    B --> C[Testing]
    C --> D[Backup]
    D --> E[Apply Migration]
    E --> F[Validation]
```

**Steps:**
1. Design with `@database-architect`
2. Create migration scripts
3. Test on development database
4. Backup production data
5. Apply migration
6. Validate data integrity

## 🎛️ Workflow Orchestration Rules

### Subagent Activation Rules

The system uses these rules to determine which subagents to activate:

| Subagent | Activation Conditions | Skip Conditions |
|----------|----------------------|-----------------|
| `requirements-analyst` | Always activated first | Never skipped |
| `ux-designer` | - UI/UX mentioned<br>- Frontend components needed<br>- User interaction required | - API-only tasks<br>- Backend-only tasks<br>- Database-only tasks |
| `frontend-engineer` | - React/Next.js work<br>- UI components<br>- Client-side logic | - Backend-only tasks<br>- Infrastructure tasks<br>- Database-only work |
| `backend-engineer` | - API development<br>- Server logic<br>- Service creation | - Frontend-only tasks<br>- Pure infrastructure<br>- Documentation-only |
| `database-architect` | - Schema changes<br>- Query optimization<br>- Database design | - Frontend-only tasks<br>- No database impact |
| `frontend-tester` | - Frontend code created/modified | - No frontend changes<br>- Backend-only work |
| `backend-tester` | - Backend code created/modified | - No backend changes<br>- Frontend-only work |
| `security-reviewer` | - Authentication/authorization<br>- Payment processing<br>- PII handling<br>- API security | - Pure UI changes<br>- Documentation updates<br>- Non-sensitive features |
| `documentation-writer` | Always activated (scope varies) | Never fully skipped |
| `ci-cd-engineer` | - Deployment needed<br>- Pipeline changes<br>- Environment setup | - Local-only changes<br>- Documentation-only |
| `cloud-architect` | - Infrastructure changes<br>- Scaling requirements<br>- New services | - Code-only changes<br>- No infrastructure impact |

### Task Type Detection

The requirements-analyst determines task type based on keywords and context:

**Frontend Indicators:**
- UI, interface, component, page, screen, button, form
- React, Next.js, TypeScript, CSS, Tailwind
- User experience, interaction, responsive, mobile

**Backend Indicators:**
- API, endpoint, service, server, backend
- Golang, REST, GraphQL, microservice
- Authentication, authorization, middleware

**Database Indicators:**
- Schema, table, query, index, migration
- PostgreSQL, SQL, database, performance
- Data model, relationships, constraints

**Infrastructure Indicators:**
- Deploy, cloud, AWS, Kubernetes, Docker
- Scaling, load balancing, monitoring
- Infrastructure, terraform, CI/CD

### Parallel Execution Rules

Subagents can run in parallel when:
- No direct dependencies exist between them
- Working on different system layers
- Independent features or components

**Common Parallel Patterns:**
- `frontend-engineer` + `backend-engineer` (different layers)
- `frontend-tester` + `backend-tester` (independent testing)
- Multiple `backend-engineer` for different microservices
- `documentation-writer` alongside development tasks

### Override Options

You can override automatic workflow decisions:

```bash
# Force specific subagents
"Use @security-reviewer even though this is a simple UI change"

# Skip specific subagents
"Skip the UX design phase and go straight to implementation"

# Specify parallel execution
"Have frontend and backend engineers work simultaneously"
```

## 🎯 Global Standards

### Code Quality

#### Frontend Standards
```json
{
  "extends": ["next/core-web-vitals"],
  "rules": {
    "no-console": "error",
    "no-unused-vars": "error",
    "@typescript-eslint/no-explicit-any": "error"
  }
}
```

#### Backend Standards
```yaml
linters:
  enable-all: true
  disable:
    - exhaustruct
    - depguard
linters-settings:
  gocyclo:
    min-complexity: 15
  dupl:
    threshold: 100
```

### Git Workflow

- **Branch Naming**: `feature/`, `bugfix/`, `hotfix/`, `release/`
- **Commit Format**: Conventional Commits
  ```
  type(scope): description
  
  [optional body]
  
  [optional footer]
  ```
- **PR Requirements**:
  - All tests must pass
  - Code review from at least one team member
  - Security scan must pass
  - Documentation updated if needed

### Testing Requirements

| Type | Coverage Target | Framework |
|------|----------------|-----------|
| Unit Tests | 80% | Jest/Go testing |
| Integration Tests | 70% | Testing Library/testcontainers |
| E2E Tests | Critical paths | Playwright |

### Security Policies

- **Authentication**: JWT with refresh tokens
- **Authorization**: RBAC with middleware
- **Encryption**: TLS 1.3 minimum
- **Secrets**: Never in code, use environment variables
- **Dependencies**: Regular updates, vulnerability scanning
- **OWASP**: Follow Top 10 guidelines

### Performance Targets

- **Frontend**:
  - First Contentful Paint: < 1.8s
  - Time to Interactive: < 3.9s
  - Cumulative Layout Shift: < 0.1
  
- **Backend**:
  - API Response Time: p95 < 200ms
  - Database Query Time: p95 < 50ms
  - Throughput: > 1000 req/s

## 🚀 Quick Commands

```bash
# Development
npm run dev              # Start frontend dev server
go run cmd/api/main.go   # Start backend server
docker-compose up        # Start all services

# Testing
npm test                 # Run frontend tests
go test ./...           # Run backend tests
npm run e2e             # Run E2E tests

# Building
npm run build           # Build frontend
go build -o app         # Build backend
docker build .          # Build Docker image

# Database
npm run db:migrate      # Run migrations
npm run db:seed         # Seed database
npm run db:reset        # Reset database

# Code Quality
npm run lint            # Lint frontend
golangci-lint run       # Lint backend
npm run format          # Format code
```

## 📚 Resources

- [API Documentation](/docs/api/README.md)
- [Architecture Diagrams](/docs/architecture/README.md)
- [Development Guide](/docs/guides/development.md)
- [Deployment Guide](/docs/guides/deployment.md)
- [Security Guidelines](/docs/security/README.md)

## 🔧 Environment Configuration

### Required Environment Variables

```env
# Frontend
NEXT_PUBLIC_API_URL=http://localhost:8080
NEXT_PUBLIC_SITE_URL=http://localhost:3000

# Backend
DATABASE_URL=postgres://user:pass@localhost:5432/dbname
REDIS_URL=redis://localhost:6379
JWT_SECRET=your-secret-key
PORT=8080

# Infrastructure
AWS_REGION=us-east-1
ENVIRONMENT=development
```

## 📝 Notes for Claude Code

When working on this project:

1. **Always check existing patterns** before implementing new features
2. **Use the appropriate subagent** for specialized tasks
3. **Follow the established conventions** in the codebase
4. **Run tests** after making changes
5. **Update documentation** when adding new features
6. **Consider security implications** of all changes
7. **Optimize for performance** where possible
8. **Keep accessibility in mind** for all UI changes

## 🤝 Collaboration Guidelines

- **Code Reviews**: Required for all changes
- **Documentation**: Keep it up-to-date
- **Communication**: Use clear commit messages
- **Testing**: Write tests for new features
- **Security**: Report vulnerabilities immediately

---

*This configuration is maintained by the development team. For questions or improvements, please create an issue or pull request.*