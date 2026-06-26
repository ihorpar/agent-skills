# Corrective UI/UX Principles

Use these principles to turn a slop diagnosis into a better interface. They are defaults, not laws.

## Priority

Optimize in this order:

1. **Orientation:** Users understand where they are, what belongs together, and what can happen.
2. **Confidence:** Users can see current state, consequences, progress, errors, and recovery.
3. **Speed:** Users can complete the main task with minimal noise, travel, and recall.

## Element Test

Every visible element should answer at least one question:

- What is this?
- What can I do here?
- What is happening now?

Remove, merge, or quiet elements that answer none. Combine elements that repeat the same answer.

## Structure

- Put controls next to the content they affect.
- Group by user intent rather than implementation layer.
- Use proximity, alignment, spacing, typography, and contrast before borders or containers.
- Add a boundary only when it communicates grouping, ownership, selection, safety, or an interaction surface.
- Keep one workflow in one coherent region unless separation has clear meaning.
- Preserve a single mental model across views and breakpoints.

## State And Feedback

- Show selected, filtered, loading, saving, stale, blocked, and completed states inline.
- Make the changed result visible after important actions; do not rely on a toast alone.
- Explain why disabled controls are disabled.
- Preserve user work through failures and retries.
- Mark invalidated output as stale instead of silently discarding it when possible.
- Make errors calm, specific, actionable, and honest.

## Progressive Disclosure

- Start with the minimum interface required for the primary task.
- Keep advanced tools nearby but visually quiet.
- Do not hide choices that materially change outcomes behind a vague "Advanced" label.
- Keep destructive actions available but separated from the primary action.

## Hierarchy

- Give one element or action clear priority within a local region.
- Vary typography, spacing, and contrast according to role.
- Avoid repeating the same component treatment at every hierarchy level.
- Prefer one strong state cue over several weak duplicate cues.
- Make review, completion, export, and publish surfaces calmer than setup surfaces.

## Copy

- Let labels carry meaning; use placeholders and helper text only as support.
- Remove helper text that repeats visible context.
- Use copy to reduce a decision, explain a consequential constraint, or aid recovery.
- Prefer concrete verbs and outcomes over process narration.
- Keep terminology stable.
- Prefer an example over an abstract formatting explanation when ambiguity remains.

## Icons And Actions

- Keep text for primary, high-stakes, or unfamiliar actions.
- Use icon plus text for navigation and medium-importance utilities when both improve scanning.
- Use icon-only controls for familiar secondary actions when space is tight.
- Give icon-only controls accessible names, visible focus, and touch-safe targets.
- Do not substitute icons merely to make an interface look cleaner.

## Accessibility And Input

- Never rely on color or hover alone.
- Make focus visible and intentional.
- Assume touch-first, keyboard-possible, hover-optional for mixed-input layouts.
- Respect reduced-motion preferences while preserving necessary feedback.
- Prevent accidental destructive actions and provide recovery where prevention would add too much friction.

## Motion

- Use motion to explain entry, exit, continuity, or changed state.
- Avoid decorative motion competing with the task.
- Do not move focus, cursor position, or nearby controls while the user is typing.

## Empty And Dense States

- Empty states should explain what happened, why, and the next useful action.
- Use one empty state per empty section rather than one per field.
- Preserve stable scan anchors in dense lists and tables.
- Make selection explicit.
- Keep units visible and align comparable values consistently.
