# repository-report

Executive-Technical Repository Report skill for AI agents.

## What it does

Generates a fixed 7-section repository report when the user explicitly asks for a repository report.

## Activation

This skill should activate only for explicit repository report requests, for example:

- "Give me a repository report"
- "Generate an executive-technical repository report"

## Output

- Saves a Markdown report in `docs/`
- Uses a fixed 7-section structure
- Includes branch classification (primary vs secondary)
- Includes collaboration, dependencies, architecture, and CI/CD (if applicable)

## Install

```bash
npx skills add <owner>/<repo> --skill repository-report
```

Example:

```bash
npx skills add canoc/cafefarm --skill repository-report
```

## Skill files

- `SKILL.md`
- `SKILL.json`
- `template.md`
- `patterns.md`
- `examples.md`
