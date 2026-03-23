# AI Compliance Plugin

Comprehensive compliance evidence collection for AI and LLM applications. Generate regulatory documentation for EU AI Act, GDPR, and global AI regulations.

## What's Included

This plugin packages the **AI Compliance Evidence Collection Kit** with:

- **22 Evidence Templates** — Jurisdiction-specific compliance documentation
- **19 Interactive HTML Assessments** — Browser-based tools for risk classification, privacy impact assessment, bias testing, governance design, and more
- **Auto-fill Engine** — Populate templates from configuration and assessment results
- **Evidence Validator** — Check for completeness and compliance gaps
- **Global Regulation Database** — Jurisdiction-specific guidance for 11+ regions

## Quick Start

### 1. Installation

Copy the plugin into your Cowork plugins directory:

```bash
cp -r ai-compliance-plugin ~/.cowork/plugins/
```

Then run the setup to copy large source files from LLMComplianceSkill:

```bash
cd ~/.cowork/plugins/ai-compliance-plugin
bash SETUP.md
```

### 2. Configure Your Project

Edit `tools/compliance-config.json`:

```json
{
  "system": {
    "name": "My AI Application",
    "type": "LLM Chat",
    "foundationModel": "GPT-4"
  },
  "organization": {
    "name": "My Company",
    "country": "US"
  },
  "project": {
    "targetJurisdictions": ["EU", "US", "UK"],
    "riskLevel": "high",
    "sector": "healthcare"
  }
}
```

### 3. Run Assessments

Open the interactive HTML tools in your browser:

```bash
# Risk classification for EU AI Act
open tools/interactive/risk-classification.html

# Privacy impact assessment
open tools/interactive/pia-assessment.html

# Bias testing and fairness
open tools/interactive/bias-testing.html

# ... and more (19 tools total)
```

Tools save results directly back to your config file.

### 4. Generate Evidence

Auto-fill all templates:

```bash
extract-evidence
```

This generates filled templates in `output/` ready for legal review.

### 5. Validate

Check for completeness and compliance gaps:

```bash
check-compliance --verbose
```

## Commands

- **`extract-evidence`** — Run the complete pipeline (configure → assess → auto-fill → validate)
- **`check-compliance`** — Validate evidence for completeness and gaps
- **`fill-templates`** — Auto-fill templates only

## Knowledge Base

Jurisdiction-specific guidance in the `knowledge/` folder:

- `AI-Regulations-Global-Overview.md` — Cross-cutting themes and timeline
- `AI-Regulations-EU.md` — EU AI Act and GDPR
- `AI-Regulations-UK.md` — UK AI Bill
- `AI-Regulations-UnitedStates.md` — Executive Order 14110, sector-specific rules
- `AI-Regulations-Canada.md` — AIDA and sector regulations
- `AI-Regulations-China.md` — CAC regulations
- `AI-Regulations-Japan-SouthKorea.md` — Japanese and Korean guidelines
- Plus 4 more regional guides

## Output Structure

After running `extract-evidence`, your `output/` folder contains:

```
output/
├── 01-transparency-documentation.md
├── 02-user-facing-disclosures.md
├── 03-ai-content-labeling.md
├── ... (22 templates total)
├── MANIFEST.md                           # Index of all templates
├── compliance-config-snapshot.json        # Config at generation time
└── evidence-check-report.txt              # Validation report
```

Hand the entire `output/` folder to your legal or compliance team.

## Template Categories

The 22 templates cover:

- **Transparency & Disclosure** (T) — System transparency, user disclosures, content labeling
- **Documentation** (D) — Training data, decision logic, impact/risk assessment
- **Assessments** (A) — Privacy impact, bias testing, security assessment
- **Human Oversight** (O) — Oversight model design, governance, incident management
- **User Rights** (U) — Consent mechanisms, data subject rights
- **Compliance** (C) — Risk classification, conformity assessment, registration

## For Legal Teams

This plugin produces **research documentation** for legal review. Output includes:

- Evidence of compliance efforts
- Risk assessments and mitigation strategies
- Jurisdiction-specific requirements mapped to your system
- Compliance timelines and deadlines

**Always have a qualified legal team review** compliance evidence before deploying regulated AI systems.

## License

MIT License. Copyright (c) 2026 Justice.

## See Also

- `ai-compliance` skill — Used to answer compliance questions
- Original LLMComplianceSkill — Full source with all tools and templates

