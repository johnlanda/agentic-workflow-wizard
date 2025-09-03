# Project Requirements Template for Claude Code Setup

Copy this template and fill it out to quickly configure your Claude Code multi-agent workflow.

## Project Information

**Project Name:** [Your Project Name]

**Project Type:** 
- [ ] Web Application (full-stack)
- [ ] API Service (backend only)
- [ ] Frontend Application (SPA)
- [ ] Mobile Application
- [ ] CLI Tool
- [ ] Library/Package
- [ ] Microservices
- [ ] Other: ___________

**Project Stage:**
- [ ] Brand new (no code yet)
- [ ] Early development (< 1000 lines)
- [ ] Active development (1000-10000 lines)
- [ ] Mature (> 10000 lines)
- [ ] Legacy (needs refactoring)

## Technology Stack

### Frontend
**Framework:** 
- [ ] React
- [ ] Vue.js
- [ ] Angular
- [ ] Next.js
- [ ] Svelte
- [ ] None (backend only)
- [ ] Other: ___________

**Styling:**
- [ ] TailwindCSS
- [ ] CSS Modules
- [ ] Styled Components
- [ ] SASS/SCSS
- [ ] Material UI
- [ ] Other: ___________

**State Management:**
- [ ] Redux
- [ ] Zustand
- [ ] Context API
- [ ] MobX
- [ ] Pinia
- [ ] Other: ___________

### Backend
**Language/Runtime:**
- [ ] Node.js
- [ ] Python
- [ ] Go
- [ ] Java
- [ ] C#/.NET
- [ ] Ruby
- [ ] PHP
- [ ] Rust
- [ ] Other: ___________

**Framework:**
- [ ] Express (Node.js)
- [ ] FastAPI (Python)
- [ ] Django (Python)
- [ ] Spring Boot (Java)
- [ ] ASP.NET Core (C#)
- [ ] Rails (Ruby)
- [ ] Laravel (PHP)
- [ ] Gin (Go)
- [ ] Other: ___________

**API Type:**
- [ ] REST
- [ ] GraphQL
- [ ] gRPC
- [ ] WebSocket
- [ ] Mixed

### Database
**Primary Database:**
- [ ] PostgreSQL
- [ ] MySQL
- [ ] MongoDB
- [ ] SQLite
- [ ] DynamoDB
- [ ] Firestore
- [ ] Other: ___________

**Caching:**
- [ ] Redis
- [ ] Memcached
- [ ] In-memory
- [ ] None
- [ ] Other: ___________

### Infrastructure
**Deployment Target:**
- [ ] AWS
- [ ] Google Cloud
- [ ] Azure
- [ ] Vercel
- [ ] Netlify
- [ ] Heroku
- [ ] Self-hosted
- [ ] Other: ___________

**Containerization:**
- [ ] Docker
- [ ] Kubernetes
- [ ] Docker Compose only
- [ ] None

**CI/CD:**
- [ ] GitHub Actions
- [ ] GitLab CI
- [ ] Jenkins
- [ ] CircleCI
- [ ] None yet
- [ ] Other: ___________

## Features & Requirements

### Core Features
- [ ] User Authentication
  - [ ] Email/Password
  - [ ] OAuth (Google, GitHub, etc.)
  - [ ] SSO
  - [ ] 2FA
- [ ] Payment Processing
  - [ ] Stripe
  - [ ] PayPal
  - [ ] Other: ___________
- [ ] Real-time Features
  - [ ] Chat
  - [ ] Notifications
  - [ ] Live updates
- [ ] File Uploads
  - [ ] Images
  - [ ] Documents
  - [ ] Video
- [ ] Email Services
- [ ] Search Functionality
- [ ] Admin Dashboard
- [ ] API for Third Parties
- [ ] Internationalization (i18n)
- [ ] Other: ___________

### Quality Requirements

**Testing Standards:**
- [ ] Unit Tests
  - Target Coverage: _____%
- [ ] Integration Tests
- [ ] E2E Tests
- [ ] Performance Tests
- [ ] Security Tests

**Code Quality:**
- [ ] Linting (ESLint, Prettier, etc.)
- [ ] Type Checking (TypeScript, PropTypes)
- [ ] Code Reviews Required
- [ ] Documentation Required

**Performance Targets:**
- Load Time: _____ seconds
- API Response Time: _____ ms
- Concurrent Users: _____
- Database Query Time: _____ ms

**Security Requirements:**
- [ ] OWASP Top 10 compliance
- [ ] PCI DSS (for payments)
- [ ] GDPR compliance
- [ ] HIPAA compliance
- [ ] SOC 2
- [ ] Other: ___________

## Team & Workflow

**Team Size:**
- [ ] Solo developer
- [ ] Small team (2-5)
- [ ] Medium team (6-15)
- [ ] Large team (16+)

**Development Methodology:**
- [ ] Agile/Scrum
- [ ] Kanban
- [ ] Waterfall
- [ ] Ad-hoc
- [ ] Other: ___________

**Release Cycle:**
- [ ] Continuous Deployment
- [ ] Daily
- [ ] Weekly
- [ ] Sprint-based (2 weeks)
- [ ] Monthly
- [ ] As needed

## Special Considerations

**Domain-Specific Requirements:**
[Describe any industry-specific needs, compliance requirements, or special constraints]

**Integration Requirements:**
[List any third-party services, APIs, or systems you need to integrate with]

**Performance Constraints:**
[Note any specific performance requirements or limitations]

**Scalability Needs:**
[Describe expected growth and scaling requirements]

## Priority Agents

Based on your project, which types of agents do you think you'll need most?

**Essential:**
- [ ] Frontend Developer
- [ ] Backend Developer
- [ ] Database Architect
- [ ] QA/Testing Expert
- [ ] DevOps Engineer
- [ ] Security Expert
- [ ] Documentation Writer

**Nice to Have:**
- [ ] Performance Engineer
- [ ] UX Designer
- [ ] Cloud Architect
- [ ] Mobile Developer
- [ ] Data Scientist
- [ ] Accessibility Expert

## Additional Notes

[Any other information that would help configure your Claude Code agents]

---

## How to Use This Template

1. **Copy this template** to a new file (e.g., `my-project-requirements.md`)
2. **Fill out all relevant sections** - check boxes and fill in details
3. **Save the file** in your project directory
4. **Share with the workflow designer**: 
   ```
   "Here's my project requirements: [paste contents or provide file path]"
   ```
5. **The workflow designer will**:
   - Parse your requirements
   - Select optimal agents
   - Generate workflows
   - Create configuration

## Quick Fill Examples

### SaaS Web Application
```
Project Type: Web Application (full-stack)
Frontend: React, TailwindCSS, Redux
Backend: Node.js, Express, REST API
Database: PostgreSQL, Redis
Features: Auth, Payments, Real-time
Quality: 80% coverage, ESLint
Team: Small (2-5)
```

### Mobile App with Backend
```
Project Type: Mobile Application
Frontend: React Native
Backend: Python, FastAPI, GraphQL
Database: MongoDB
Features: Auth, Push Notifications
Quality: E2E tests, Security tests
Team: Medium (6-15)
```

### Microservices Architecture
```
Project Type: Microservices
Backend: Go, gRPC
Database: PostgreSQL, Redis
Infrastructure: Kubernetes, AWS
Quality: 90% coverage, Performance tests
Team: Large (16+)
```