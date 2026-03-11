# Design Guidelines — Base

## Purpose
This file defines the shared design guidance that should be reused across initiatives.

It is a base file intended to support consistency across products and features. Initiative-specific design decisions can extend this guidance when needed, but should not contradict it without a clear reason.

## Design foundation
- Use **Fluent UI 9** as the default component foundation for product experiences.
- Align visual and interaction decisions to the existing product’s current patterns, look and feel, and user expectations.
- When improving a small part of an existing product, prefer continuity with the current product experience unless there is a clear usability reason to improve the pattern.
- Use existing approved product patterns before introducing new one-off patterns.

## Component usage
- Start with Fluent UI 9 components first.
- Prefer using Fluent components as-is where they meet the need.
- If a component needs adjustment, keep the behavior recognizable and consistent.
- Do not introduce custom components unless the default Fluent option or existing approved product pattern does not meet the functional or usability need.
For detailed Fluent UI 9 component, token, and prototype-versus-implementation rules, refer to `10_fluent-ui_base.md`.

## Customization policy
Use the following order of preference:

1. Use Fluent UI 9 as-is
2. Apply minor styling adjustments while preserving clarity, accessibility, and recognizability
3. Introduce a custom pattern only when the default option is not sufficient

When introducing a custom pattern:
- State why the existing Fluent or approved product pattern was not enough
- Keep the solution consistent with the rest of the product
- Avoid creating a one-off variant when an existing reusable pattern can be applied
- Reuse previously approved customizations instead of creating new alternatives for the same UI problem

If a custom pattern proves useful more than once, document it in the shared `design-guidelines_base.md` so it can be reused across future initiatives.

## Working with existing product patterns
- When updating or extending an existing product, align first to the established visual language, interaction model, and content behavior of that product area.
- If the existing product already uses an approved custom pattern, prefer matching that pattern unless there is an intentional decision to improve it.
- Do not introduce a visually or behaviorally inconsistent solution unless the improvement is clearly justified.
- When an improved pattern replaces an older one, document the new preferred pattern in the shared design guidance.

## Visual consistency
- Use a clear and predictable hierarchy.
- Prioritize clarity over decoration.
- Keep visual emphasis proportional to importance.
- Avoid unnecessary variation in common UI elements.
- The same UI problem should use the same pattern across initiatives unless there is a clear reason to diverge.

## Typography
- Use the default Fluent typography approach as the baseline.
- Keep headings, labels, and body text roles consistent.
- Prefer readable, scannable text over dense paragraphs.
- Avoid introducing custom typography patterns unless needed for an established product requirement.

## Color and theming
- Use the existing product theme and Fluent-aligned color behavior as the baseline.
- Prefer semantic and consistent use of color for status, alerts, and emphasis.
- Do not introduce ad hoc colors without a documented reason.
- Keep color usage aligned with accessibility and readability requirements.

## Spacing and layout
- Use a consistent spacing rhythm across screens and components.
- Prefer layouts that support fast scanning and clear hierarchy.
- Use progressive disclosure when more detail is needed.
- High-level views should surface critical information first and detailed information second.

## Reusable diagnostic card pattern
Use a consistent diagnostic card structure across initiatives when surfacing domain health, status detail, or drill-down summary, unless a screen spec explicitly overrides it.

### Card structure
Collapsed state should show:
- title
- status indicator (for example RAG)
- trend
- exactly 3 key bullets
- a visible “Needs updating” section

Expanded state should:
- retain all collapsed content
- add exactly 2 additional bullets between the first 3 bullets and the “Needs updating” section
- add links or drill-down references

### Content model
The first 3 bullets should represent **what is happening now**. These should prioritize:
1. current state or problem
2. impact, severity, or exposure
3. recent movement, change, or trend

The additional 2 bullets should represent **why the condition exists or what is constraining resolution**. These should prioritize:
1. key cause, dependency, blocker, or driver
2. pending condition, unresolved constraint, or follow-up context

The “Needs updating” section should represent a factual update, review, confirmation, correction, or formalization needed in the underlying project data, record, or control process.

### Trust and source rule
Diagnostic card content must remain factual and based on available project or product data.

Diagnostic cards must not contain:
- AI-generated interpretation
- AI-generated prediction
- AI-generated recommendation

AI-generated reasoning belongs only in a clearly separated AI layer or equivalent AI-designated area.

### Reuse rule
When the same domain-health card problem appears across multiple initiatives, reuse this structure by default instead of inventing a new card pattern.

## Content behavior
- Use clear, direct labels.
- Prefer consistent terminology across products and initiatives.
- Keep text concise unless additional explanation materially improves clarity.
- Avoid repeating the same message in multiple places unless the repetition is intentional and useful.

## AI-specific design behavior
- AI should feel subtle, supportive, and trustworthy.
- AI should not visually overpower the core product content.
- AI signals should help users focus attention, not create anxiety.
- Use consistent visual treatment for AI summaries, recommendations, and alerts across initiatives.
- Distinguish AI-added content clearly enough that users understand what was generated or inferred.

## Accessibility
- Maintain readable hierarchy and sufficient contrast.
- Support clear focus states and keyboard-friendly interaction patterns.
- Handle truncation intentionally so important information is not hidden without a way to access it.
- Prefer patterns that reduce cognitive load and improve scanability.

## Reusable pattern evolution
- Treat this file as a living shared standard.
- Update it when a design issue repeats, a better pattern is proven, or a known mistake should be prevented in future work.
- Add successful repeatable patterns back into this file so future initiatives can reuse them.
- Add recurring mistakes or weak patterns as explicit anti-patterns when useful.

## Anti-patterns to avoid
- Creating one-off custom components for common UI problems without a clear reason
- Over-emphasizing secondary content so it competes with primary task information
- Introducing inconsistent interaction patterns for similar tasks
- Adding visual noise that reduces scanability or confidence
- Allowing AI-generated content to feel more important than the core product state
