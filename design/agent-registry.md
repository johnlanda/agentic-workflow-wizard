# Claude Code Agent Registry (Local)

All agent configurations are stored locally in the `/agents` directory. No external dependencies or Python required.

## How to Use

1. **First Time Setup**: Run `./fetch-all-agents.sh` to download all agents
2. **Generate Workflow**: Run `./generate-workflow-config.sh` and select project type
3. **Install**: Copy `.claude-output/.claude` to your project

## Available Agents

All agents are pre-downloaded and stored in `/agents/*.md`

### 🛠️ Development Agents
| Agent | File | Description |
|-------|------|-------------|
| api-designer | agents/api-designer.md | API specification and design |
| frontend-engineer | agents/frontend-engineer.md | Frontend development specialist |
| backend-engineer | agents/backend-engineer.md | Backend development specialist |
| fullstack-engineer | agents/fullstack-engineer.md | Full-stack development |
| mobile-developer | agents/mobile-developer.md | Mobile app development |
| game-developer | agents/game-developer.md | Game development specialist |

### 💻 Language Specialists
| Agent | File | Description |
|-------|------|-------------|
| python-pro | agents/python-pro.md | Python expert |
| javascript-pro | agents/javascript-pro.md | JavaScript specialist |
| typescript-pro | agents/typescript-pro.md | TypeScript expert |
| golang-pro | agents/golang-pro.md | Go language specialist |
| rust-pro | agents/rust-pro.md | Rust programming expert |
| java-pro | agents/java-pro.md | Java development |
| csharp-pro | agents/csharp-pro.md | C# and .NET specialist |
| cpp-pro | agents/cpp-pro.md | C++ programming |
| swift-pro | agents/swift-pro.md | Swift/iOS development |
| kotlin-pro | agents/kotlin-pro.md | Kotlin/Android development |
| ruby-pro | agents/ruby-pro.md | Ruby programming |
| php-pro | agents/php-pro.md | PHP development |
| nextjs-developer | agents/nextjs-developer.md | Next.js specialist |
| react-native-developer | agents/react-native-developer.md | React Native mobile |

### 🏗️ Infrastructure Agents
| Agent | File | Description |
|-------|------|-------------|
| devops-engineer | agents/devops-engineer.md | DevOps and CI/CD |
| cloud-architect | agents/cloud-architect.md | Cloud infrastructure design |
| database-administrator | agents/database-administrator.md | Database design and optimization |
| kubernetes-expert | agents/kubernetes-expert.md | Kubernetes orchestration |
| docker-specialist | agents/docker-specialist.md | Docker containerization |
| terraform-expert | agents/terraform-expert.md | Infrastructure as Code |
| aws-specialist | agents/aws-specialist.md | AWS cloud services |
| azure-specialist | agents/azure-specialist.md | Azure cloud platform |
| gcp-specialist | agents/gcp-specialist.md | Google Cloud Platform |

### 🔒 Quality & Security
| Agent | File | Description |
|-------|------|-------------|
| qa-expert | agents/qa-expert.md | Testing and quality assurance |
| security-reviewer | agents/security-reviewer.md | Security analysis and review |
| code-reviewer | agents/code-reviewer.md | Code quality review |
| performance-engineer | agents/performance-engineer.md | Performance optimization |
| accessibility-expert | agents/accessibility-expert.md | Accessibility compliance |
| penetration-tester | agents/penetration-tester.md | Security penetration testing |

### 🎯 Specialized Agents
| Agent | File | Description |
|-------|------|-------------|
| data-scientist | agents/data-scientist.md | Data science and analytics |
| ml-engineer | agents/ml-engineer.md | Machine learning engineering |
| blockchain-developer | agents/blockchain-developer.md | Blockchain development |
| iot-developer | agents/iot-developer.md | IoT device programming |
| ar-vr-developer | agents/ar-vr-developer.md | AR/VR development |
| documentation-writer | agents/documentation-writer.md | Technical documentation |
| ux-designer | agents/ux-designer.md | User experience design |
| product-manager | agents/product-manager.md | Product management |
| scrum-master | agents/scrum-master.md | Agile/Scrum facilitation |
| business-analyst | agents/business-analyst.md | Business analysis |

### ✍️ Creative Agents
| Agent | File | Description |
|-------|------|-------------|
| content-writer | agents/content-writer.md | Content creation |
| copywriter | agents/copywriter.md | Marketing copy |
| technical-writer | agents/technical-writer.md | Technical writing |
| video-editor | agents/video-editor.md | Video editing |
| graphic-designer | agents/graphic-designer.md | Graphic design |

### 🎭 Special Agent
| Agent | File | Description |
|-------|------|-------------|
| orchestrator | agents/orchestrator.md | Workflow coordination (always included) |

## Pre-configured Project Templates

Run `./generate-workflow-config.sh` and select:

### 1. Full-Stack Web Application
- frontend-engineer
- backend-engineer
- database-administrator
- api-designer
- qa-expert
- devops-engineer
- code-reviewer

### 2. Frontend Application
- frontend-engineer
- typescript-pro
- ux-designer
- qa-expert
- accessibility-expert
- code-reviewer

### 3. Backend API
- backend-engineer
- database-administrator
- api-designer
- qa-expert
- security-reviewer
- devops-engineer

### 4. Microservices
- backend-engineer
- devops-engineer
- kubernetes-expert
- docker-specialist
- api-designer
- database-administrator
- qa-expert

### 5. Mobile Application
- mobile-developer
- react-native-developer
- backend-engineer
- api-designer
- ux-designer
- qa-expert

### 6. Data Science
- data-scientist
- ml-engineer
- python-pro
- database-administrator
- documentation-writer

## Quick Start

```bash
# 1. Download all agents (one time only)
./fetch-all-agents.sh

# 2. Generate configuration for your project type
./generate-workflow-config.sh fullstack

# 3. Install in your project
bash .claude-output/setup.sh /path/to/your/project

# 4. Start using Claude Code
cd /path/to/your/project
claude .
```

## Custom Configuration

To create a custom agent selection:

1. Run `./generate-workflow-config.sh custom`
2. Manually copy desired agents from `/agents` to `.claude-output/.claude/agents/`
3. Update `.claude-output/.claude/project.yaml` with your agent list
4. Install as normal

## Advantages of Local Storage

✅ **No Python Required** - Pure bash scripts only
✅ **No Network Dependencies** - Agents cached locally  
✅ **Fast Generation** - Simple file copying
✅ **Version Control** - Check agents into git
✅ **Customizable** - Edit agents locally
✅ **Offline Work** - No internet needed after initial fetch

## Directory Structure

```
agentic-coding/
├── agents/                          # All agent definitions (50+ files)
│   ├── orchestrator.md             # Workflow coordinator
│   ├── frontend-engineer.md        # Frontend specialist
│   ├── backend-engineer.md         # Backend specialist
│   └── ...                         # All other agents
├── .claude-output/                  # Generated configuration
│   ├── .claude/                    # Ready to copy to project
│   │   ├── agents/                 # Selected agents
│   │   ├── workflows/              # Workflow definitions
│   │   ├── config/                 # Settings
│   │   ├── project.yaml           # Main config
│   │   └── CLAUDE.md              # Instructions
│   ├── setup.sh                    # Installation script
│   └── validate.sh                 # Validation script
├── fetch-all-agents.sh             # Download all agents
├── generate-workflow-config.sh      # Generate configuration
└── agent-registry.md               # This file
```

## Maintenance

To update agents from VoltAgent repository:

```bash
# Re-fetch all agents with latest versions
./fetch-all-agents.sh

# Your existing configurations remain unchanged
# Regenerate configs to use updated agents
```