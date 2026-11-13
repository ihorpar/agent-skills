# Handoff templates

Keep packets concise and self-contained. Include only applicable fields. Use plain language compatible with the receiving model; no private reasoning transcript is needed.

## O to executor

```text
Role: Execute milestone <ID> only; report to O. Do not accept your own work.
Goal: <observable outcome and why it matters>
Plan: <canonical location and pinned revision>
Workspace: <path/branch, exact base, accepted dependencies, integration destination>
Context: <applicable instructions, relevant files, accessible prototype source/version>
Requirements: <hard constraints, required outcomes, preferences, exclusions>
Prototype: <interface and interactions to preserve; mock behavior boundaries>
Acceptance: <criteria, required checks, review requirement and reason>
Mode: <proceed after brief self-check | preflight then wait for O>
Authority: <allowed decisions/actions; what needs O or user resolution>
Return: <interpretation, material questions if any, evidence-backed suggestions if any>
Finish: Report exact changes, verification and missing checks; do not advance milestones.
```

## Executor to O

```text
Milestone / plan revision:
Status: Submitted | Blocked
Workspace and exact baseline/result state:
Implemented outcomes and actual delta/artifact references:
Acceptance evidence: <criterion -> check/result and code state>
Unperformed or failed checks:
Review findings/dispositions, if review was performed:
Deviations and their reasons:
Blockers / decisions needed, with recommended resolution:
Out-of-scope suggestions, only if material:
Integration notes and remaining work:
```

## O resolution

```text
Milestone / evaluated code state:
Decision: Accepted | Changes requested | Awaiting review/checks/integration/user
Evidence checked:
Findings: <accept and route to E | reject with reason | defer with impact>
Required follow-up and owner:
Canonical plan update and next action:
```

Send a reviewer established requirements and design reasons, exact baseline/result, and relevant integration paths. Omit the executor's quality verdict, expected findings, prior review history, or persuasion toward approval. A reviewer may challenge a decision with material evidence.
