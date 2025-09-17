# Agent Setup

## Overview

Agent Setup is a comprehensive collection of specialized AI agent configurations and design workflows for Claude Code. This repository provides pre-configured agents organized by system integration (Linear, Asana, Local) for common development tasks including architecture design, documentation generation, product management, prompt optimization, and research, along with automated design review workflows for maintaining UI/UX quality.

## Technology Stack

### Core Technologies
- **Platform:** Claude Code MCP (Model Context Protocol) server configuration
- **Format:** Markdown-based agent definitions with YAML frontmatter

### Supported Integrations
- **MCP Servers:** Linear, Atlassian, Playwright, GitHub, Context7, shadcn-ui
- **Tools Integration:** Browser automation via Playwright MCP

## Getting Started

### Prerequisites
- Claude Code installed and configured
- Access to supported MCP servers (optional for enhanced functionality)

### Installation

Copy whatever agent you need into your local agents or user-space agents. Follow the [official instructions](https://docs.anthropic.com/en/docs/claude-code/sub-agents)

### Configuration

The repository includes a `.mcp.json` configuration file that provides enhanced integrations:

| MCP Server | Type | Purpose |
|------------|------|---------|
| `linear` | SSE | Project management integration |
| `atlassian` | SSE | Atlassian tools integration |
| `playwright` | Command | Browser automation for design testing |
| `github` | HTTP | GitHub API integration |
| `context7` | SSE | Documentation and technical resources |
| `shadcn-ui` | Command | UI component management |

**Note:** API keys and authentication tokens need to be configured separately for each MCP server.

## System Organization

Agents are organized by system integration to provide specialized workflows that match your team's preferred tools:

### Linear Integration (`linear/`)
- **Target Users:** Teams using Linear for project management and issue tracking
- **Key Features:** Direct integration with Linear issues, automatic linking, and Linear-specific workflows
- **Use Cases:** Creating PRDs and technical specs that automatically sync with Linear issues

### Asana Integration (`asana/`) - Coming Soon
- **Target Users:** Teams using Asana for project management
- **Key Features:** Asana task integration, project templates, and Asana-specific workflows
- **Use Cases:** PRD and specification creation with Asana project alignment

### Local Integration (`local/`)
- **Target Users:** Teams preferring local development without external project management tools
- **Key Features:** File-based organization, chronological naming with YYYY-MM prefixes, markdown-based workflows
- **File Structure:** PRDs stored in `prds/` folder, implementation tasks in `tasks/[prd-name]/` folders
- **Use Cases:** Self-contained development workflows for smaller teams or personal projects

### Usage

Agents are invoked directly in Claude Code using their configured names:

```bash
# Example agent invocations

# Linear-integrated agents
@linear/architect      # Create technical specifications from PRDs (Linear integration)
@linear/product-manager # Create Product Requirements Documents (Linear integration)

# General-purpose agents
@documenter     # Generate comprehensive project documentation
@prompt-improver # Optimize AI prompts following best practices
@research-specialist # Research technical solutions and documentation

# Local system agents (file-based workflow)
@local/architect      # Local file system architecture agent
@local/product-manager # Local file system product management agent

# Future integrations (coming soon)
# @asana/architect     # Asana-integrated architecture agent
# @asana/product-manager # Asana-integrated product management agent
```

## Project Structure

```
agent-setup/
├── .mcp.json                    # MCP server configuration
├── cursor-rule.md              # Development guidelines
├── documenter.md               # Documentation generation agent
├── prompt-improver.md          # Prompt optimization agent
├── research-specialist.md      # Technical research agent
├── linear/                     # Linear-integrated agents
│   ├── architect.md            # Technical specification agent (Linear integration)
│   └── product-manager.md      # PRD creation agent (Linear integration)
├── local/                      # Local file system agents
│   ├── architect.md            # Technical specification agent (file system)
│   └── product-manager.md      # PRD creation agent (file system)
├── asana/                      # Asana-integrated agents (coming soon)
└── design-workflows/           # Automated design review workflows
    ├── LICENSE                # Workflow license
    ├── README.md              # Workflow overview
    └── design-review/         # Design review templates and examples
        ├── README.md
        ├── design-principles-example.md
        ├── design-review-agent.md
        ├── design-review-claude-md-snippet.md
        └── design-review-slash-command.md
```

## Core Agents

### System-Integrated Agents

#### Linear Integration

##### Architect Agent (`linear/architect.md`)
**Purpose:** Creates detailed technical specifications from Product Requirements Documents (PRDs) with Linear integration
- Transforms PRDs into implementation-ready technical blueprints
- Supports both single comprehensive specs and multi-role specifications
- Includes complete API definitions, database schemas, and testing strategies
- Maintains cross-specification coordination for complex features
- Integrates with Linear for issue tracking and project management

##### Product Manager Agent (`linear/product-manager.md`)
**Purpose:** Creates comprehensive Product Requirements Documents from user ideas with Linear integration
- Structured requirements gathering with validated user feedback
- Complete PRD generation with user flows and acceptance criteria
- Integration with existing systems analysis
- Maintains PRD index for conflict detection and organization
- Seamless Linear integration for issue creation and tracking

#### Local Integration

##### Architect Agent (`local/architect.md`)
**Purpose:** Creates detailed technical specifications based on PRDs with local file system organization
- Transforms PRDs into implementation-ready task files stored in `tasks/[prd-name]/` folders
- Uses natural file naming and category-based organization for clarity
- Includes complete technical specifications with cross-file coordination
- Maintains traceability through file references and markdown links
- No external dependencies - works entirely with local file system

##### Product Manager Agent (`local/product-manager.md`)
**Purpose:** Creates comprehensive Product Requirements Documents using local file system storage
- Structured requirements gathering with YYYY-MM chronological naming
- Complete PRD generation stored as markdown files in `prds/` folder
- File-based state persistence through Agent Session Log embedded in documents
- Easy discovery and organization through consistent file naming conventions
- Seamless handoff to architect agent through file system references

#### Future Integrations
- **Asana Integration:** Similar architecture and product management agents optimized for Asana workflows

### General-Purpose Agents

#### Documenter Agent (`documenter.md`)
**Purpose:** Generates comprehensive technical documentation through codebase analysis
- Reverse-engineers project structure and technology stack
- Creates detailed README files with setup instructions and API documentation
- Extracts functionality from actual code without placeholder content
- Supports multiple project types and architectural patterns

#### Prompt Improver Agent (`prompt-improver.md`)
**Purpose:** Optimizes AI prompts following established best practices
- Minimal XML tagging approach for maximum clarity
- Structured templates for complex use cases
- Measurable requirements and quality standards
- Support for various prompt types (technical, analysis, creative)

#### Research Specialist Agent (`research-specialist.md`)
**Purpose:** Finds current solutions for non-trivial technical challenges
- Prioritizes Context7 MCP and GitHub MCP for latest documentation
- Curates actionable examples over theoretical explanations
- Quality assessment based on recency and reliability
- Structured output with prioritized solutions and key insights

## Design Workflows

### Automated Design Review System
The repository includes a comprehensive design review workflow that provides automated feedback on frontend code changes:

**Features:**
- **Live Environment Testing:** Uses Playwright MCP for real-time UI component interaction
- **Standards-Based Evaluation:** Follows design principles from top-tier companies
- **Multi-Phase Review Process:** Covers interaction flows, responsiveness, accessibility, and code health
- **Claude Code Integration:** Slash commands and subagent configurations

**Components:**
- Design review agent configuration for automated assessments
- CLAUDE.md integration snippets for project-specific design guidelines
- Slash command implementations for on-demand reviews
- Example design principles documents

**Usage:**
```bash
# Use specialized design review agent
@design-review
```

## Configuration Guidelines

### Project Integration
1. **CLAUDE.md Setup:** The `cursor-rule.md` specifies reading CLAUDE.md files for project-specific context
2. **Agent Customization:** Modify agent descriptions and instructions for project-specific needs
3. **MCP Integration:** Configure relevant MCP servers based on your development stack

### Best Practices

#### For Linear Integration
- Use Linear projects as primary PRD containers
- Maintain clear project-to-issues relationships
- Apply consistent labeling per project CLAUDE.md guidelines

#### For Local Integration
- Store PRDs in `prds/` folder with YYYY-MM-descriptive-name.md format
- Store technical specifications in `tasks/[prd-name]/` folders
- Use natural file naming for tasks (e.g., `backend_auth_api.md`)
- Maintain cross-references between PRD and task files for traceability

#### General
- Use consistent naming conventions across documentation
- Maintain CLAUDE.md files for project-specific guidelines

## Development Workflow

The repository supports an AI-native development approach:

1. **Requirements Gathering:** Use your preferred system integration to create comprehensive PRDs:
   - `@linear/product-manager` for Linear-integrated workflows
   - `@local/product-manager` for local file-based workflows
2. **Technical Planning:** Use your preferred system integration to generate implementation specifications:
   - `@linear/architect` for Linear-integrated workflows
   - `@local/architect` for local file-based workflows
3. **Research Phase:** Use `@research-specialist` for technical challenge resolution
4. **Implementation:** Follow specifications with design review integration
5. **Documentation:** Use `@documenter` to generate comprehensive project documentation

**System Selection:** Choose the appropriate system integration based on your project's workflow requirements:
- **Linear:** For teams using Linear project management
- **Local:** For teams preferring file-based workflows without external dependencies
- **Asana:** Coming soon for teams using Asana project management

## Success Metrics

**Technical Quality:**
- Complete specifications enable immediate implementation without additional research
- All requirements are traceable back to validated user needs
- Testing strategies are comprehensive and executable
- Documentation accurately reflects actual system functionality

**Process Efficiency:**
- Reduced time from idea to implementation-ready specification
- Consistent quality across different team members and projects
- Automated design quality assurance
- Streamlined research and documentation processes