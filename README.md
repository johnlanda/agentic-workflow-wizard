# Agentic Workflow Designer for Claude Code

## 🎯 Purpose

This repository contains an **interactive workflow designer** that helps developers automatically configure optimal multi-agent setups for their Claude Code projects. Instead of manually selecting agents and writing workflows, simply describe your project and let Claude Code design the perfect configuration for you.

## 🚀 How It Works

1. **Clone this repository** - It contains the workflow designer agent
2. **Open in Claude Code** - The designer agent is ready to help
3. **Tell Claude your situation**:
   - For new projects: "I want to build a [type] application"
   - For existing projects: "Set up Claude Code for my codebase"
4. **Answer a few questions** - The designer will ask about tech stack and requirements
5. **Get your configuration** - Complete setup generated in `.claude-output/`
6. **Copy to your project** - Move the configuration and start developing!

## 📋 Quick Start

### Option 1: Interactive Setup
```bash
# 1. Clone the workflow designer
git clone [this-repo]
cd agentic-coding

# 2. Open in Claude Code
claude-code .

# 3. Start the design process
"Help me set up Claude Code agents for my project"

# 4. The designer will:
# - Check for existing code or ask about new project
# - Ask clarifying questions  
# - Select optimal agents
# - Generate workflows
# - Create configuration

# 5. Find your configuration in .claude-output/
ls .claude-output/
```

### Option 2: Template-Based Setup (Fastest!)
```bash
# 1. Copy and fill out the template
cp PROJECT_REQUIREMENTS_TEMPLATE.md my-requirements.md
# Edit my-requirements.md with your project details

# 2. Open in Claude Code
claude-code .

# 3. Share your requirements
"Here's my project requirements: [paste template contents]"

# 4. Get instant configuration
# The designer will parse your template and generate everything immediately

# 5. Find your configuration in .claude-output/
ls .claude-output/
```

## 🤖 What Gets Generated

The workflow designer creates a complete Claude Code configuration:

```
.claude-output/
├── project.yaml          # Main configuration file
├── agents/               # Selected agent definitions
│   ├── orchestrator.md   # Always included
│   ├── [selected].md     # Agents chosen for your project
├── workflows/            # Custom workflows
│   ├── feature-development.yaml
│   ├── bug-fix.yaml
│   └── [custom].yaml
├── SETUP.md             # Installation instructions
├── AGENTS_RATIONALE.md  # Why these agents were chosen
└── README.md            # Project-specific guide
```

## 💡 Example Interactions

### Using the Requirements Template (Recommended)
```
You: "I've filled out the requirements template for my SaaS project: 
[pastes filled template with React, Node.js, PostgreSQL, Auth, Payments, etc.]"

Designer: "Perfect! I've parsed your requirements template. Based on your specifications:
- Full-stack web application
- React/Redux frontend with TailwindCSS
- Node.js/Express backend with REST API
- PostgreSQL + Redis
- Features: Auth, Stripe payments, real-time chat
- 80% test coverage requirement

I'll configure these agents:
- orchestrator (workflow coordination)
- frontend-engineer (React/Redux specialist)
- backend-engineer (Node.js/Express expert)
- database-architect (PostgreSQL/Redis optimization)
- qa-expert (Jest/Playwright testing)
- security-reviewer (auth & payment security)
- websocket-engineer (real-time features)

Generating your complete configuration in .claude-output/..."
```

### Starting a Brand New Project (Interactive)

```
You: "I need to set up Claude Code for a new project"

Designer: "I see we're starting a new project! Let's design the perfect setup for your needs.

Let's plan your project:

1. What type of application are you building?
   - Web application (full-stack)
   - API service (backend only)
   - Frontend application (SPA)
   - Mobile application
   - Other?

2. What technology stack do you want to use? (or I can recommend)
   - Frontend: React/Vue/Angular/Next.js?
   - Backend: Node.js/Python/Go/Java?
   - Database: PostgreSQL/MySQL/MongoDB?

3. What features will you need?
   - User authentication?
   - Real-time updates?
   - Payment processing?
   - File uploads?

4. What are your quality requirements?
   - Basic (just get it working)
   - Standard (testing + linting)
   - Strict (full testing + security + performance)

5. Team size?

You: "Web app, React + Node.js + PostgreSQL, needs auth and payments, standard quality, small team"

Designer: "Perfect! For your full-stack web application, I'll configure:

Selected Agents:
- orchestrator (workflow coordination)
- frontend-engineer (React development)
- backend-engineer (Node.js APIs)
- database-architect (PostgreSQL design)
- qa-expert (testing strategy)
- security-reviewer (auth & payments security)

I'll also create optimized workflows for parallel frontend/backend development.

Generating your configuration in .claude-output/..."
```

### Analyzing an Existing Project

```
You: "Configure Claude Code for my existing codebase"

Designer: "I'll analyze your existing codebase and create an optimal configuration.

Scanning project structure...

Found:
- Python Django backend with REST API
- Vue.js frontend with Vuex
- PostgreSQL database
- Docker configuration
- pytest and cypress tests

I'll create a configuration with:
- backend-engineer (Python/Django specialist)
- frontend-engineer (Vue.js specialist)  
- database-architect (PostgreSQL)
- qa-expert (pytest/cypress)
- ci-cd-engineer (Docker deployment)

Generating configuration in .claude-output/..."
```

## 📚 Documentation

- **[Project Requirements Template](PROJECT_REQUIREMENTS_TEMPLATE.md)** - Fill this out for instant setup
- **[Agent Catalog](claude-code-agents-catalog.md)** - Complete list of available agents
- **[Workflow Design Patterns](agentic-workflow-design.md)** - Architecture and patterns
- **[Research Document](agent-coding-research.md)** - Academic research foundation
- **[Implementation Plan](agentic-workflow-implementation-plan.md)** - Future enhancements

## 🎨 How the Designer Works

### 1. Input Detection
The workflow designer checks what information you've provided:
- **Template Provided**: Parses your filled template and generates immediately
- **Existing Project**: Analyzes codebase first, then clarifies requirements
- **New Project**: Jumps to interactive requirements gathering

### 2. Requirements Processing
Through a conversational interface, it gathers:
- Application type and purpose
- Team size and structure
- Quality standards
- Performance requirements
- Deployment targets

### 3. Intelligent Agent Selection
Based on analysis and requirements, it:
- Matches agents to your technology stack
- Considers team size and workflow preferences
- Balances coverage with efficiency
- Explains each selection with rationale

### 4. Workflow Generation
Creates optimized workflows that:
- Maximize parallel execution
- Include appropriate quality gates
- Handle errors gracefully
- Scale with your team

## 🔧 Customizing the Designer

### Adding New Agent Sources

Edit `.claude/agents/workflow-designer.md` to include new agent repositories or custom agents.

### Modifying Selection Criteria

Update the agent selection matrix in the workflow designer to match your organization's standards.

### Creating Templates

Add workflow templates in `.claude/workflows/` for common project types in your organization.

## 📊 Supported Project Types

The designer can configure Claude Code for:

- **Web Applications** (React, Vue, Angular)
- **APIs** (REST, GraphQL)
- **Mobile Apps** (React Native, Flutter)
- **Microservices** (Docker, Kubernetes)
- **CLI Tools** (Node.js, Python, Go)
- **Libraries** (NPM packages, Python modules)
- **Data Science** (Jupyter, Python, R)
- **DevOps** (Infrastructure as Code)

## 🎯 Agent Selection Philosophy

The designer follows these principles:

1. **Minimal Viable Team** - Start with essential agents only
2. **Technology Alignment** - Match agents to your exact stack
3. **Progressive Enhancement** - Easy to add agents as you grow
4. **Parallel Optimization** - Maximize concurrent execution
5. **Quality First** - Include testing and review by default

## 🚦 Workflow Patterns

Generated workflows follow proven patterns:

### Sequential Development
```
Requirements → Design → Implement → Test → Deploy
```

### Parallel Execution
```
Frontend ─┐
Backend  ─┼→ Integration → Testing → Deployment
Database ─┘
```

### Hierarchical Decomposition
```
Feature → Components → Tasks → Subtasks
```

## 📈 Benefits

Using the workflow designer provides:

- **5-10x faster setup** compared to manual configuration
- **Optimal agent selection** based on your specific needs
- **Best practice workflows** from day one
- **Clear documentation** of choices and rationale
- **Easy customization** with generated templates

## 🔄 Iterating Your Configuration

As your project evolves:

1. **Re-run the designer** with updated requirements
2. **Merge new agents** into existing configuration
3. **Evolve workflows** based on team feedback
4. **Share improvements** with the community

## 💬 Example Commands After Setup

Once your configuration is installed:

```bash
# Feature Development
"Implement user authentication with OAuth"

# Bug Fixing
"Fix the checkout process timeout issue"

# Performance
"Optimize the dashboard loading time"

# Testing
"Add integration tests for the payment flow"

# Documentation
"Generate API documentation"
```

The orchestrator and specialized agents will handle everything!

## 🤝 Contributing

Help improve the workflow designer:

1. **Add project templates** for new frameworks
2. **Improve agent selection** logic
3. **Share workflow patterns** that work well
4. **Report issues** and edge cases

## 🎓 Learning Resources

- [Claude Code Documentation](https://docs.anthropic.com/en/docs/claude-code)
- [Sub-Agents Guide](https://docs.anthropic.com/en/docs/claude-code/sub-agents)
- [VoltAgent Repository](https://github.com/VoltAgent/awesome-claude-code-subagents)

## ⚡ Quick Reference

### Fastest Setup (with Template)
```bash
# 1. Fill out template
cp PROJECT_REQUIREMENTS_TEMPLATE.md my-project.md
# Edit my-project.md

# 2. Share with designer
"Here's my requirements: [paste]"
```

### Interactive Setup
```
"Set up Claude Code for my project"
```

### View Generated Config
```
ls .claude-output/
```

### Install Configuration
```bash
cp -r .claude-output/* /your/project/.claude/
```

### Restart Claude Code
Close and reopen to load new configuration

### Verify Setup
```
"List available agents"
```
