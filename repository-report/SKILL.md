---
name: repository-report
description: Activates only when the user explicitly asks for a repository report and generates a fixed 7-section Executive-Technical Repository Report.
---

# Executive-Technical Repository Report

## Purpose

Deliver a consistent executive-technical document to understand the real state of a repository without turning it into a deep audit. The output should support decision-making and fast onboarding.

## Activation and boundaries

Use when:

- The user explicitly asks for a **repository report**.
- Valid variants: "give me a repository report", "generate a repo report", "executive-technical repository report".

Avoid when:

- The user asks for specific debugging or code fixes.
- The user only wants to find files, symbols, or isolated code facts.
- The user requests partial analysis (for example, only branches or only dependencies) without asking for a full report.

## Main rule of this skill

- Always generate an **Executive-Technical Repository Report**.
- Always use the **same full structure**.
- Do not omit sections for brevity; if information is missing, state it explicitly in the relevant section.

## Delivery rule (mandatory)

- The final result must always be saved as a Markdown file in `docs/`.
- Recommended filename format: `REPOSITORY_EXECUTIVE_TECHNICAL_REPORT_YYYY-MM-DD.md`.
- The report must explicitly include the generation date.
- In addition to the file, provide a short chat summary.

## Required report scope

1. Executive summary
2. General overview
3. Repository structure
4. Branch and collaboration status
5. Technologies and dependencies
6. Application architecture
7. CI/CD (if applicable)

## Branch rules

### Branch classification

Classify branches into two groups:

- **Primary branches**: `main`, `master`, `develop`, `dev`, `trunk`, `release/*`, `staging`, `production`, or equivalents representing baseline, integration, or delivery.
- **Secondary branches**: `feature/*`, `fix/*`, `hotfix/*`, `bugfix/*`, `chore/*`, `docs/*`, `refactor/*`, `test/*`, plus personal or temporary branches.

### Critical rule

- **Never** describe a primary branch as "obsolete".
- For primary branches, use operational readings such as: `Primary baseline`, `Integration branch`, `No recent activity`, `Requires validity check`.
- For secondary branches, you may use states such as: `Active`, `On hold`, `Candidate for closure`.

### Minimum data per branch

- Name
- Type (`Primary` or `Secondary`)
- Last activity
- Last author
- Reading or status
- Suggested action

If PR/issue metadata is unavailable, do not invent context; mark `no additional evidence`.

## Collaboration rules

For each contributor include:

- Commits in 30 days
- Commits in 90 days
- Trend (`Up`, `Down`, `Stable`, `No recent activity`)
- Level (`High`, `Medium`, `Low`)

If activity is concentrated in 1–2 people, state it neutrally.

## Workflow

1. Gather project context

- Read `README`, `package.json`, main router, core folders, and configuration files.

2. Gather Git data

- Local/remote branches and latest activity.
- Short commit history for recent context.
- Aggregated contributors over 30/90 days.

3. Identify stack and dependencies

- Frameworks, critical libraries, versions, and purpose.
- Separate runtime and development dependencies.

4. Identify architecture and structure

- Main modules.
- Data flow.
- Visible technical decisions.
- CI/CD evidence if present.

5. Write using the fixed template

- Do not simplify structure.
- Do not change section order.

6. Save document

- Write final report to `docs/REPOSITORY_EXECUTIVE_TECHNICAL_REPORT_YYYY-MM-DD.md`.
- Confirm the created or updated path to the user.

## Required output format

Always use this structure:

# Executive-Technical Repository Report

**Date:** YYYY-MM-DD
**Repository:** REPOSITORY_NAME
**Data source:** Git + files from REPOSITORY_NAME

## 1) Executive summary

- What the project does
- Who it serves
- Current state
- Key findings

## 2) General overview

- Project type
- Current status
- Main entrypoints / routes / scripts
- Relevant operational findings

## 3) Repository structure

- Summarized tree of main folders
- Folder responsibilities
- Observed conventions

## 4) Branch and collaboration status

### Primary branches

| Branch | Type | Last activity | Author | Reading | Suggested action |
| ------ | ---- | ------------- | ------ | ------- | ---------------- |

### Secondary branches

| Branch | Type | Last activity | Author | Status | Suggested action |
| ------ | ---- | ------------- | ------ | ------ | ---------------- |

### Contributors

Analyzed period: 30/90 days

| Contributor | Commits (30d) | Commits (90d) | Trend | Level |
| ----------- | ------------: | ------------: | ----- | ----- |

## 5) Technologies and dependencies

- Runtime
- Development
- Critical versions
- Purpose of each key dependency

## 6) Application architecture

- General pattern
- Main modules
- Data flow
- Visible technical decisions

## 7) CI/CD (if applicable)

- Detected pipelines
- Deployment configuration
- Visible automations
- If not applicable or not detected, state it explicitly

## Writing style

- Clear technical language for mixed audiences.
- Concrete, decision-oriented phrasing.
- No filler and no overly compressed output.
- If information is missing, state it in the corresponding section.
- For PDF readability: use compact tables, short lists, and consistent headings.

## Success criteria

✅ The full 7-section structure is always preserved
✅ Primary and secondary branches are clearly separated
✅ No primary branch is labeled as obsolete
✅ Stack and dependencies include version and purpose
✅ CI/CD is documented or explicitly marked as not detected

## Resources

- [patterns.md](patterns.md): classification and writing patterns
- [examples.md](examples.md): usage examples
- [template.md](template.md): base report template
