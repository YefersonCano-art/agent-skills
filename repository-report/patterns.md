# Executive-Technical Report Patterns

## Pattern 1: Fixed report order

The report must always use this order without omitting sections:

1. Executive summary
2. General overview
3. Repository structure
4. Branch and collaboration status
5. Technologies and dependencies
6. Application architecture
7. CI/CD (if applicable)

Do not replace this with a short version.

---

## Pattern 2: Branch classification by role

### Primary branches

Treat as primary unless there is strong evidence otherwise:

- `main`
- `master`
- `develop`
- `dev`
- `trunk`
- `release/*`
- `staging`
- `production`

Suggested readings:

- "Primary repository baseline"
- "Integration branch"
- "No recent activity"
- "Requires validity check"

Never use "obsolete" for a primary branch.

### Secondary branches

Examples:

- `feature/*`
- `fix/*`
- `hotfix/*`
- `bugfix/*`
- `chore/*`
- `docs/*`
- `refactor/*`
- `test/*`
- personal branches

Suggested states:

- `Active`
- `On hold`
- `Candidate for closure`

---

## Pattern 3: Contributor reading

Use 30/90 day windows by default to avoid short-term bias.

Suggested trends:

- `Up`: 30-day period shows recovery or increase compared to the longer period.
- `Down`: no recent activity or clear decline.
- `Stable`: sustained contribution.
- `No recent activity`: zero commits in both 30 and 90 days.

---

## Pattern 4: Stack and dependencies

Always separate at minimum:

- Runtime dependencies
- Development dependencies
- Critical versions
- Usage purpose

Do not list irrelevant packages without context. Prioritize frameworks, routing, state, UI, build, linting, testing, and deployment.

---

## Pattern 5: CI/CD

Section 7 must always exist.

If evidence exists, include:

- Pipelines or workflows
- Deployment files
- Visible integrations
- Build, test, or deploy automations

If there is no evidence, explicitly write:

- "No CI/CD pipeline was detected in the analyzed repository."

---

## Pattern 6: Executive-technical writing

- Clear and direct language.
- Sufficient technical depth for onboarding and decisions.
- Do not turn it into a deep audit.
- If evidence is missing, state it and do not invent details.
