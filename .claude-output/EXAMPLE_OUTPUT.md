# Example Output from Workflow Designer

This directory (`.claude-output/`) contains an example of what the workflow designer agent would generate for a typical full-stack web application project.

## Generated Structure

```
.claude-output/
├── project.yaml          # Main Claude Code configuration
├── agents/               # Selected agent configurations
│   ├── orchestrator.md
│   ├── frontend-engineer.md
│   ├── backend-engineer.md
│   ├── database-architect.md
│   └── qa-expert.md
├── workflows/            # Custom workflows
│   ├── feature-development.yaml
│   └── bug-fix.yaml
├── SETUP.md             # Installation instructions
├── AGENTS_RATIONALE.md # Explanation of agent selection
└── README.md            # Project-specific documentation
```

## How This Was Generated

1. **Project Analysis**: The workflow designer scanned the codebase and detected React, Node.js, and PostgreSQL

2. **Requirements Gathering**: Through interactive Q&A, determined:
   - Building a SaaS application
   - Team size: 3-5 developers
   - Quality requirements: Standard (80% test coverage)
   - Deployment: AWS

3. **Agent Selection**: Based on analysis, selected:
   - **orchestrator**: For coordination
   - **frontend-engineer**: For React development
   - **backend-engineer**: For Node.js APIs
   - **database-architect**: For PostgreSQL optimization
   - **qa-expert**: For testing requirements

4. **Workflow Generation**: Created workflows optimized for:
   - Parallel frontend/backend development
   - Integrated testing
   - Quality gates at each stage

## To Use This Configuration

1. Copy all contents to your project's `.claude/` directory
2. Restart Claude Code
3. The new configuration will be automatically loaded
4. Start using commands like "implement user authentication"

## Customization

You can modify any generated file to better suit your needs. The configuration is designed to be a starting point that can evolve with your project.