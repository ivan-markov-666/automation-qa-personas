# automation-qa-personas

A collection of reusable LLM personas designed to speed up day-to-day work for Automation QA engineers, SDETs, and developers.

## Repository purpose

This repository contains persona prompt documents that you can paste into an LLM-based assistant (e.g. GitHub Copilot Chat, ChatGPT, Windsurf, etc.) to get a focused "virtual teammate" for a specific QA task. The goals are to:

- Shorten repetitive analysis and authoring work
- Standardise the quality of test design, diagnostics, and documentation
- Make advanced QA practices more accessible to the whole team

## Current personas

### 1. API Test Automation LLM Assistant (`API-testing.md`)

**Primary use cases**

- Design comprehensive positive and negative API test suites for a single endpoint
- Generate test cases in different formats (classical, BDD, tabular, or a custom template)
- Guide you through collecting framework context, endpoint details, generating cases, refining them, and then implementing automated tests in your existing framework

**How it helps**

- Ensures systematic coverage of methods, protocols, headers, body variants, authentication, rate limiting, pagination, caching, performance, and more
- Keeps you focused on one endpoint at a time and prevents missing important edge cases
- Produces ready-to-implement test case specifications that can be handed to any QA engineer or developer

**Rough time savings**

- Manual design of a thorough test suite for one non-trivial endpoint typically takes ~1–2 hours
- With the persona: ~10–20 minutes to answer its questions and review the generated cases
- Typical saving: about **3–5× faster** test design, with more consistent coverage

---

### 2. Maria Test Analyzer – Test Report & Log Output Summary (`TestReportAndLogOutputSummary.md`)

**Primary use cases**

- Analyse failing test runs and log output
- Quickly extract exact error messages and the most critical failures
- Run focused commands such as `/help`, `/quick`, `/framework`, `/patterns`, `/performance`, `/compare`, `/export` to explore failures from different angles
- Generate human-readable failure reports for documentation or sharing with the team

**How it helps**

- Turns raw console output into a prioritised list of issues, suspected root causes, and concrete next steps
- Highlights recurring patterns (timeouts, database problems, missing dependencies, performance bottlenecks, etc.)
- Produces ready-to-paste analysis reports for tickets, PR comments, or status updates

**Rough time savings**

- Manual triage of a noisy test log often takes 15–45 minutes, especially under time pressure
- With the persona: ~2–10 minutes for an initial `/quick` scan plus deeper `/analyze` runs as needed
- Typical saving: about **2–4× faster** triage, with clearer, more structured communication

---

### 3. Emily – Complete Documentation Suite Generator (`DocumentEverything.md`)

**Primary use cases**

- Generate and maintain three core documentation files for any project:
  - `SETUP_GUIDE.md` – technical setup guide / runbook for developers and admins
  - `USER_GUIDE.md` – end-user guide in plain language
  - `README.md` – high-level project overview and entry point
- Work with both new and existing projects
- Drive a short interactive interview about architecture, setup, workflows, and known gotchas

**How it helps**

- Ensures that technical, user, and overview docs stay in sync
- Encourages capturing **why** decisions were made, not just the bare minimum "how to run"
- Integrates well with AI code editors that can auto-create or update files from Emily's output

**Rough time savings**

- Writing a decent setup guide, user guide, and README from scratch usually takes half a day to a full day
- With the persona: ~30–90 minutes of Q&A plus review and minor edits
- Typical saving: about **3–6× faster** documentation with higher consistency

## How to use these personas

1. Open the persona file you want to use (`API-testing.md`, `TestReportAndLogOutputSummary.md`, or `DocumentEverything.md`).
2. Copy the persona document and paste it into your LLM-based assistant chat.
3. Follow the activation / startup instructions in the document (each persona explains how to begin).
4. Collaborate with the persona as with a specialised teammate:
   - answer its questions
   - review what it generates
   - iterate until the output matches your needs

## Who benefits

- **Automation QA / SDETs** – faster test design, clearer reports, less manual log reading
- **Developers** – better feedback from tests, ready-made docs, less time spent on boilerplate
- **Teams** – more consistent practices across projects and easier onboarding

Over time, you can extend this repository with additional personas for other repetitive or high-cognitive QA tasks and keep them all in one place.
