# Slop Detection Taxonomy

Use this taxonomy to detect patterns, not to enforce one visual style. Require rendered or code-grounded evidence.

## Classification

- **Violation:** Actively harms comprehension, trust, accessibility, or task completion.
- **Excess:** A legitimate pattern used so often that it weakens hierarchy or creates noise.
- **Taste:** Aesthetic preference without a strong usability claim. Record only when relevant; never auto-fix.

## Structural Slop

### Container bloat

Wrappers, cards, panels, or bordered regions that do not create a meaningful grouping, ownership boundary, or interaction surface.

### Nested framing

Cards inside cards or repeated backgrounds and borders expressing the same hierarchy.

### Detached controls

Actions placed away from the content or state they affect, forcing visual travel or ambiguity.

### Layout fragmentation

A simple workflow split across unnecessary sections, tabs, drawers, steps, or modals.

### Over-componentized forms

Small forms inflated with per-field captions, panels, footers, and repeated validation chrome.

### Spacing replaced by chrome

Borders, shadows, fills, and dividers used where proximity, alignment, and whitespace could express structure.

## Hierarchy And Visual Slop

### Uniform hierarchy

The same radius, border, padding, heading scale, or component treatment applied at every level so nothing reads as primary.

### Effect stacking

Rounded corners, borders, shadows, gradients, icon circles, and hover effects accumulated on one element without distinct meaning.

### Competing emphasis

Multiple primary buttons, highlighted panels, badges, or callouts demanding attention simultaneously.

### Pill and badge spam

Capsule styling used for ordinary metadata, field labels, navigation, filters, or micro-actions where plain text or a quieter control would scan better.

### Generic SaaS composition

Interchangeable gray-on-white cards, large radii, soft shadows, muted subtitles, metric tiles, and dashboard grids applied regardless of product task.

### Decorative motion

Animation that does not clarify hierarchy, continuity, causality, or state change.

### Token monotony

One spacing, radius, border, and typography treatment repeated mechanically rather than used to express hierarchy.

## Copy Slop

### Redundant explainers

Helper text that repeats the label, placeholder, selection, or visible behavior.

### Process narration

Copy explaining what the system will do instead of the result or consequence the user needs to understand.

### Microcopy bloat

Excess subtitles, captions, parentheticals, reassurance, and instructional notes that increase reading without reducing decision cost.

### Marketing language in product UI

Words such as seamless, powerful, smart, effortless, or AI-powered where a concrete label would communicate more.

### Instructional UI

Text compensating for an unclear layout or control when the interaction itself could be made self-evident.

### Terminology drift

Different names for the same concept across views, states, or actions.

### Placeholder-as-label

Critical meaning or format expectations placed only in disappearing placeholder text.

## Interaction Slop

### Action overload

Too many low-value or infrequent actions visible at once, weakening the primary path.

### Progressive-disclosure failure

Advanced, rare, or diagnostic controls compete with the main workflow, or consequential choices are hidden behind an undifferentiated "Advanced" area.

### Affordance mismatch

Text used where a familiar icon is clearer and more compact, or an icon used where wording is required for comprehension.

### Repeated action labels

Dense layouts repeat "Edit," "Manage," "View details," or "Click to copy" instead of using row interaction, proximity, or a lightweight familiar affordance.

### State-label duplication

Several badges, captions, icons, colors, or toasts communicate the same state.

### Toast-only feedback

The app announces success without visibly updating or confirming the affected content.

### Invisible or ambiguous state

Selection, filtering, saving, loading, staleness, disabled reasons, or completion cannot be understood at the point of interaction.

### Hover dependence

Important actions or meaning are available only through hover.

### Control travel

Users must move between distant regions to complete one tightly coupled task.

### Premature modalization

A modal or drawer interrupts a task that could be completed safely in context.

## Product-Theater Slop

### Placeholder product thinking

Generic empty states, canned sample data, or suggestions unrelated to the user’s real next step.

### AI theater

Sparkles, assistant callouts, confidence scores, insight cards, summaries, or recommendation boxes that add ceremony without decision value.

### Trust theater

Reassuring labels, security decoration, or status treatments unsupported by useful evidence or system behavior.

### Feature ceremony

A trivial operation expanded into a multi-step experience, celebratory transition, or explanatory sequence.

### Fake intelligence

Recommendations that are generic, obvious, unactionable, or disconnected from available evidence.

### Premature flexibility

Filters, customization, management surfaces, or advanced settings exposed before a credible use case exists.

## Accessibility And Resilience Slop

### Color-only meaning

Status or selection is communicated only by hue.

### Focus neglect

Keyboard focus is missing, clipped, low contrast, or visually unrelated to the control.

### Touch-hostile compactness

Icon actions or dense controls have inadequate targets or rely on precise pointer input.

### Destructive ambiguity

Destructive actions resemble ordinary actions, lack consequence clarity, or offer no practical recovery.

### Failure camouflage

Errors are replaced by generic fallback content, silent resets, or optimistic success that can be mistaken for completed work.

### Orientation loss

Sorting, filtering, refresh, generation, or responsive reflow causes users to lose their place or selection.

## Ranking Guidance

Score 0 to 3 for user impact, prevalence, primary-task interference, evidence confidence, and fix leverage.

Prefer findings that:

- Explain several visible symptoms.
- Affect the primary workflow.
- Can be corrected without speculative product changes.
- Improve orientation or confidence before cosmetic polish.

Do not inflate severity merely because a pattern looks unfashionable.
