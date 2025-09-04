# Agent Setup

## Overview

Agent Setup is a comprehensive collection of specialized AI agent configurations and design workflows for Claude Code. This repository provides pre-configured agents for common development tasks including architecture design, documentation generation, product management, prompt optimization, and research, along with automated design review workflows for maintaining UI/UX quality.

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

### Usage

Agents are invoked directly in Claude Code using their configured names:

```bash
# Example agent invocations
@architect      # Create technical specifications from PRDs
@documenter     # Generate comprehensive project documentation
@product-manager # Create Product Requirements Documents
@prompt-improver # Optimize AI prompts following best practices
@research-specialist # Research technical solutions and documentation
```

## Project Structure

```
agent-setup/
├── .mcp.json                    # MCP server configuration
├── architect.md                 # Technical specification agent
├── cursor-rule.md              # Development guidelines
├── documenter.md               # Documentation generation agent
├── product-manager.md          # PRD creation agent
├── prompt-improver.md          # Prompt optimization agent
├── research-specialist.md      # Technical research agent
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

### Architect Agent (`architect.md`)
**Purpose:** Creates detailed technical specifications from Product Requirements Documents (PRDs)
- Transforms PRDs into implementation-ready technical blueprints
- Supports both single comprehensive specs and multi-role specifications
- Includes complete API definitions, database schemas, and testing strategies
- Maintains cross-specification coordination for complex features

### Documenter Agent (`documenter.md`)
**Purpose:** Generates comprehensive technical documentation through codebase analysis
- Reverse-engineers project structure and technology stack
- Creates detailed README files with setup instructions and API documentation
- Extracts functionality from actual code without placeholder content
- Supports multiple project types and architectural patterns

### Product Manager Agent (`product-manager.md`)
**Purpose:** Creates comprehensive Product Requirements Documents from user ideas
- Structured requirements gathering with validated user feedback
- Complete PRD generation with user flows and acceptance criteria
- Integration with existing systems analysis
- Maintains PRD index for conflict detection and organization

### Prompt Improver Agent (`prompt-improver.md`)
**Purpose:** Optimizes AI prompts following established best practices
- Minimal XML tagging approach for maximum clarity
- Structured templates for complex use cases
- Measurable requirements and quality standards
- Support for various prompt types (technical, analysis, creative)

### Research Specialist Agent (`research-specialist.md`)
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
- Store PRDs in `prds/` folder with descriptive kebab-case filenames
- Maintain `prds/index.md` for PRD organization and conflict detection
- Store technical specifications in `specs/` folder
- Use consistent naming conventions across documentation

## Development Workflow

The repository supports an AI-native development approach:

1. **Requirements Gathering:** Use `@product-manager` to create comprehensive PRDs
2. **Technical Planning:** Use `@architect` to generate implementation specifications
3. **Research Phase:** Use `@research-specialist` for technical challenge resolution
4. **Implementation:** Follow specifications with design review integration
5. **Documentation:** Use `@documenter` to generate comprehensive project documentation

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