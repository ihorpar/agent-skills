---
name: plan-implement
description: Implement code-related plans, feature builds, refactors, migrations, and similar engineering work milestone by milestone, with a sub-agent code review after each milestone and explicit triage of the findings.
---

# Plan Implement

## Strategy

Use this skill when a user gives a plan that should be executed in ordered milestones.

Work one milestone at a time:

1. Implement the current milestone.
2. Run the fastest relevant checks for the milestone before review.
3. Launch a fresh sub-agent with medium reasoning to review the uncommitted changes.
4. Give that reviewer only the general task context, the original plan, the current milestone scope, its expected outcome or done criteria, and the relevant acceptance criteria.
5. Do not pass iteration history, prior findings, or implementation chatter.
6. Have the reviewer inspect the current uncommitted diff and return concrete findings.
7. Triage the findings:
   - Fix findings that are valid and material.
   - Push back on findings that are unreasonable, unsupported, or clearly by design.
8. Re-run the fastest relevant checks after applying accepted fixes.
9. Update the plan checklist or change notes after each milestone so context survives into the next cycle.
10. Briefly explain why each finding was accepted or rejected.
11. Move to the next milestone only after the current one is reviewed and resolved.
12. After the final milestone, update Outcomes or Retrospective notes and summarize residual risks.

## Review Focus

Ask the review sub-agent to use appropriate reasoning, usually medium, and higher when the milestone touches migration or runtime safety.

Ask the review sub-agent to focus on:

- correctness and broken assumptions
- missing edge cases
- test coverage gaps
- contract, API, or schema mismatches
- rollout, migration, or compatibility risk
- maintainability, security, or performance concerns when material
- the uncommitted diff plus adjacent call paths

Have the reviewer return file-and-line findings ordered by severity.

## Operating Rules

- Keep the plan moving milestone by milestone.
- Keep each review fresh and isolated from prior iteration history.
- Do pass the original plan, current milestone scope, expected behavior, and acceptance criteria.
- Prefer concrete, repo-grounded feedback over speculation.
- For UI milestones, produce a manual QA checklist before marking the milestone complete.
- Do not rewrite the plan unless the user asks for a revised plan.
