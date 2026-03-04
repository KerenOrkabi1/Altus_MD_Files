# Fluent UI - Base

## Purpose

This file defines the Fluent UI execution standard for AI-generated design and implementation work in this product.

It exists to make "use Fluent UI 9" more concrete and repeatable.

This file should:

* reduce generic enterprise approximation
* improve design-system consistency
* guide component choice
* distinguish prototype-level Fluent alignment from true Fluent implementation
* support smoother transition from design exploration to developer handoff

This file should be used together with:

* `03_design-guidelines_base.md` for broad UX/design policy
* `06_product-shell_base.md` for shell and host-frame constraints
* initiative-specific files such as masterplan, screen spec, tasks, and decision log

## Scope

This file applies to:

* page content generated inside the product shell
* component-system choices
* typography and spacing rules
* token-aligned color and elevation behavior
* prototype-vs-implementation expectations

This file does not define:

* product-specific business logic
* initiative-specific content hierarchy
* shell structure (that belongs in `06_product-shell_base.md`)

---

## Core implementation target

### True implementation target

When the output is intended as real implementation code, the default target is:

* **React**
* **Fluent UI React v9**
* **`@fluentui/react-components`**
* **`FluentProvider`** at the root
* real Fluent component imports where possible
* real Fluent icons where possible

A true implementation should prefer the official Fluent React package rather than recreating Fluent visually with custom HTML/CSS.

### Prototype target

When the output is intended as a design prototype or concept artifact, the result may be a:

* **Fluent-aligned prototype**

This means:

* the design follows Fluent UI 9 design-system rules as closely as practical
* the design uses Fluent-like component families and token logic
* the design may still be an approximation if the actual package is not being imported

A Fluent-aligned prototype is **not** the same as a true Fluent implementation.

### Required distinction

AI must clearly state which of the following it is producing:

* **Fluent-aligned prototype**
* **True Fluent implementation**

It must not imply real package fidelity if it is only approximating Fluent visually.

---

## Token-first rule

Fluent UI should be treated as a **token-based design system**, not as a loose visual style.

When generating designs or code:

* prefer token-based logic over ad hoc visual choices
* use consistent rules for color, typography, spacing, and elevation
* avoid decorative styling that does not map to system meaning
* prefer consistency and clarity over custom visual expression

When exact tokens are not available in the generation environment:

* approximate the Fluent token model as closely as practical
* remain consistent across the whole screen
* do not mix multiple unrelated visual systems

---

## Typography

### Default typeface

Use a Fluent-aligned Windows/web typeface by default:

* **Segoe UI Variable**
* fallback: **Segoe UI**, system sans-serif

Do not introduce a different primary typeface unless explicitly requested.

### Typography ramp

Use the following web/Windows Fluent-aligned starter ramp by default:

* **Caption 1 Regular** = 12px / 16px
* **Caption 1 Strong** = 12px / 16px
* **Body 1 Regular** = 14px / 20px
* **Body 1 Strong** = 14px / 20px
* **Subtitle 2** = 16px / 22px
* **Subtitle 1** = 20px / 26px
* **Title 3** = 24px / 32px
* **Title 2** = 28px / 36px

### Usage guidance

* Use **Body 1 Regular** for standard body content by default.
* Use **Body 1 Strong** for emphasized body content.
* Use **Caption 1** for metadata, helper text, secondary labels, and low-prominence detail.
* Use **Subtitle 2** for section labels and medium-priority headings.
* Use **Subtitle 1** for more prominent section titles where stronger hierarchy is needed.
* Use **Title 3** and **Title 2** sparingly for page-level emphasis and high-priority summary signals.

### Readability and accessibility

Typography should support clear legibility and contrast:

* standard text should meet accessible contrast expectations
* large text may use lower contrast thresholds only where appropriate
* do not use low-contrast decorative text for meaningful content

---

## Spacing and layout rhythm

### Base spacing rhythm

Use a **4px base rhythm**.

Preferred spacing steps:

* 4px
* 8px
* 12px
* 16px
* 20px
* 24px
* 32px

### Layout rule

* use consistent spacing between related elements
* align sections and cards to a stable grid rhythm
* avoid arbitrary margins and uneven visual gaps
* keep the layout calm, structured, and predictable

### Grid intent

For larger web layouts:

* prefer consistent column alignment
* keep cards and sections aligned to a repeatable grid structure
* avoid visually unstable widths unless there is a clear reason

---

## Color system

### Color logic

Color should follow system meaning first.

Use color for:

* semantic status
* hierarchy
* emphasis
* active state
* accessible differentiation

Do not use color as decoration without meaning.

### Color groups

Use the following logic:

* **Neutral** = surfaces, text, structure, separators
* **Brand** = primary emphasis, active state, selected state, primary actions
* **Status** = success, warning, danger, info
* **Generic** = only when needed for specific domain use that still remains system-consistent

### Semantic usage

* **Success / stable / on track** → success color
* **Warning / at risk / attention needed** → warning color
* **Critical / blocked / error** → danger color
* **Primary actions / selected states / active navigation** → brand color
* **Structure and non-semantic surfaces** → neutral colors

### Color discipline

* preserve a clear contrast hierarchy
* do not overload the UI with too many colored surfaces
* keep most structure neutral and reserve color for meaning
* avoid mixing non-system colors that make the page feel visually inconsistent

---

## Elevation and shadows

### Elevation rule

Use restrained elevation by default.

* prefer low-elevation surfaces
* use subtle shadows for cards and elevated panels
* avoid heavy stacked shadows
* avoid dramatic visual depth that breaks Fluent’s calm system feel

### Shadow discipline

* use a small number of consistent shadow levels
* keep neutral surfaces on neutral shadow logic
* on colored surfaces, use brand-aligned shadow handling only when necessary
* do not invent one-off shadow recipes for decorative effect

### Surface behavior

* most information surfaces should feel stable and lightweight
* hover elevation should be subtle
* emphasis should come from hierarchy and structure first, not from exaggerated shadow

---

## Component-family preference

When generating screens or code, prefer the following Fluent component families before inventing custom equivalents.

### Core component preference order

1. **Text**
2. **Button**
3. **Badge**
4. **Tag**
5. **Card**
6. **ProgressBar**
7. **TabList / Tab**
8. **Menu / MenuButton**
9. **Avatar**
10. **MessageBar**
11. **Divider**
12. **Tooltip**

If a suitable Fluent component exists, prefer that over a custom component.

---

## Component usage rules

### Text

Use Fluent text patterns for readable, consistent typography.

Use text presets and the type ramp consistently:

* Body text for standard content
* Caption for metadata/supporting detail
* Subtitle / Title for structured hierarchy

Do not create arbitrary text sizing without a clear hierarchy reason.

### Button

Use **Button** for actions.

* Use buttons for a single action or event.
* Use a link for navigation when the action is actually movement to another destination.
* Prefer clear button hierarchy:

  * primary
  * secondary
  * subtle / ghost
  * destructive only when needed

Do not overuse primary buttons.
Do not turn all actions into equal-weight CTAs.

### Badge

Use **Badge** to communicate status or short contextual meaning near related content.

Use Badge for:

* status labels
* compact state signals
* lightweight emphasis

Do not use Badge as a decorative label with no meaning.

### Tag

Use **Tag** for compact labeled items, counts, filters, or lightweight metadata chips.

Use Tag when:

* the content is short
* the label is categorical
* the pattern behaves like a structured label rather than a status signal

Do not confuse Tag with Badge when semantic status is the real purpose.

### Card

Use **Card** as the primary content surface for grouped information.

Use Card for:

* grouped signals
* section-level summaries
* compact structured content blocks
* drill-down entry surfaces

Cards should:

* remain calm and structured
* use restrained elevation
* not become overly decorative panels

### ProgressBar

Use **ProgressBar** for measurable progression or completion.

Use it for:

* actual progress
* completion state
* quantified movement toward a goal

Do not use it as a decorative line when no real progress meaning exists.

### TabList / Tab

Use **TabList / Tab** to switch between related categories or views.

Use tabs when:

* content is related
* the user is moving between peer views in the same context

Do not use tabs as a substitute for broader navigation that should really be links or page navigation.

### Menu / MenuButton

Use **Menu** for hidden actions revealed from a trigger.

Use it when:

* the actions are related
* they are secondary or overflow actions
* they should not all appear inline

Do not use Menu for data entry.
Do not hide primary actions in a menu if they should be directly visible.

### Avatar

Use **Avatar** to represent a person, team, or identity.

Use it for:

* people
* ownership
* user/account identity
* lightweight identity context

Where relevant, Avatar may support status or activity context.

### MessageBar

Use **MessageBar** to communicate important state, warning, success, or blocking information tied to the current page or surface.

Use MessageBar when:

* the user needs to notice a meaningful state
* the content is relevant to the current page/task
* the message should remain visible within the flow

Do not use MessageBar as a decorative banner.
Do not replace a destructive blocking dialog with a MessageBar.

### Divider

Use **Divider** to:

* separate content groups
* create visual rhythm
* reinforce hierarchy

Use Divider sparingly and intentionally.
Do not add dividers everywhere just to create visual clutter.

### Tooltip

Use **Tooltip** for supplemental, non-essential information.

Use Tooltip when:

* the information helps clarify
* the UI remains understandable without it
* the content is short and plain

Do not use Tooltip for:

* critical system feedback
* long explanatory content
* core content that should be visible by default

---

## Custom component rule

### Custom is allowed only when necessary

Custom structures are allowed only when:

* Fluent has no suitable component or pattern
* the domain problem is truly specific
* the custom pattern still remains visually compatible with Fluent

### Custom must still align

When a custom pattern is necessary:

* build it on Fluent-like surfaces, spacing, typography, and semantic logic
* do not introduce a visually foreign mini-design-system
* extend Fluent foundations rather than replacing them

### Examples of acceptable custom patterns

Examples may include:

* a domain-specific stage strip
* an AI-specific insight composition
* a structured signal group that combines multiple Fluent primitives

Even in these cases:

* use Fluent-aligned text
* use Fluent-aligned spacing
* use Fluent-aligned status logic
* use standard components inside the custom composition where possible

---

## Interaction and state behavior

### Interaction consistency

Interactive elements should:

* have clear hover states
* have visible focus treatment
* communicate active/selected states clearly
* not rely on color alone when another cue is needed

### State discipline

Use interaction and status states consistently:

* default
* hover
* active / selected
* disabled
* focused
* error / warning / success where applicable

Do not invent unique state treatments per component unless required by a strong product reason.

---

## Navigation and action hierarchy

### Action hierarchy

Prefer:

* one primary action
* a small number of secondary actions
* low-prominence tertiary / overflow actions

Do not make all actions compete visually.

### Navigation vs action

Keep the distinction clear:

* use **links** for navigation
* use **buttons** for actions
* use **tabs** for related peer views
* use **menus** for grouped hidden actions

This distinction should remain clear in both prototypes and implementation drafts.

---

## Shell compatibility rule

The product shell may contain product-specific patterns that are not purely standard Fluent components.

That is acceptable.

However:

* page content inside the shell should still follow Fluent UI rules
* custom shell framing should not justify random custom design inside the content canvas
* the shell may be Altus-specific, while the content system remains Fluent-aligned

This is especially important for:

* cards
* status surfaces
* action patterns
* tabs within the page content
* alerts and secondary feedback

---

## Prototype vs implementation truth

### Fluent-aligned prototype

A Fluent-aligned prototype:

* follows Fluent component families
* follows token logic
* follows Fluent typography and spacing discipline
* may still be HTML/CSS or approximate artifact code
* may not use the real Fluent React package

This is valid for:

* design validation
* stakeholder review
* concept testing
* shell/content alignment checks

### True Fluent implementation

A true Fluent implementation:

* uses React
* imports from `@fluentui/react-components`
* uses `FluentProvider`
* uses real Fluent components wherever practical
* uses actual Fluent icons where possible
* uses actual themes/tokens rather than only visual approximation

This is the standard for:

* implementation-oriented code generation
* developer-reusable output
* code handoff experiments

### Mandatory reporting rule

When AI generates a UI or code artifact, it should explicitly state:

* whether the output is prototype-only
* whether it is a Fluent-aligned prototype
* whether it is a true Fluent implementation
* which parts are custom or approximated

It must not blur these distinctions.

---

## Reporting requirement for AI runs

When AI generates a screen using this file, it should report:

1. Which Fluent component families were used (or intended)
2. Which parts are custom
3. Which parts are approximated
4. Whether the output is prototype-only or true implementation
5. Whether the output remained aligned to this Fluent file

This makes the workflow more inspectable and easier to review.

---

## What AI must avoid

AI must not:

* treat Fluent as a vague visual mood only
* invent custom UI when a suitable Fluent component exists
* use decorative shadows, color, or type scaling that breaks system consistency
* collapse the difference between a prototype approximation and true implementation
* create a visually polished but system-inconsistent screen
* use non-semantic color decoration in place of meaningful status logic
* overload the interface with too many competing visual accents

---

## Reuse rule

This file is intended to be reusable across multiple initiatives in the same product.

Initiative-specific files may:

* add local component priorities
* add domain-specific custom patterns
* define page-specific exceptions

But they should not override the core Fluent rules in this file without a deliberate accepted decision.
