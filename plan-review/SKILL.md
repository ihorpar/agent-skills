---
name: plan-review
description: Review code-related plans, feature implementations, refactors, migrations, and similar engineering proposals by launching a sub-agent, then triaging its findings into accepted and rejected items with brief reasons.
---

# Plan Review

## Use This Skill

Use this skill when a user wants a review of a code-related plan, especially for a new feature, refactor, migration, rollout, or similar engineering change.

## Review Workflow

1. Launch one sub-agent to review the plan.
2. Give the sub-agent the plan plus only the repo context needed to evaluate it.
3. Ask for concrete findings only.
4. Focus the review on implementation realism, not abstract product critique.

## What To Look For

Ask the sub-agent to focus on:

- missing implementation steps
- incorrect assumptions about the codebase
- broken sequencing or dependencies
- API, schema, or contract mismatches
- edge cases and failure modes
- test coverage gaps
- backward compatibility, migration, or rollout risks
- performance, security, or maintainability concerns when material

Prefer findings grounded in actual repository structure, existing patterns, and testable implementation details.

## Triage Findings

When the sub-agent returns:

- Accept findings that are valid, material, and worth addressing.
- Reject findings that are unsupported, based on a misunderstanding, duplicate, too speculative, or not important enough.

For each finding, briefly explain why you accepted or rejected it.

## Final Response

If there are no findings, say the plan looks sound and mention any low-confidence areas.
Do not rewrite the plan unless the user explicitly asks for that.
Keep the final response concise and structured.
