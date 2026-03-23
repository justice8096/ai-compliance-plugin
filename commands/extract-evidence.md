# Extract Evidence

Extract compliance evidence from a source repository using the AI Compliance Evidence Collection Kit.

This command runs the complete evidence extraction pipeline:

1. **Configure** your AI system details in `tools/compliance-config.json`
2. **Assess** using the 19 interactive HTML tools (browser-based assessments for human judgment)
3. **Auto-fill** all evidence templates from your configuration
4. **Validate** your evidence for completeness and compliance gaps

## Usage

```bash
extract-evidence [--config <path>] [--output <path>] [--interactive] [--json]
```

## Options

- `--config <path>` — Path to compliance-config.json (default: tools/compliance-config.json)
- `--output <path>` — Output directory for filled templates (default: output/)
- `--interactive` — Open browser tools for human assessments
- `--json` — Generate JSON output instead of markdown

## Workflow

1. Edit `tools/compliance-config.json` with system, organization, and project details
2. Run interactive tools:
   - Open `tools/interactive/risk-classification.html` for EU AI Act risk tier
   - Fill `tools/interactive/pia-assessment.html` for privacy assessment
   - Complete other assessments as relevant to your jurisdiction
   - Tools save results back to the config file
3. Auto-fill templates: `node tools/autofill.js --config tools/compliance-config.json --output output/`
4. Review generated evidence in `output/` folder
5. Hand to legal/compliance team for final review

## Output

Generated in `output/`:
- 22 filled evidence templates (markdown)
- `MANIFEST.md` — Index of all templates
- `compliance-config-snapshot.json` — Config snapshot at generation time
- `evidence-check-report.txt` — Validation report

## See Also

- `check-compliance` — Validate your evidence
- `fill-templates` — Auto-fill templates only
