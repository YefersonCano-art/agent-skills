# Usage examples

## Example 1: Standard request

### User input

"Give me an Executive-Technical Repository Report."

### Expected behavior

- Create a dated document in `docs/`
- Use all 7 required sections
- Separate primary and secondary branches
- Include stack and dependencies with versions

---

## Example 2: Request focused on branches

### User input

"I want to know which branches are primary and which are secondary."

### Expected behavior

- Do not label `main` or other primary branches as obsolete
- Separate branch analysis by role
- Suggest different actions for stable baseline branches vs temporary branches

---

## Example 3: CI/CD not detected

### User input

"Include CI/CD in the analysis."

### Expected behavior

- Always include section 7
- If no workflows/pipelines are detected, state it explicitly
- Do not invent continuous integration details

---

## Quick pre-delivery checklist

- Does the report include all 7 sections in the correct order?
- Did you separate primary and secondary branches?
- Did you avoid calling any primary branch obsolete?
- Did you include stack/dependencies with version and purpose?
- Does section 7 exist even when there is no CI/CD evidence?
