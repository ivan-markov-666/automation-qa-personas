# Project Context — {PROJECT_NAME}

Override file for the Denitsa SDET persona. Contains project-specific rules.
Load this together with the main persona file.

---

## 1. Bug Tracker

- **System:** {FILL IN — e.g., Azure DevOps / Jira / GitHub Issues}
- **Project URL:** {FILL IN}
- **Default Area Path:** {FILL IN}
- **Default Iteration Path:** {FILL IN}
- **Default Tags:** automated-testing, {FILL IN}

## 2. Bug Report Template

Team uses these fields (★ = required, others optional but recommended):

- ★ **Title** — `[Component] — {summary}`
- ★ **Severity** — Critical / High / Medium / Low
- ★ **Repro Steps** — numbered, actionable
- ★ **Expected Result** — reference BR-ID when possible
- ★ **Actual Result** — concrete values
- **Environment** — staging / production / local
- **Evidence** — error message / response payload / log snippet / monitoring data (see §7)
- **Affected Build / PR** — link if known

Team-specific rules: {FILL IN — e.g., "Tag dev lead for Critical bugs"}

## 3. PBI Comment Format

- Language: English
- Max length: {FILL IN — e.g., "10 lines, one scroll"}
- Required sections: Status, Coverage, Bugs (if any), Blocked (if any)
- Link via BUG-{N} work item IDs (not bug titles)
- Other rules: {FILL IN}

## 4. QA Documentation — Source of Truth

- **Source of Truth:** {FILL IN — e.g., "Automation project repository" or "Tracker only"}
- **Test cases location:** {FILL IN — e.g., docs/test-cases/*.md}
- **Bug reports location:** {FILL IN — e.g., docs/bugs/*.md}
- **Test strategy location:** {FILL IN — e.g., docs/e2e-strategy.md}
- **Sync to tracker:** {FILL IN — e.g., AzureCli command/script}
- **Workflow:**
  1. {FILL IN — e.g., "Generate .md file in correct folder"}
  2. {FILL IN — e.g., "Commit"}
  3. {FILL IN — e.g., "Run sync command to push to tracker"}

## 5. Test Plan / Test Case Organization

- **Structure:** {FILL IN — e.g., "Root test plan with sub-plans per project"}
- **Before creating new test cases:** Denitsa MUST query the source of truth 
  (see §4) via Research Prompt to understand current structure and decide 
  where new test cases belong.
- **Naming conventions for TC files:** {FILL IN — e.g., TC-{N}-{slug}.md}

## 6. Artifact Relations

Relations that MUST be enforced when generating artifacts:

- **Test Case → PBI:** {FILL IN — e.g., "Every TC links to the ONE PBI that motivated it"}
- **Bug → PBI:** {FILL IN — e.g., "Every Bug links to the PBI being tested"}
- **Bug → Test Case(s):** {FILL IN — e.g., "Every Bug links to the TC(s) that uncovered it"}
- **Other relations:** {FILL IN}

## 7. Bug Evidence — Monitoring / Observability

Before filing a Bug, ALWAYS check for raw error evidence:

- **Tool:** {FILL IN — e.g., AppInsights / Datadog / Sentry / CloudWatch}
- **Access:** {FILL IN — e.g., URL, query template, CLI command}
- **What to capture:** Raw error message, stack trace, correlation ID, timestamp
- **Include in Bug Report:** raw evidence goes in the Evidence section of the bug file (see §2)

## 8. Bug Filing Workflow

1. Document in automation project first: {FILL IN — e.g., docs/bugs/BUG-{N}-{slug}.md}
2. Commit (suggested commit message format: {FILL IN})
3. Sync to tracker: {FILL IN — e.g., "Run AzureCli sync command from project root"}

---

## How Denitsa Applies This

- **Phase 2** (Test Case Generation) → respect §4 (file-first), §5 (query structure before generating), §6 (relations)
- **Step 4.3** (Failing Test Diagnosis) → check §7 for raw evidence BEFORE classifying as BUG
- **Step 4.6** (Bug Reports) → use fields from §2; include raw evidence per §7
- **Step 4.7** (Bug Generation Prompt) → use defaults from §1; follow workflow §8
- **Step 4.8** (PBI Comment) → follow §3
- All other phases → main persona as-is
