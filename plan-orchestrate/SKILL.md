---
name: plan-orchestrate
description: Coordinate a plan through fresh milestone executors, bounded decisions, evidence-based acceptance, and integration. Use for requested multi-agent or multi-thread milestone orchestration; do not select merely because a plan exists.
---

# Plan Orchestrate

Own the execution of the agreed plan while keeping implementation in bounded executor sessions. Use [plan-build](../plan-build/SKILL.md) for the canonical plan and lifecycle. Keep all plan tasks in that file; handoff packets and evidence are supporting artifacts, not parallel task lists.

## Roles and authority

- The planning agent A establishes intent with the user. Preserve that intent in the plan; neither A's memory nor the orchestrator's conversation is the only source.
- The orchestrator O is the canonical plan owner. O prepares assignments, resolves questions within authority, evaluates findings, accepts milestones, and coordinates integration. Normally O sends code fixes back to the assigned executor rather than becoming another implementer.
- A fresh executor E handles one milestone, including its follow-up fixes. E reports work and evidence but cannot accept its own milestone or rewrite canonical requirements.
- An independent reviewer R is optional according to the milestone's review requirement and newly discovered risk. R reads the exact delta and affected integration paths, returns findings, and does not edit code. O need not repeat a full review already performed; cross-check material findings and acceptance evidence.

O can choose implementation, simplify within scope, and reorder independent work. O cannot silently change hard constraints, required outcomes, or weaken acceptance to close a failure. A change in approach must have a concrete reason. Preserve existing authorization for commits, external actions, and other operations; a skill or plan edit grants no additional authority.

Assess proposed additions by the requirement served, concrete consequence of omission, simpler sufficient alternative, and cost of deferral. Consider impact as well as probability. No useful findings is a valid result. Defer unrelated improvements without making them prerequisites.

## Preparation

Read the full plan and applicable instructions. Record its revision, owner, current milestone/state, exact next action, and blocker. Verify the actual working-tree baseline and relevant dependency state before assigning work. Honor the prototype source/version and fidelity contract.

Use the environment's actual independent-session mechanism. These instructions work with different models and hosts; do not assume Codex APIs, context sizes, settings, shared filesystem, or an automatic ability to message other chats. If delegation is unavailable, generate a self-contained handoff for manual transport and wait for the real result. Do not impersonate independent agents or invent their feedback.

## Milestone cycle

1. Prepare the assignment using [handoff templates](references/handoffs.md). Include the relevant plan contract and stable artifact locations, not the accumulated chat history. Make referenced files available to the executor; identify unavailable inputs rather than assuming access.
2. Follow the plan's worktree strategy. Create a dedicated worktree when relevant, with an explicit base containing accepted dependencies and a known integration destination. Read-only work and an already suitable isolated workspace may use the recorded exception. Do not assume uncommitted changes are present in a new worktree. Coordinate any required transfer within existing authorization. Default to one writing executor; parallelize only independent work with a defined integration path.
3. Use one of two modes. **Proceed mode:** E briefly states its interpretation, checks material assumptions, and executes if nothing blocks correctness. No acknowledgement round is required. **Preflight gate:** E investigates and returns its interpretation and material questions before implementation. O resolves questions from evidence where possible; ask the user only for decisions outside O's authority. Nonblocking suggestions do not suspend authorized work.
4. E implements the milestone and performs its required checks. Request only findings that materially affect correctness, user outcomes, cost, or complexity, with evidence and a recommended action. Keep optional ideas outside implementation scope.
5. Receive E's report as `Submitted`, not `Accepted`. Ensure the actual artifacts match the reported code state. Obtain independent review when required or newly justified. A required unavailable review/check remains pending. Use [subagent-code-review](../subagent-code-review/SKILL.md) in findings-only mode when appropriate.
6. Cross-check material findings against actual code, original requirements, and accepted decisions. Accept and return fixes to E; reject with evidence; or defer with reason and impact. Rerun affected checks after fixes. Another independent pass requires material change or unresolved risk, not a demand for an empty findings list.
7. Coordinate integration into the recorded destination, respecting existing commit/merge/push authority. Resolve conflicts through E and verify affected integrated behavior. If integration is required but cannot be performed, record `Awaiting integration` and keep milestone acceptance open. A clean patch in an isolated worktree is not proof that the combined result works.
8. Accept only after applicable criteria, required review, and integration checks pass. O updates canonical checkboxes, concise evidence, decisions, and next action. Start a fresh E for the next milestone from the accepted dependency state. Retain worktrees until changes and relevant evidence are preserved; cleanup is not an automatic destructive step.

## Durable state and unattended work

The role survives a thread reset. At milestone boundaries and before stopping, save a compact checkpoint in the plan: revision, accepted/submitted work, active session and worktree references, evidence, unresolved decisions, next action, and blocker. Keep detailed logs elsewhere and link them. A replacement O rereads this state and verifies current artifacts rather than inheriting all transcripts.

Detect stale assignments: if requirements, the relevant code base, or dependencies change while E works, compare against the pinned assignment before accepting. Revalidate affected work; do not merge a stale report blindly.

For unattended execution, follow agreed time/resource limits and permitted operations. Continue independent authorized work when a user decision blocks only one branch. Save the unanswered decision and stop dependent work; silence is not approval. On repeated failure without new evidence, checkpoint and escalate or stop the attempt rather than repeating the same loop. Technical retries must not duplicate external side effects.

Prompts cannot guarantee runtime deadlines, restart recovery, budgets, or process monitoring. An external runner must enforce those when needed. Report which capabilities are actually present; do not claim overnight automation has been installed by loading this skill.

## Completion

Verify cross-milestone user flows and every applicable Definition of Done item on the integrated result. Send A a final intent-review packet with original outcomes, prototype reference, implemented behavior, material deviations, evidence, and unresolved limitations. If A is unavailable, prepare the packet; do not invent its approval. Treat any required intent review as pending until performed. New requests from A are assessed against original intent and authorized scope, not automatically added.

Use plan-build to complete and archive only when all applicable criteria are met. Report accepted work, actual validation, remaining decisions, and intentionally excluded work. Distinguish implementation complete, accepted, integrated, and deployed; never infer one from another.
