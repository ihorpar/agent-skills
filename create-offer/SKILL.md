---
name: create-offer
description: Create, review, and rewrite client offers, proposals, and product descriptions from vague, technical, or messy input into clear client-facing commercial narratives. Use when the user wants to prepare an offer for a client, package a product or feature for sale, review offer copy, remove jargon, turn technical notes into business value, or rewrite a proposal while preserving strong result-oriented language. Works in any language and should preserve the requested or source language unless asked to translate.
metadata:
  short-description: Create and polish client offers
---

# Create Offer

Use this skill to create, review, or rewrite client-facing offers, proposals, and product descriptions. The goal is not generic marketing copy. The goal is a clear commercial narrative that a client can understand, believe, and act on.

This skill works in any language. Preserve the language requested by the user or the language of the source artifact. Do not default to Ukrainian unless the user asks for Ukrainian. Ukrainian examples are allowed when useful, but the workflow is language-agnostic.

## Core Taste

Keep the user's preferred style:

- Strong result language is allowed and often desirable.
- Do not automatically hedge outcomes if the user is intentionally selling a strong result.
- Replace internal jargon with plain client-facing language.
- Replace abstract feature descriptions with concrete user scenarios.
- Explain value through work: who opens it, what they see, what they do next.
- Make the offer more concrete, not merely shorter.
- Avoid turning the copy into vague motivational marketing.

Good pattern:

```text
The editor opens the radar, sees which topics are growing in the selected vertical, and quickly chooses stories to assign.
```

Ukrainian example:

```text
Редактор відкриває радар, одразу бачить, які теми ростуть у потрібній тематиці, і швидко відбирає сюжети в роботу.
```

## Operating Modes

Choose the mode from the user's request. If unclear, infer the most useful mode and proceed.

### 0. Context Intake

Use when the user has only a rough idea, scattered notes, a feature list, a voice-like dump, or a blurry product vision.

Ask short batches of clarifying questions until there is enough context to create the offer. Prefer 3-5 questions per batch. Do not ask a giant questionnaire all at once.

Gather enough of:

- Who the client is and who makes the decision.
- What problem the offer solves.
- What is being proposed.
- What already exists and what is new.
- What business results the user wants to sell.
- What constraints matter: budget, timeline, dependencies, integrations, access, data, approvals.
- What proof or credibility exists: previous work, current product, examples, client pain, metrics.
- What tone is needed: calm, strong sales, enterprise, friendly, technical, founder-to-founder.
- What format is needed: HTML page, deck outline, email, proposal doc, section rewrite, bullets.

Stop asking and start drafting once the offer can be structured without guessing the core business value. If a detail is missing but not blocking, state the assumption and continue.

### 1. Review

Use when the user asks to review, critique, sanity-check, or improve an existing offer without asking for a rewrite yet.

Lead with concrete findings. Look for:

- Internal jargon or technical implementation language.
- Abstract nouns that hide the real user action.
- Feature lists with no buyer value.
- Result claims with no visible mechanism.
- Modules that do not say who uses them or how.
- Mixed audiences with unclear prioritization.
- Future-vision sections that sound vague rather than phased.
- Language mixing that feels accidental.
- Over-compression that removes sales force.
- Excessive density only when it hurts comprehension for the artifact type.

Important: do not treat strong result wording as a flaw by default. If it sells and the user likes that tone, keep it and make the mechanism clearer.

Review output should usually include:

- What works.
- What is unclear.
- What sounds too internal.
- What needs a concrete scenario.
- What should be rewritten first.

### 2. Rewrite

Use when the user asks to rewrite, polish, package, create, make a presentation, make it client-facing, or implement feedback.

You may merge feedback and rewrite in one pass when the user asks for it. Do not force a separate review checkpoint unless the user specifically asked for review only.

For each offer section or product module, aim for this structure:

```text
Name
What we do
How it works in the client's workflow
Result
```

When useful, use this more compact pattern:

```text
What it is -> What the user does -> What changes for the business
```

For product modules, include at least one concrete operational scenario:

```text
Role opens X, sees Y, and does Z.
```

Examples:

```text
The release editor opens the analytics screen, sees which materials are growing, which are falling, and which should be updated instead of abandoned.
```

```text
Випусковий відкриває аналітику й одразу бачить, що росте, що просідає і які матеріали варто не списувати, а допрацьовувати.
```

## Rewrite Rules

Convert technical wording into client-facing wording:

- "analytics layer" -> "analytics screen", "analytics tool", "management view"
- "platform content" -> "content for different platforms"
- "follow-up ideas" -> "ideas for continuing the topic"
- "AI module processes data" -> "the editor opens the tool, sees the recommendation, and chooses the next action"
- "future AI vision" -> "the next phase after the core modules"
- "signals" -> use only when the audience understands it; otherwise say "topics that are growing", "changes that need attention", or "new competitor activity"

Keep strong result verbs when they are part of the sales style:

- increases
- reduces
- speeds up
- improves
- strengthens
- gives the team
- helps the client

But make the mechanism visible:

```text
Increases traffic from external platforms by preparing Telegram, Instagram, Threads, and X versions from one article immediately after publication.
```

Avoid:

- Empty claims without a workflow.
- Product-internal labels unless the client already uses them.
- Overly abstract phrases like "single operational system" unless followed by concrete actions.
- Mixed-language copy unless it is intentional or domain-standard.
- Weak hedging such as "may potentially help" when the requested style is a confident offer.

## Language Handling

- Preserve the requested language.
- If the source language and requested language conflict, ask only if it materially matters; otherwise follow the latest user instruction.
- Keep product names, platform names, and common industry terms in their natural form.
- Do not mix Ukrainian, Russian, and English casually.
- If using English terms inside another language, make sure they are familiar product terms, not avoidable jargon.

## Deliverable Shapes

Match the user's requested artifact:

- Existing text review: findings first, then suggested rewrite direction.
- Rewrite of one section: provide the rewritten section only, plus a brief note if needed.
- Full offer: produce a structured client-ready draft.
- HTML/deck copy: preserve the existing section structure unless the structure itself is the problem.
- Context intake: ask the next useful batch of questions.

When editing files, preserve the artifact's existing visual and structural language unless the user asks for a redesign.

For concrete output shapes, read [references/output_templates.md](references/output_templates.md) when the user needs:

- a modular offer page
- a product vision section
- a pricing/package proposal
- a technical-to-commercial module rewrite

For reusable rewriting patterns, read [references/rewrite_patterns.md](references/rewrite_patterns.md) when the text feels too internal, too technical, or too abstract.

## Final Quality Check

Before finishing, check:

- Can the client picture the workflow?
- Is every major feature tied to a buyer-visible result?
- Did you remove internal jargon?
- Did you keep the user's strong commercial tone?
- Is the language consistent?
- Does the offer say what happens now versus what is a next phase?
- Is the text clear enough for a decision-maker who was not in the product discussion?
