---
name: unslopify-frontend
description: Detect and remove generic AI-generated frontend patterns such as excessive cards, nested containers, pill spam, redundant helper text, uniform hierarchy, action overload, generic SaaS styling, and decorative AI theater. Use when asked to unslopify, simplify, declutter, critique, audit, or redesign an existing web interface while preserving its product intent and established design language. Supports quick implementation and interactive HTML audit modes with evidence-based before/after mockups.
---

# Unslopify Frontend

Improve an existing interface by identifying root causes of visual and interaction slop, then applying the smallest credible corrections. Preserve useful complexity, product identity, accessibility, and working behavior.

## Load The Right Resources

- Read [references/slop-taxonomy.md](references/slop-taxonomy.md) before every audit.
- Read [references/ui-ux-principles.md](references/ui-ux-principles.md) before proposing or implementing fixes.
- Read [references/remediation-patterns.md](references/remediation-patterns.md) when translating findings into design changes.
- Use [assets/report-template.html](assets/report-template.html) only in interactive mode.

## Choose A Mode

Honor an explicitly requested mode.

When no mode is specified:

- Use **quick mode** for a narrow, concrete request affecting a small surface.
- Use **interactive mode** for broad requests such as "unslopify this page," "improve this UI," or "redesign this flow."

State the selected mode in the first progress update.

## Establish Evidence

Inspect the real interface before judging it:

1. Read project instructions and identify the relevant routes, components, styles, and design tokens.
2. Run or open the actual app when feasible.
3. Capture the relevant viewport or inspect user-provided screenshots.
4. Check responsive behavior when the affected layout materially changes on mobile.
5. Distinguish rendered evidence from code-only inference.

Do not invent problems from generic expectations. A dense expert tool, playful consumer app, and restrained admin interface require different corrections.

## Detect And Rank Slop

Audit against the taxonomy and cluster repeated symptoms under root causes. Twelve unnecessary cards are one container-bloat finding with twelve examples, not twelve findings.

For every finding, record:

- **Problem:** the root cause, stated plainly.
- **Evidence:** visible examples and relevant source locations.
- **Impact:** how it affects orientation, confidence, speed, accessibility, or task completion.
- **Principle:** the corrective rule that applies.
- **Fix:** the smallest credible change.
- **Classification:** violation, excess, or taste.

Score each finding from 0 to 3 on:

- User impact
- Prevalence
- Primary-task interference
- Evidence confidence
- Fix leverage

Rank by total score, then by user impact. Do not auto-fix taste findings. Treat repeated low-level symptoms as one root-cause cluster.

## Quick Mode

Use the detect-then-fix sequence without pausing for approval:

1. Audit the scoped interface.
2. Select violations and meaningful excesses with strong evidence.
3. Implement the smallest coherent set of fixes.
4. Preserve existing design-system conventions unless those conventions are the diagnosed problem.
5. Verify behavior, accessibility, responsive layout, and relevant tests.
6. Summarize what changed and what was deliberately left alone.

Do not turn a targeted cleanup into an unsolicited rebrand.

## Interactive Mode

Do not edit production code before the user approves the direction.

1. Audit the whole relevant surface.
2. Rank root-cause clusters.
3. Select the three most severe distinct clusters. Avoid filling all three slots with variants of the same issue.
4. Copy `assets/report-template.html` to a temporary local artifact.
5. Replace its example content with evidence from the actual app.
6. Include a full-context before view and equally sized before/after mockups for each top finding.
7. Include the remaining audit, implementation plan, preserved behavior, risks, and unresolved decisions.
8. Present the report path with a short chat summary.
9. Wait for approval or redirection.
10. After approval, implement, verify, and remove temporary artifacts unless the user asks to keep them.

Create alternative mockups only when a real product decision remains ambiguous. Do not manufacture A/B options for decoration.

## Build Honest Mockups

- Base proposals on the actual application, not a generic replacement dashboard.
- Keep before and after at identical dimensions and comparable content/state.
- Preserve real labels, data density, navigation, and workflow constraints.
- Change only what demonstrates the proposed correction.
- Mark inferred or unavailable content honestly.
- Prefer HTML/CSS mockups or edited app components over stylized concept art.

## Apply The Correction Order

Optimize in this order:

1. Orientation: Can users tell where they are and what belongs together?
2. Confidence: Can they see state, consequences, and recovery paths?
3. Speed: Can they complete the main task without noise or travel?

Within a surface, try corrections in this order:

1. Remove redundant elements and copy.
2. Improve grouping, proximity, alignment, and spacing.
3. Clarify typography and emphasis.
4. Improve control placement and progressive disclosure.
5. Add borders, backgrounds, icons, or motion only when they communicate something the earlier steps cannot.

## Guardrails

- Do not equate minimalism with quality.
- Do not remove boundaries that communicate ownership, selection, safety, or hierarchy.
- Do not replace clear text with cryptic icons. Use icon-only controls only for familiar secondary actions, with accessible names and touch-safe targets.
- Do not hide important state or consequential decisions to make a screen look cleaner.
- Do not erase deliberate brand personality, useful density, or domain-specific controls.
- Do not introduce a new design system unless the user requested one.
- Do not rely on hover for essential information or actions.
- Do not report aesthetic preference as a usability defect.

## Self-Audit The Result

Before presenting a report or implementation, run the same taxonomy against the result.

Confirm that it does not introduce:

- New wrapper or card layers
- Repeated pills, badges, captions, or status labels
- Uniform emphasis across unrelated elements
- Redundant explanatory copy
- Generic AI or trust theater
- More visible actions than the original without clear value
- Accessibility or responsive regressions

If the report itself fails this check, simplify it before presentation.
