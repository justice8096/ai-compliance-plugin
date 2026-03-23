# Setup Instructions

This plugin requires copying large source files from the original LLMComplianceSkill project.

## Prerequisites

- Node.js 16+ (for auto-fill and validation tools)
- Original LLMComplianceSkill project available at: `D:\LLMComplianceSkill\`

## Setup Steps

### 1. Copy Source Files

Copy these directories from LLMComplianceSkill into the plugin:

```bash
# From D:\LLMComplianceSkill\ to ai-compliance-plugin\

cp -r D:\LLMComplianceSkill\tools\               ai-compliance-plugin\tools\
cp -r D:\LLMComplianceSkill\templates\           ai-compliance-plugin\templates\
cp -r D:\LLMComplianceSkill\knowledge\           ai-compliance-plugin\knowledge\
```

This copies:
- `tools/` — Auto-fill engine, evidence checker, interactive assessments, data files
- `templates/` — 22 evidence template files (markdown)
- `knowledge/` — Regulation files (AI-Regulations-*.md) and interactive world map

### 2. Verify Installation

After copying, your plugin structure should be:

```
ai-compliance-plugin/
├── plugin.json
├── README.md
├── SETUP.md
├── LICENSE
├── skills/
│   └── ai-compliance/
│       └── SKILL.md
├── commands/
│   ├── extract-evidence.md
│   ├── check-compliance.md
│   └── fill-templates.md
├── tools/
│   ├── autofill.js
│   ├── evidence-checker.js
│   ├── interactive/
│   │   ├── risk-classification.html
│   │   ├── pia-assessment.html
│   │   ├── bias-testing.html
│   │   └── ... (19 tools)
│   ├── data/
│   │   ├── jurisdiction-matrix.json
│   │   ├── deadline-data.json
│   │   └── llm-registry.json
│   └── compliance-config.json
├── templates/
│   ├── 01-transparency-documentation.md
│   ├── 02-user-facing-disclosures.md
│   └── ... (22 templates)
├── knowledge/
│   ├── AI-Regulations-Global-Overview.md
│   ├── AI-Regulations-EU.md
│   └── ... (11 regional guides)
└── output/
    └── (generated after first run)
```

### 3. Configure for Your Project

Edit `tools/compliance-config.json` with:
- System details (name, type, foundation model)
- Organization info (company name, location)
- Target jurisdictions and risk level
- Sector (healthcare, finance, etc.)

### 4. Run a Test

Test the auto-fill engine:

```bash
node tools/autofill.js --config tools/compliance-config.json --output output/
```

Check the generated templates in `output/`.

## Troubleshooting

**Error: Cannot find module 'fs'**
- Ensure Node.js is installed: `node --version`

**Templates directory not found**
- Verify you copied `templates/` from LLMComplianceSkill

**Knowledge base files missing**
- Ensure `knowledge/` directory was copied with all AI-Regulations-*.md files

**Interactive tools not loading**
- Open tools in a modern browser (Chrome, Firefox, Safari, Edge)
- Tools require JavaScript enabled

## Next Steps

1. Run the full extraction pipeline: `extract-evidence`
2. Open interactive assessments in `tools/interactive/`
3. Generate evidence: `node tools/autofill.js`
4. Validate: `check-compliance --verbose`
5. Review `output/` folder with your legal team

## License

MIT License. Copyright (c) 2026 Justice.
