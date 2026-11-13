---
name: plan-implement
description: Use only when the user explicitly asks to use plan-implement/$plan-implement or requests milestone-by-milestone implementation with a subagent review after each milestone. Do not invoke for ordinary implementation merely because a plan exists.
---

# Plan Implement

Execute the requested plan one milestone at a time, with independent review and main-agent resolution after each milestone.

This is the single-implementer workflow. For a requested orchestrator with fresh milestone executors, use [plan-orchestrate](../plan-orchestrate/SKILL.md). Do not replace the selected workflow implicitly.

## Preparation and plan maintenance

Read the current plan and applicable repository instructions. Use [plan-build](../plan-build/SKILL.md) for persistent plan maintenance and completion. Update verified tasks during execution and record implementation adjustments within the authorized scope without requiring a separate request to revise the plan. Preserve the intended outcome and explain material changes.

Record the working-tree baseline before implementation, including staged, unstaged, and relevant untracked work. Preserve enough of the baseline and each milestone's starting state to identify its actual changes, including when milestones edit the same file. Use existing commits or temporary patches/file snapshots as appropriate; do not commit merely to create a review boundary or overwrite unrelated user work.

## Milestone cycle

Honor the plan's execution mode, decision boundaries, prototype contract, and worktree strategy. Create the relevant milestone worktree from the correct dependency state before editing; preserve unrelated work and verify integrated results. For a clear milestone, state the interpretation briefly and proceed without an artificial acknowledgement round. For material unresolved decisions, complete the useful preflight and pause dependent work for resolution. Suggestions outside scope do not block progress.

If assigned only one milestone by an orchestrator, stay within that assignment. Return implementation evidence and findings to the canonical plan owner instead of marking the overall milestone accepted, advancing the next milestone, or archiving the plan. Local progress notes are not acceptance.

1. Implement the current milestone and update completed, verified tasks in the plan.
2. Run proportionate checks that establish the milestone's expected behavior. Record failures and unavailable checks truthfully.
3. Launch one fresh, read-only subagent using the review instructions below. Review the current milestone's delta, relevant untracked files, and affected integration paths, rather than automatically reviewing all accumulated uncommitted work.
4. Independently cross-check every finding against the code, user requirements, current plan, and repository constraints. Classify it as accept and fix, reject with evidence or rationale, or defer as valid but outside scope.
5. Implement accepted fixes in the main agent and rerun affected checks. Explain dispositions briefly; "by design" alone is insufficient. Use another fresh review only when material fixes or high-risk changes justify it, not as a mechanical loop until no findings remain.
6. Update the plan with verification evidence, relevant decisions, remaining risks, and the next action. Continue to the next milestone once accepted findings are fixed and required milestone validation passes. If a required check is unavailable, record the blocker and keep affected completion criteria open; continue independent work when possible.

## Independent review

Start a fresh reviewer session without inherited conversation, using `fork_turns: "none"` where supported. If unavailable, prepare a review handoff and report required independent review as pending; do not substitute self-review silently. Choose available model settings proportionate to the risk; do not require provider-specific setting names. The reviewer must not edit files, mutate the repository, or implement fixes.

Provide a self-contained packet with the repository location, milestone baseline and review target, applicable repository instructions, current plan requirements and milestone criteria, and relevant application constraints. Extract needed plan context without forwarding prior review history or implementation narration.

Include brief design notes when relevant: intentional behavior, accepted tradeoffs, their reasons, and known downsides. Use only established requirements, current plan decisions, or documented implementation rationale; do not invent justifications. Assemble notes from available evidence and ask the user only when an unresolved decision materially changes correctness. Do not pass the main agent's code-quality verdict, anticipated findings, previous review findings, or arguments intended to secure approval.

Design notes are context, not exemptions. Ask the reviewer to check whether the code honors the decisions and whether their assumptions hold. It may challenge a decision with evidence of a material problem, distinguishing design concerns from implementation defects.

Let the reviewer choose how to investigate correctness, contracts, failure modes, and material compatibility, security, performance, or maintenance risks. Request findings ordered by severity, with file-and-line evidence, the triggering condition, and resulting failure or material impact. Separate demonstrated defects from unresolved questions. Missing tests alone are not a defect without identifying the behavior left unverified. No material findings is a valid result.

## Completion

Include cross-milestone integration and acceptance checks in final validation. Record checks actually performed and any unperformed checks; a manual QA checklist does not establish that validation passed. Respect repository and user constraints on browser validation.

Verify every applicable Definition of Done item and milestone task before marking the plan complete. Fill `Completion Summary` and archive it under `.plans/done/` through the `plan-build` lifecycle. Report the outcome, accepted fixes, rejected and deferred findings with reasons, validation, and residual risks. Do not commit or push unless the user explicitly asks.
