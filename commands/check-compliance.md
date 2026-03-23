# Check Compliance

Validate your compliance evidence for completeness and identify gaps.

This command runs the evidence checker to flag missing fields, incomplete sections, and compliance gaps across all templates.

## Usage

```bash
check-compliance [--config <path>] [--output <path>] [--template <NN>] [--verbose] [--json]
```

## Options

- `--config <path>` — Path to compliance-config.json (default: tools/compliance-config.json)
- `--output <path>` — Output directory for filled templates (default: output/)
- `--template <NN>` — Check only template NN (01-22)
- `--verbose` — Show detailed findings for each template
- `--json` — Structured JSON output

## Examples

```bash
# Check all templates
check-compliance

# Check only Template 07 (Privacy Impact Assessment)
check-compliance --template 07

# Verbose output with JSON format
check-compliance --verbose --json
```

## Output

The checker reports:
- **Missing fields** — Required fields not filled
- **Incomplete sections** — Sections with placeholder text
- **Compliance gaps** — Fields required by your target jurisdictions
- **Risk flags** — High-risk compliance gaps that need immediate attention

## See Also

- `extract-evidence` — Run the full extraction pipeline
- `fill-templates` — Auto-fill templates only
