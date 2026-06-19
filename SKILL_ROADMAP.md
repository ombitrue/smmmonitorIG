# Skill Roadmap

This roadmap tracks capability development, not feature delivery. Skill levels move only when there is evidence from merged work, accepted designs, published artifacts, reviewer validation, or pilot outcomes.

## Skill graph

```text
Evidence
 ├─ Capture
 ├─ Replay
 ├─ Benchmarking
 └─ Reproducibility

Integration Reliability
 ├─ Provider Diagnostics
 ├─ API Boundary Design
 ├─ Error Interpretation
 └─ Configuration Hygiene

Product Clarity
 ├─ Setup Narrative
 ├─ User Trust
 ├─ Scope Control
 └─ Public Documentation

Operational Readiness
 ├─ Local Runbook
 ├─ Health Checks
 ├─ Failure Triage
 └─ Pilot Feedback
```

## Skill levels

```text
0 = Aware
1 = Understand
2 = Practice
3 = Repeatable
4 = Mentor
5 = Authority
```

## Current capabilities

```yaml
- skill: Provider Diagnostics
  level: 2
  confidence: medium
  evidence:
    - Existing proxy includes /api/health and /api/probe routes for checking API-key presence and testing candidate provider endpoints.
  next_step: Convert diagnostic behavior into documented, repeatable verification steps with expected outputs.

- skill: API Boundary Design
  level: 2
  confidence: medium-low
  evidence:
    - Existing server centralizes RapidAPI host, endpoint configuration, request construction, and error enrichment behind backend routes.
  next_step: Document which credentials are read from environment variables versus request headers, and clarify the trust boundary.

- skill: Error Interpretation
  level: 2
  confidence: medium
  evidence:
    - Existing backend maps common upstream statuses such as 401, 403, 404, and 429 to actionable log messages.
  next_step: Add user-facing troubleshooting examples that can be reproduced without exposing secrets.

- skill: Setup Narrative
  level: 1
  confidence: medium-low
  evidence:
    - README contains basic installation and provider-configuration guidance.
  next_step: Align documentation with the actual default port and current server behavior.

- skill: Reproducibility
  level: 1
  confidence: low
  evidence:
    - npm start exists, but the default test script is a placeholder and there is no formal verification checklist yet.
  next_step: Add a minimal smoke-check path for local server startup and health validation.

- skill: Pilot Feedback
  level: 0
  confidence: low
  evidence: []
  next_step: Define what would count as a valid pilot outcome before claiming monitoring effectiveness.
```

## Capability signals

```yaml
signals:
  strongest:
    - Backend diagnostic intent is already present.
    - The application is small enough to keep operational behavior understandable.
  weakest:
    - No accepted pilot outcomes are recorded.
    - Automated validation is not yet established.
    - Documentation and runtime defaults appear partially misaligned.
```

## Next recommended skill

```yaml
next_recommended_skill: Reproducibility
reason: The project needs a repeatable way to prove setup and proxy health before adding claims, UI complexity, or broader integrations.
next_best_development_step: Document and/or automate a minimal local smoke check that verifies server startup, default port behavior, and /api/health response without requiring a real RapidAPI call.
```

## Update rule reminder

Capabilities produce execution. Execution produces evidence. Evidence justifies progress. Progress does not come from claims.
