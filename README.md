# 🚀 Claude Code Workflow Generator

An intelligent agent configuration system for Claude Code projects. Simply describe your project to Claude, and it will automatically select the optimal combination of agents from a library of 134 specialized configurations, creating a complete, portable setup tailored to your specific needs.

## ✨ Key Features

- **134 Real Agent Configurations** - Pre-extracted from VoltAgent repository
- **Automatic Setup** - Claude is pre-configured as a workflow generator when you open this repo
- **Intelligent Agent Selection** - Claude analyzes your project and picks the perfect agents
- **Complete Agent Catalog** - Full descriptions for informed agent selection
- **Zero Dependencies** - No scripts or external tools required
- **Fully Portable** - Generated `.claude` folders work immediately
- **Adaptive Configuration** - Tailored to your exact technology stack and requirements

## 📁 Project Structure

```
agentic-coding/
├── agents/                          # 134 agent configurations with full specs
│   ├── orchestrator.md             # Workflow coordinator (always included)
│   ├── frontend-developer.md       # Frontend specialist
│   ├── backend-developer.md        # Backend specialist
│   └── [131 more agents]           # Complete agent library
│
├── .claude-output/                  # Generated configurations (git-ignored)
│   └── .claude/                    # Portable Claude configuration
│       ├── agents/                 # Selected agents for your project
│       ├── workflows/              # Workflow definitions
│       ├── config/                 # Settings and configuration
│       ├── project.yaml            # Main configuration
│       └── CLAUDE.md              # Project-specific instructions
│
├── design/                          # Design documents and research
│   ├── agent-coding-research.md
│   ├── agentic-workflow-design.md
│   └── [other design docs]
│
├── .claude/                         # Claude Code configuration (auto-loaded)
│   ├── CLAUDE.md                    # Workflow generator instructions
│   └── ...                          # Additional Claude settings
│
├── AGENT-CATALOG.md                # Complete agent reference (134 agents)
└── PROJECT_REQUIREMENTS_TEMPLATE.md # Template for requirements
```

## 🎯 Quick Start

### 1️⃣ Clone and Setup

```bash
# Clone the repository
git clone https://github.com/[your-org]/agentic-coding
cd agentic-coding

# Agents are pre-extracted and ready to use!
# 134 agents available in /agents directory
```

### 2️⃣ Open in Claude Code

```bash
# Open this repository in Claude Code
claude .

# Claude is automatically configured as a workflow generator!
# The .claude/CLAUDE.md instructions are loaded on startup
```

### 3️⃣ Describe Your Project

Simply tell Claude about your project:

```
"I'm building a SaaS application with React frontend, Node.js backend, PostgreSQL database, and Stripe payments"
```

Or for existing projects:

```
"Configure Claude agents for my Python data science project that uses pandas and scikit-learn"
```

### 4️⃣ Claude Generates Configuration

Claude will:
- Analyze your requirements
- Intelligently select the right agents from 134 available
- Generate complete configuration in `.claude-output/`
- Provide setup instructions

### 5️⃣ Install in Your Project

```bash
# Copy the generated configuration to your project
cp -r .claude-output/.claude /path/to/your/project/

# Open your project with Claude Code
cd /path/to/your/project
claude .
```

## 📋 Example Agent Configurations

Claude intelligently selects agents based on your project. Here are some examples:

### Full-Stack Web Application
When you describe a React + Node.js + PostgreSQL project, Claude might select:
- `orchestrator` - Workflow coordination
- `react-specialist` - React development
- `javascript-pro` - Node.js backend
- `database-administrator` - PostgreSQL optimization
- `api-designer` - REST API design
- `qa-expert` - Testing strategy
- `devops-engineer` - Deployment
- `security-auditor` - Security review

### Machine Learning Pipeline
For a fraud detection ML project, Claude might choose:
- `orchestrator` - Workflow management
- `data-scientist` - Model development
- `ml-engineer` - Pipeline implementation
- `python-pro` - Python expertise
- `data-engineer` - ETL processes
- `mlops-engineer` - Model deployment
- `performance-engineer` - Optimization
- `security-auditor` - Data protection

### Mobile Application
For a React Native e-commerce app, Claude might select:
- `orchestrator` - Development coordination
- `react-native-developer` - Mobile UI
- `mobile-developer` - Platform integration
- `backend-developer` - API services
- `payment-integration` - Checkout flow
- `qa-expert` - Mobile testing
- `ux-designer` - User experience

## 📖 Agent Catalog

See **[AGENT-CATALOG.md](AGENT-CATALOG.md)** for the complete list of 134 available agents with full descriptions, organized by category:

- 🛠️ Core Development (11 agents)
- 💻 Language & Framework Specialists (24 agents)
- 🏗️ Infrastructure & DevOps (12 agents)
- 🔒 Quality, Security & Testing (13 agents)
- 🤖 Data, AI & Machine Learning (13 agents)
- 🎯 Specialized Domains (11 agents)
- 📊 Business, Product & Management (14 agents)
- 🔧 Developer Experience & Tools (11 agents)
- 🔄 Meta-Orchestration & Coordination (9 agents)

## 🛠️ Advanced Usage

### Specific Agent Requests

You can ask Claude for specific agents:

```
"I need a configuration with rust-engineer, blockchain-developer, and security-auditor agents"
```

### Adding Requirements

Be specific about your needs:

```
"Create a configuration for a high-traffic e-commerce platform with React frontend, 
Node.js microservices, Kubernetes deployment, and strict security requirements"
```

### Reviewing Agent Selection

After generation, you can ask:

```
"Why did you choose these agents? Can you add a payment-integration specialist?"
```

### Using the Requirements Template

For complex projects, use the template for comprehensive configuration:

```bash
# 1. Copy and fill out the template
cp PROJECT_REQUIREMENTS_TEMPLATE.md my-requirements.md
# Edit my-requirements.md with your project details

# 2. Share with Claude:
"Here's my project requirements: [paste template contents]"
```

Claude will parse your detailed requirements and create a precise configuration.


## 📊 What Gets Generated

### Complete .claude Structure
- **project.yaml** - Main configuration with agent list
- **agents/*.md** - Selected agent definitions
- **workflows/*.yaml** - Workflow patterns (main, feature, bugfix, testing)
- **CLAUDE.md** - Project-specific instructions
- **config/settings.json** - Feature toggles and settings

### Installation Scripts
- **setup.sh** - One-command installer for your project
- **validate.sh** - Configuration validator

## ✅ Validation

After Claude generates your configuration, review it:

```bash
# Check what was generated
ls -la .claude-output/.claude/

# View selected agents
ls .claude-output/.claude/agents/

# Review the configuration
cat .claude-output/.claude/project.yaml
```

Claude will ensure all necessary files are created and properly configured.

## 🎓 Why Use This Tool?

1. **Intelligent Agent Selection** - Claude analyzes your needs and picks optimal agents
2. **Adaptive Configuration** - Tailored specifically to your project, not generic templates
3. **Best Practice Workflows** - Industry-standard patterns built-in
4. **Zero Setup Time** - No manual configuration or script running
5. **Fully Portable** - Share configurations with your team
6. **Version Control Ready** - Check everything into git
7. **No External Dependencies** - Works offline after setup

## 🔍 How It Works

1. **Project Analysis**: Claude understands your requirements through natural conversation
2. **Intelligent Matching**: Analyzes your tech stack, scale, and needs against 134 agents
3. **Smart Selection**: Picks optimal agents considering dependencies and interactions
4. **Configuration Generation**: Creates complete `.claude` structure with workflows
5. **Portable Output**: Self-contained configuration ready to copy to any project

## 🐛 Troubleshooting

### No agents found
```bash
# Verify agents directory exists
ls agents/ | wc -l  # Should show 134
```

### Configuration not generated
```
"Please generate the workflow configuration for my project"
```

### Missing specific technology
```
"Can you add agents for GraphQL and Redis to my configuration?"
```

### Want different agents
```
"Replace the frontend-developer with react-specialist and vue-expert"
```

## 📚 Documentation

- **[AGENT-CATALOG.md](AGENT-CATALOG.md)** - Complete agent reference with descriptions
- **[PROJECT_REQUIREMENTS_TEMPLATE.md](PROJECT_REQUIREMENTS_TEMPLATE.md)** - Quick setup template
- **[design/](design/)** - Architecture and design documents

## 🤝 Contributing

1. **Add new agents** - Create properly formatted `.md` files in `/agents`
2. **Improve templates** - Enhance pre-configured project types
3. **Share workflows** - Add new workflow patterns
4. **Report issues** - Help us improve the tool

## 📝 License

MIT License - See LICENSE file for details

## 🚀 Get Started

Ready to configure your Claude Code project?

1. Open this repository in Claude Code: `claude .`
2. Describe your project: "I'm building a [your project type]"
3. Copy the generated configuration to your project
4. Start developing with your optimized multi-agent team!

Your personalized agent configuration will be ready in seconds!