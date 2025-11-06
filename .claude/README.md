# Claude Code Skills - Complete Package

This package contains 12 custom Agent Skills for Claude Code Web.

## Skills Included

### Content & Marketing Skills

**1. content-intent-agent**
- 34 verification modules for content optimization
- 16-part conversion scoring system
- Veto power over non-compliant content
- LLM/conversational search optimization

**2. internal-comms**
- Write internal communications using company formats
- Status reports, leadership updates, newsletters, FAQs

**3. slack-gif-creator**
- Create custom GIFs for Slack messages
- Animated reactions and responses

### Development & Technical Skills

**4. mcp-builder**
- Create Model Context Protocol (MCP) servers
- Python (FastMCP) and Node/TypeScript support
- Integrate external APIs and services

**5. skill-creator**
- Create new custom Agent Skills
- Interactive guidance and templates
- Best practices for skill authoring

### Design & Visual Skills

**6. algorithmic-art**
- Create algorithmic art using p5.js
- Seeded randomness and interactive parameters
- Flow fields, particle systems, generative patterns

**7. artifacts-builder**
- Build elaborate multi-component HTML artifacts
- React, Tailwind CSS, shadcn/ui support
- State management and routing

**8. canvas-design**
- Create beautiful visual art in PNG/PDF
- Posters, designs, static pieces
- Original design philosophy

**9. theme-factory**
- Style artifacts with themes
- 10 pre-set themes with colors/fonts
- Apply to slides, docs, reports, landing pages

**10. brand-guidelines**
- Apply Anthropic's brand colors and typography
- Consistent visual formatting
- Company design standards

### Project Management Skills

**11. llm-rankings**
- Comprehensive LLM model evaluation and ranking
- Benchmark-based comparisons
- Task-specific recommendations
- Cost-effectiveness analysis

**12. pm-orchestrator-website**
- Website project coordination
- 7-phase mandatory workflow
- Quality gate enforcement
- WCAG AAA accessibility compliance
- Mobile-first responsive design

## Installation Instructions

### For Claude Code Web (GitHub Projects)

1. Navigate to your repository root:
   ```bash
   cd /path/to/your-repo
   ```

2. Extract this package:
   ```bash
   unzip claude-skills-complete-package.zip
   ```

3. Commit to GitHub:
   ```bash
   git add .claude/
   git commit -m "Add Claude Code Skills - complete package (12 skills)"
   git push
   ```

4. Restart Claude Code Web session connected to the repo

### For Claude Code CLI (Local)

1. Extract to user-level skills directory:
   ```bash
   unzip claude-skills-complete-package.zip -d ~/.claude/
   ```

2. Skills are immediately available to all projects

## How Skills Work

- Skills are automatically discovered when in `.claude/skills/` directory
- Claude loads them on-demand when relevant to your request
- Each skill has a SKILL.md file with instructions and optional resources

## Testing Skills

Ask Claude:
- "What skills are available?"
- "Compare Claude vs GPT-4" (triggers llm-rankings)
- "Create a poster design" (triggers canvas-design)
- "Build an MCP server" (triggers mcp-builder)
- "Plan a website redesign" (triggers pm-orchestrator-website)

## Documentation

- [Agent Skills Overview](https://docs.anthropic.com/en/docs/agents-and-tools/agent-skills/overview)
- [Skills in Claude Code](https://docs.anthropic.com/en/docs/claude-code/skills)
- [Skills Cookbook](https://github.com/anthropics/claude-cookbooks/tree/main/skills)
