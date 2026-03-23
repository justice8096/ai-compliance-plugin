# AI Compliance Plugin

## Purpose
Cowork plugin that packages the AI compliance evidence collection workflow: regulatory knowledge base, evidence extractors, interactive assessment tools, and template autofill pipeline.

## Tools & Stack
- **Cowork plugin format** (.plugin)
- **Node.js** for extractors and autofill
- **Browser** for interactive assessment tools

## Directory Structure
```
plugin.json              — Plugin manifest
skills/
  ai-compliance/
    SKILL.md             — Skill definition and instructions
commands/
  scan-repo.md           — Extract evidence from a git repository
  check-compliance.md    — Run compliance checker against config
  fill-templates.md      — Auto-fill evidence templates
```

## Commands
- `/scan-repo` — Run git, package, and CI extractors on a repository
- `/check-compliance` — Validate compliance-config.json completeness
- `/fill-templates` — Auto-fill 23 evidence templates from config

## Technical Notes
- References LLMComplianceSkill tools for heavy lifting
- Skill includes jurisdiction-specific guidance for 12 regions
- Interactive tools opened in browser via Windows-MCP
