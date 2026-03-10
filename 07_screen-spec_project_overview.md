# Screen Spec - Project Overview (V2 Contract)

## Purpose

This file defines the active screen contract for the Project Overview experience.

It is the screen-level specification used to generate and refine the Project Overview page with reduced design drift across tools. It defines what must remain true in the current approved screen model, even if some visual detail remains open for later refinement.

This file should work with:

* `01_masterplan_project_overview.md`
* `02_user-journey_project_overview.md`
* `03_design-guidelines_base.md`
* `04_rules_base.md`
* `06_product-shell_base.md`
* `09_decision-log_base.md`
* `10_fluent-ui_base.md`

## Screen identity

* Screen name: **Project Overview**
* Screen type: **High-level landing page for an individual project**
* Primary users: **Project Manager (PM)** and **PMO**
* Primary usage moment: **Open an individual project and quickly assess control, stability, and need for intervention**

## Core screen job

This screen must help the user quickly determine:

* Am I on track?
* Is anything critical?
* Do I need to act now?
* What is driving the issue?
* How serious is it?
* Where is the problem coming from?
* Where do I fix it?
* What must be updated?

The page should feel calm, high-signal, and decision-support oriented.

## Host layout dependency

This screen must be generated inside the host product frame defined in `06_product-shell_base.md`.

That means:

* the left navigation shell already exists
* the top product area already exists
* this file defines the page content inside the remaining content canvas

The shell is not part of the editable page body for this screen.

## Active design principle

The current screen model should optimize for:

* fast scanability
* stable information hierarchy
* confidence in project control
* clear drill-down paths
* progressive reveal rather than dense inline detail
* subtle AI augmentation without overpowering the baseline experience

This page should remain a high-level overview, not a deep operational workspace.

## Required outcome

The generated version must:

* remain high-level
* support fast project health assessment
* surface attention areas clearly
* preserve a clear separation between baseline project facts and AI support
* provide enough visibility to decide whether further investigation or action is needed
* support both stable and at-risk project states without changing the page model

## Required information backbone

The screen must visibly cover the minimum backbone defined by the project direction.

### Core domains

* Cost
* Schedule
* Scope
* Resources

### Drift domains

* Risks
* Issues
* Dependencies
* Changes

These items must be represented in the experience either as visible cards in the Diagnostic + Drill-down section or through an explicit reveal pattern such as **Show all domains**.

## Primary hierarchy

The screen uses a three-part hierarchy plus drill-down behavior:

* **Layer 1 — Executive Summary**  
  The fastest factual assessment layer. Must answer the top questions in under 30 seconds without requiring drill-down.

* **Layer 2 — AI Insight Layer (optional)**  
  Visible only when AI is enabled. Sits directly below the Executive Summary. Provides AI-specific interpretation based on the selected maturity level.

* **Layer 3 — Diagnostic + Drill-down**  
  A unified domain section that helps the user understand severity, source, cause, and path to fix.

* **Drill-down destination**  
  Deeper operational detail is reached by navigation from the overview rather than being fully exposed inline.

This hierarchy replaces the earlier split between Main Health Domains, Supporting Drift Domains, AI Support Layer, and a separate Next Steps section.

## Above-the-fold expectation

The area above the fold must allow the user to answer the first three questions without scrolling:

* Am I on track?
* Is anything critical?
* Do I need to act now?

This area must include:

* the overall project health signal
* forecast visibility — the user must be able to understand expected project finish timing from the top-level experience without drilling down
* any immediately critical flags
* a clear immediate-action signal when action is needed

Forecast visibility is a top-layer requirement. It must be present in the Executive Summary, not deferred to a drill-down view.

## Required screen sections

The active page model should include the following sections inside the content canvas.

### 1. Executive Summary

A top summary area that helps the user understand the current overall state in under 30 seconds.

This section must:

* summarize the project status at a glance
* signal whether the project appears stable or drifting
* help the user quickly judge if intervention may be needed
* include forecast visibility so the user can understand expected project finish timing from the top-level experience
* include the immediate-action answer to **Do I need to act now?**

This section should answer:

* Am I on track?
* Anything critical?
* Do I need to act now?

This section may include a concise summary pattern, a status band, or a compact health overview, but it must stay calm and not dominate the full page.

### Executive Summary action rule

A separate standalone **Next Steps** section is no longer required in the active model.

Instead:

* the Executive Summary should state whether immediate action is required
* if action is required, it should present **one primary next action** and may include **one or two secondary follow-ups**
* deeper fix destinations belong in the Diagnostic + Drill-down section, not as a standalone action block

### 2. AI Insight Layer

A dedicated AI section that appears directly below the Executive Summary only when AI is enabled.

This section must:

* sit on top of the same project control model, not replace it
* remain visually and functionally subordinate to baseline project facts
* use the same container area across all AI maturity levels
* update in place when the user changes the active AI maturity level
* keep AI-generated content contained to this section only

When AI is off:

* no AI section is shown
* no placeholder AI content is shown in its place
* the AI level selector is not shown

When AI is on:

* the AI section becomes visible directly under the Executive Summary
* the AI level selector becomes visible
* only one maturity view is shown at a time
* changing the maturity level updates the AI content in place
* switching maturity levels must not restructure or replace the baseline non-AI sections

### AI containment rule

AI-generated content must remain contained to the AI Insight Layer.

That means:

* no AI summary inside domain cards
* no AI explanation embedded inside Executive Summary factual content
* no AI-generated card-level commentary in the Diagnostic + Drill-down section

The baseline page must remain fully usable with AI off.

### AI maturity behavior in the screen

The page must support the following AI maturity states:

* **AI Off**  
  No AI-generated content is shown on the page. The user relies entirely on direct project facts and status signals.

* **Level 1 — Descriptive**  
  AI summarizes the current project state in plain language. It describes what is visible without interpretation beyond the data.

  This level should:
  * highlight the most important visible signals
  * restate the current state in simpler language
  * avoid causal reasoning
  * avoid predictive language
  * avoid advanced recommendations beyond what is already obvious from visible facts

* **Level 2 — Diagnostic**  
  AI explains why something may be off track by connecting signals across cost, schedule, scope, resources, risks, issues, dependencies, and changes.

  This level should:
  * identify likely drivers behind the current status
  * connect signals across multiple domains where useful
  * explain where instability is likely coming from
  * rank or prioritize likely causes where possible
  * avoid future simulation as the primary behavior

* **Level 3 — Predictive**  
  AI highlights likely future drift, likely next slippages, and emerging risks based on patterns and recent signals.

  This level should:
  * highlight what may worsen next if nothing changes
  * surface likely future drift or slip patterns
  * use probability or confidence language where appropriate
  * remain insight-oriented rather than autonomous

* **Level 4 — Agentic**  
  AI suggests the next best action and may help prepare follow-up steps, interventions, or response paths, while keeping the human in control.

  This level should:
  * recommend the next best action
  * suggest intervention options or response paths
  * identify who or what may need follow-up
  * support simulation, comparison, or recommended-action framing where useful
  * keep the human as the decision-maker
  * avoid presenting autonomous action as if it has already happened

### AI interaction rule

The AI layer is interactive.

It must support:

* AI On / Off state
* in-place switching between supported AI maturity levels when AI is enabled
* clear selected-state treatment for the active maturity level
* one maturity state visible at a time

The exact control pattern may vary by implementation or prototype, but the behavior contract must remain stable.

## 3. Diagnostic + Drill-down

A unified domain section that helps the user understand what is wrong, how serious it is, where it is coming from, and where to go fix it.

This section must:

* provide the main diagnostic view of the project
* avoid duplicating the Executive Summary
* support fast scan in collapsed mode
* support deeper inspection through expansion and drill-down
* provide a clear path from signal to destination

This section should answer:

* What is driving the issue?
* How serious is it?
* Where is the problem coming from?
* Where do I fix it?
* What must be updated?

### Diagnostic section composition

The section should use one unified domain model with two visibility tiers.

#### Always-visible core domains

The following four domains must always be shown:

* Cost
* Schedule
* Scope
* Resources

These domains should appear first in the section.

#### Conditional drift domains

The following domains are conditionally visible:

* Risks
* Issues
* Dependencies
* Changes

These domains should be shown when:

* they currently have a meaningful issue or flagged condition
* or they have turned green since the last review and should be surfaced as recovered/improved

A **Show all domains** control should allow the user to reveal the full set when needed.

### Diagnostic non-duplication rule

The Diagnostic + Drill-down section must not duplicate the Executive Summary.

That means:

* Executive Summary = top-level status, criticality, and immediate action signal
* Diagnostic cards = evidence, severity, source, cause, and fix path
* the same KPI or sentence should not be repeated across both sections unless needed for comprehension

## Diagnostic card contract

Each visible domain should use a compact card pattern.

### Collapsed state

Each collapsed card must show:

* domain title
* a small RAG status dot beside the title representing the current domain status
* a trend cue beside or near the title
* the top 3 signals for that domain
* an expand affordance

The collapsed state must support fast scan without requiring expansion.

### Title and status rules

The title area should include:

* the domain name
* a small current-state RAG indicator
* a trend cue that signals the recent direction of change

The RAG indicator reflects **current status only**.

The trend cue reflects recent movement such as:

* worsening
* unchanged
* improving
* recovered

**Recovered** should be used when a domain has turned green since the last review and is still worth surfacing as a meaningful change.

### Top 3 signal rule

The top 3 signals should remain concise and high-value.

A good default pattern is:

* one key problem or state signal
* one severity or impact signal
* one change or trend signal

The exact content may vary by domain, but the pattern should remain compact and easy to scan.

### Expanded state

When expanded, a card may reveal:

* 2–4 additional diagnostic details
* 1–3 relevant drill-down links
* a short high-level statement of what needs updating
* optional owner, date, or changed-since-last-review context where useful

Expanded content must remain high-level enough for an overview page. It must not become a full detailed workspace.

### Expand / collapse behavior

Diagnostic cards must support explicit expand / collapse interaction.

The interaction contract is:

* cards are collapsed by default
* users can expand a card to reveal more relevant diagnostic information
* users can collapse the card again after review
* the page must still be useful without expanding any card
* expanded state should help the user decide where to go next, not complete all work inline

### Drill-down link rule

Expanded cards may expose multiple relevant destinations when needed.

For example, a schedule card may link to:

* schedule detail
* milestone detail
* dependency detail

Use links for navigation destinations and keep action hierarchy clear.

### What needs updating rule

When a card indicates what needs updating, it should do so at a high level.

For example:

* baseline dates need review
* dependency ETA needs confirmation
* forecast cost needs refresh

The overview should identify the update need, but the actual update work happens in the destination area rather than inside the card.

## Section ordering rule

The active page must follow this section order:

1. Executive Summary
2. AI Insight Layer (only when AI is on)
3. Diagnostic + Drill-down

This order is the current stable screen model.

## Interaction requirements

The screen must support the following interaction behavior:

* fast scan without mandatory interaction
* stable section boundaries so users can predict where information lives
* optional AI-assisted interpretation when available
* in-place AI maturity switching when AI is enabled
* expandable/collapsible diagnostic cards
* clear clickable or navigable drill-down paths into detailed areas
* progression from awareness to action without requiring AI
* visibility control for hidden healthy domains through **Show all domains**

## Layout expectations

The layout should:

* fit naturally inside the existing product shell
* use an enterprise-style information hierarchy
* support quick left-to-right and top-to-bottom scanning
* use cards, panels, sections, or similar structured containers where helpful
* avoid dense walls of text
* preserve a calm, controlled visual rhythm
* keep AI visible but clearly subordinate to factual project information

## Locked constraints for the current model

Unless explicitly changed by a later approved revision, AI must preserve these constraints in generated versions:

* the page remains a high-level overview, not a detailed workspace
* Executive Summary remains the top factual assessment layer
* the AI layer appears only when AI is on and sits below the Executive Summary
* AI content remains contained to the AI layer only
* the Diagnostic + Drill-down section remains unified rather than split into separate main-health and supporting-drift sections
* the four core domains remain always visible
* conditional drift domains remain filtered by issue or recovery state unless the user reveals all domains
* the page must include a clear path from signal to drill-down destination
* the design must align to the host product shell and existing product patterns

## What AI must not do

When generating or revising this screen, AI must not:

* redesign the product shell
* omit one of the four core domains without an explicit approved reason
* reintroduce a separate standalone Next Steps section unless explicitly requested
* place AI-generated content inside domain cards
* replace direct factual visibility with AI-only summaries
* show all AI maturity levels at once in the same content area
* create a visually noisy or overly promotional AI experience
* introduce an entirely new page model that feels disconnected from the existing product
* turn the page into a deep operational screen with excessive inline detail

## Demo and prototype scenario note

For testing and prototype comparison, the screen should work for at least these conditions:

### Demo-state behavior

Healthy, At-risk, and Recovered states are alternate sample states for the same Project Overview design.

They may change content, statuses, trends, and action-needed signals, but must not change the page structure.

AI controls remain separate from demo-state variation:
- AI On / Off controls whether the AI Insight Layer is shown
- AI maturity controls the type of AI content shown
- project-state variation controls the example data only

### Scenario A — Healthy / stable project

The page should support a project that is broadly on track.

Expected behavior:

* Executive Summary confirms stability
* no immediate action is required
* core domains may still show mild watch-outs without creating false urgency
* AI should reinforce confidence without manufacturing drama

### Scenario B — At-risk project

The page should support a project with meaningful issues.

Expected behavior:

* Executive Summary shows clear concern and immediate action signal where needed
* at least one core domain is off track
* one or more drift domains explain or contribute to the issue
* AI should clarify the issue and help prioritize attention

### Scenario C — Recovered / improving project

The page may also support a project where a previously problematic domain has turned green.

Expected behavior:

* a recovered domain may still be surfaced in the Diagnostic section
* the trend cue should indicate recovery or improvement
* the page should help the user distinguish between stable healthy state and newly recovered state

These scenarios are included to support prototype evaluation and cross-tool testing. They do not change the structural rules above.

## Intentional open items for later refinement

The following may still be refined later without changing the core screen model:

* exact visual treatment of the Executive Summary
* exact visual treatment of the AI level control
* exact card styling and density
* exact iconography for trend cues and domain links
* exact motion or transition behavior for expand/collapse and AI switching
* detailed threshold definitions for each domain signal
* trust and transparency requirements for AI explanations

## Success criteria for review

The current screen contract is successful if a reviewer can confirm that:

* the screen feels native to the existing product
* the first 30-second questions are answerable quickly
* the Executive Summary provides a clear immediate-action signal
* AI appears only when enabled and updates correctly by maturity level
* diagnostic cards are easy to scan in collapsed mode
* expanded cards provide useful additional context without becoming dense
* the page supports both healthy and at-risk scenarios
* the page feels structured, calm, and trustworthy
* the page supports judgment first and drill-down second
