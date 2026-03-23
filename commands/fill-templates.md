# Fill Templates

Auto-fill compliance evidence templates from your configuration and interactive assessments.

This command populates all 22 evidence templates using data from your compliance-config.json and the results from interactive HTML assessments.

## Usage

```bash
fill-templates [--config <path>] [--output <path>] [--template <NN>] [--format <format>]
```

## Options

- `--config <path>` — Path to compliance-config.json (default: tools/compliance-config.json)
- `--output <path>` — Output directory for filled templates (default: output/)
- `--template <NN>` — Fill only template NN (01-22)
- `--format <format>` — Output format: markdown (default), json, html

## Examples

```bash
# Fill all templates
fill-templates

# Fill only Template 07 (Privacy Impact Assessment)
fill-templates --template 07

# Output as HTML
fill-templates --format html
```

## Output

Generated templates in `output/`:
- `01-transparency-documentation.md`
- `02-user-facing-disclosures.md`
- `03-ai-content-labeling.md`
- ... (22 templates total)
- `MANIFEST.md` — Index of all templates

## Before Running

1. Edit `tools/compliance-config.json` with your system and organization details
2. Run interactive assessments in `tools/interactive/` for human-judgment fields
3. Save assessment results back to config

## See Also

- `extract-evidence` — Run the full extraction pipeline with validation
- `check-compliance` — Validate your evidence for completeness
