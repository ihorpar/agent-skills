---
name: plan-review
description: Use only when the user explicitly asks to review or critique a plan, names plan-review, or requests a sub-agent plan review. Reviews code-related plans, applies accepted findings to the plan by default, and reports accepted and rejected findings. Do not invoke for ordinary plan creation, implementation, or general code reviews.
---

# Plan Review

Use this skill only after an explicit request to review a plan. It is intended primarily for code-related plans covering features, refactors, migrations, rollouts, and similar engineering work.

## Modes

- **Apply mode (default):** Review the plan, triage every finding, and update the plan with every accepted finding before responding.
- **Review-only mode:** Only use when the user explicitly asks for feedback without changing the plan, or says not to modify it.

"Apply" means update the plan, not implement the code. Code implementation belongs to `plan-implement`.

## Workflow

1. Locate and read the complete plan. Read only the repository files needed to evaluate its implementation realism, assumptions, and dependencies.
2. Launch one fresh sub-agent to review the plan. Pass the plan, relevant repository context, expected behavior, acceptance criteria, and current milestone when applicable. Do not pass prior review history, the main agent's analysis, or intended conclusions.
3. Ask the sub-agent for concrete findings only, grounded in repository structure and testable implementation details. Ask it to identify severity and plan section or file/line evidence where available.
4. Triage every finding in the main agent:
   - **Accept** findings that are valid, material, and worth addressing.
   - **Reject** findings that are unsupported, based on a misunderstanding, duplicate, too speculative, or not important enough. Record a brief reason.
5. In apply mode, immediately update the plan with every accepted finding. Add or revise implementation steps, sequencing, dependencies, acceptance criteria, tests, rollout notes, risks, or milestone tracker entries as needed. Preserve the plan's existing structure and keep all checklist/change notes accurate.
6. Re-read the updated plan and check for contradictions, missing dependencies, and incomplete acceptance criteria. Do not claim that a finding was applied unless the plan actually reflects it.
7. In review-only mode, leave the plan unchanged and report proposed changes instead.

## What To Look For

Ask the sub-agent to focus on:

- missing implementation steps
- missing or inadequate milestone tracker structure
- milestone tracking that is only meant to be updated at the end instead of during execution
- incorrect assumptions about the codebase
- broken sequencing or dependencies
- API, schema, or contract mismatches
- edge cases and failure modes
- test coverage gaps
- backward compatibility, migration, or rollout risks
- performance, security, or maintainability concerns when material

Use appropriate reasoning effort for the scope, usually medium. Use higher reasoning for migration, data integrity, runtime safety, or other high-risk work.

## Final Response

Keep the response concise and report:

- accepted findings and how each was incorporated into the plan
- rejected findings and the brief reason for each rejection
- any low-confidence areas or residual risks

If there are no findings, say the plan looks sound and mention any low-confidence areas. If the plan was inline or not writable, state that the accepted changes were returned as proposed edits rather than written to a file.
