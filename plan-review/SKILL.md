---
name: plan-review
description: Use only when the user explicitly asks to review or critique a code-related plan, names plan-review/$plan-review, or requests a subagent plan review. Independently reviews the plan, applies accepted findings by default, and reports finding dispositions. Do not invoke for ordinary plan creation, implementation, or general code reviews.
---

# Plan Review

Review engineering plans for implementation realism, missing requirements, and material risks.

## Modes

- **Apply mode, default:** Review, triage every finding, and update the plan with accepted changes before responding.
- **Review-only mode:** Leave the plan unchanged when the user explicitly asks for feedback without edits.

This skill changes the plan only. Use `plan-implement` when the user requests milestone execution with independent reviews; ordinary implementation does not require that workflow.

## Context and independent review

Locate and read the complete current plan and repository files needed to evaluate its assumptions and dependencies. Launch one fresh reviewer session without inherited conversation; use `fork_turns: "none"` where supported. If the environment cannot launch an independent reviewer, prepare the self-contained handoff and report that independent review is pending; do not describe self-review as independent review. The reviewer is read-only and must not edit the plan, change code, or mutate the repository.

Provide a self-contained packet with the repository location, current plan, applicable repository instructions, relevant repository context, expected behavior, acceptance criteria, and current milestone when applicable. Omit prior review history from the packet and avoid forwarding the main agent's analysis, anticipated findings, or desired verdict.

Include a few brief notes on relevant intentional behavior and accepted tradeoffs, with each decision's reason and known downside. Extract established user requirements, current plan decisions, or documented implementation rationale; do not invent retrospective justifications. Ask the user only when an unresolved decision materially affects correctness and cannot be resolved from available evidence.

Design notes are context, not exemptions. Ask the reviewer to check whether the plan honors the decisions and whether their assumptions still hold. It may challenge decisions with evidence of material problems, distinguishing a design concern from a missing or incorrect implementation step.

Let the reviewer choose how to investigate missing steps, unsupported assumptions, sequencing, contracts, validation, and material migration, compatibility, security, performance, or maintenance risks. Assess whether progress and completion can be tracked reliably without imposing unnecessary template changes.

Use reasoning effort appropriate to the scope, usually medium and higher for migration, data integrity, or runtime safety. Request concrete findings ordered by severity, with plan-section or file-and-line evidence, the triggering condition, and resulting failure or material impact. Separate demonstrated problems from unresolved questions. Missing tests alone are not a defect without identifying the behavior left unverified. No material findings is a valid result.

## Main-agent resolution

Check whether the plan preserves the original intent and any working prototype's required interface and interactions. Distinguish hard constraints, outcomes, preferences, and assumptions. Look for unnecessary scope, premature abstractions, expensive safeguards without a material failure case, and simpler sufficient approaches. Do not demand a simplification or extra feature when none is warranted. Consider both likelihood and impact of failure.

For orchestrated plans, check decision authority, submitted-versus-accepted status, milestone dependencies and worktree bases, integration ownership, proportionate review requirements, and early verification of the main uncertainty. Require only the detail needed to prevent a concrete execution error; do not impose a new bureaucracy on small plans.

When an orchestrator owns the canonical plan, return proposed changes to that owner unless explicitly assigned editing authority. This ownership rule takes precedence over default apply mode. Report proposed changes as unapplied until the owner records them.

Independently cross-check every finding against repository evidence, user requirements, and the current plan. Classify each as:

- **Accept:** Valid, material, and appropriate to address within the current scope.
- **Reject:** Unsupported, incorrect, duplicate, immaterial, or inconsistent with a justified requirement or tradeoff without demonstrating a material problem in that decision. Explain why; "by design" alone is insufficient.
- **Defer:** Valid but outside the current scope. Record the reason and impact without silently expanding the plan.

In apply mode, update the plan with every accepted finding. Use [plan-build](../plan-build/SKILL.md) for persistent plan maintenance and lifecycle while preserving useful existing structure and history. Revise steps, sequencing, acceptance criteria, validation, or risk notes as needed. Revalidate affected completion claims; do not mark proposed work completed or relax required outcomes merely to close a finding.

Re-read the updated plan for contradictions, missing dependencies, and incomplete acceptance criteria. Do not claim a finding was applied unless the plan reflects it. In review-only mode, report proposed changes instead. For an inline or unwritable plan, return concrete proposed edits and state that no file was changed.

## Final response

Report accepted findings and how they were incorporated or proposed, rejected and deferred findings with brief reasons, and any low-confidence areas or residual risks. If there are no material findings, say so without implying that code or runtime behavior was validated.
