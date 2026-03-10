# Masterplan - Project Overview (High Level)

## Overview

This file defines the overall direction, scope, and working intent for the Project Overview experience.

The Project Overview is the high-level landing page for an individual project. It should help a Project Manager (PM) or PMO quickly understand whether the project is under control, where attention is needed, and whether action is required.

This file is the primary source of truth for the overall direction of the experience. Supporting files such as `05_tasks_project_overview.md`, `04_rules_base.md`, `03_design-guidelines_base.md`, `02_user-journey_project_overview.md`, `07_screen-spec_project_overview.md`, and `09_decision-log_base.md` should align to it.

## Outcome Spec

### Audience and context

* Primary users: Project Manager (PM) and Project Management Office (PMO)
* Usage moment: This is the project landing page users see when they open an individual project
* Primary usage intent: Quickly understand whether the project is under control, where attention is needed, and whether intervention is required

### Job to be done

* Help me stay on top of my project, reduce surprises, and maintain control over delivery.

### Core user intent

The Project Overview should help the PM or PMO determine, at a glance:

* Whether the project is stable or drifting
* Whether intervention is needed now
* Which areas need attention first
* What has changed since the last review
* What action, if any, should be taken next

### Decisions supported

The page should support the following high-level decisions:

1. Do I need to escalate?
2. Do I need to reallocate resources?
3. Do I need to adjust the schedule?
4. Do I need risk mitigation?
5. Do I need stakeholder communication?
6. Do I need budget correction?
7. Do I need scope or change approval?

### Stakeholder communication — V1 scope decision

In V1, stakeholder communication is not given a dedicated visibility block or direct trigger on the Project Overview page.

The need for stakeholder communication is expected to be inferred by the user from the signals already visible across cost, schedule, scope, resources, risks, issues, dependencies, and changes.

This decision is intentional and scoped to V1. It may be revisited in a later iteration if a dedicated stakeholder communication signal is justified.

### Must-have information backbone

The page must include high-level visibility into the four core control domains:

* Cost
* Schedule
* Scope
* Resources

It must also surface the key supporting domains that may cause or explain project drift:

* Changes
* Dependencies
* Risks
* Issues

These together form the minimum information backbone for the Project Overview.

### Forecast visibility

The user must be able to understand expected project finish timing from the top-level experience without drilling down.

Forecast visibility is a top-layer requirement. It belongs in the Executive Summary and must not be deferred to a lower section.

### Scope intent

This page is intended to remain high-level. It should prioritize project control and decision support rather than deep operational detail.

The screen should support a fast first scan, followed by optional progressive reveal when the user needs more context.

### Executive Summary intent

The top layer of the page must allow the user to answer, in under roughly 30 seconds:

* Am I on track?
* Is anything critical?
* Do I need to act now?

Immediate action guidance belongs in this top summary layer rather than in a separate standalone section.

### Non-AI baseline behavior

In the non-AI state, the page should help users answer project control questions through structured, visible facts and signals. The experience should rely on clear status indicators, summaries, and direct access to the core project health dimensions:

* Cost
* Schedule
* Scope
* Resources
* Risks
* Issues
* Dependencies
* Changes

The baseline experience should enable users to judge whether action is needed without relying on AI interpretation.

### AI-augmented intent

When AI is enabled, the experience should not replace the baseline decisions. Instead, AI should improve the user's ability to:

* Intervene earlier than planned
* Detect what is likely to slip next
* Identify what is trending off track
* Understand what changed since the last review
* Focus limited attention on the highest-priority concerns
* Receive recommended actions
* Explore simulation or intervention-oriented guidance at higher maturity levels when appropriate

AI should act as a layer of support on top of the same project control model, not as a separate experience.

### AI maturity levels

The experience should support five states:

* Default / AI Off  
  No AI support. The user relies on direct project facts, status signals, and standard project controls.

* Level 1 - Descriptive  
  AI summarizes what is already happening. It helps explain the current state in plain language without interpretation beyond what is visible in the data.

* Level 2 - Diagnostic  
  AI helps explain why something may be off track by connecting visible conditions across cost, schedule, scope, resources, risks, issues, changes, and dependencies.

* Level 3 - Predictive  
  AI highlights likely future drift, likely next slippages, emerging risk, and what may worsen if no action is taken.

* Level 4 - Agentic  
  AI recommends next best actions and may help prepare intervention-oriented outputs such as draft follow-up paths, proposed actions, or simulation-style what-happens-next guidance, while keeping the human in control.

### Design intent for AI behavior

Across all AI-enabled levels:

* AI should feel supportive, subtle, and trustworthy
* AI should reduce cognitive load, not add noise
* AI should help the user focus, not intimidate them
* Each level must feel meaningfully different in purpose and value
* AI content should remain contained to the dedicated AI insight layer when enabled
* The baseline page should remain complete and usable when AI is off

### Early success criteria

This Outcome Spec will be considered successful if it enables:

* A clear separation between non-AI baseline and AI augmentation
* Prototype concepts that can be evaluated against the same decision-support goals
* Easy refinement later without rewriting the whole structure
* Consistent regeneration across tools using short prompts and stable source files

### Known gaps to refine later

This v2 spec still needs deeper definition for:

* Specific thresholds and signals for each decision
* Trust and transparency requirements
* Success and failure criteria at a more measurable level
* Exact copy and tone for each AI maturity state
* Whether simulation outputs at higher AI maturity should become a more formal pattern later

## Scope and constraints

### In scope

* A high-level Project Overview landing page for an individual project
* Decision support for PM and PMO users
* A clear non-AI baseline experience
* AI maturity layering from descriptive to agentic
* A top-level Executive Summary, optional AI insight layer, and a unified Diagnostic + Drill-down section
* Progressive reveal through expandable diagnostic cards

### Out of scope

* Deep transactional workflows
* Full project editing experiences
* Detailed configuration or admin settings
* Backend logic, integrations, and implementation specifics
* Final production-ready interaction details

### Constraints

* The page must remain high-level and scannable
* AI should enhance judgment, not overpower the user
* The experience should prioritize control, clarity, and focus
* The design should support progressive refinement over time
* The overview must not duplicate the same information across layers without good reason

## File structure

This project uses separate files with clear responsibilities:

* `01_masterplan_project_overview.md`  
  Defines the overall direction, intent, scope, and core decision-support model.

* `05_tasks_project_overview.md`  
  Breaks the work into small executable steps in the correct order.

* `04_rules_base.md`  
  Defines how the AI or generator should behave while creating or refining outputs.

* `03_design-guidelines_base.md`  
  Captures design principles, UX tone, layout behavior, and visual intent.

* `02_user-journey_project_overview.md`  
  Describes the user flow from opening the project to taking action.

* `07_screen-spec_project_overview.md`  
  Defines the page structure, interaction model, section behavior, card contract, AI placement, and what must appear where on the screen.

* `09_decision-log_base.md`  
  Records accepted stable decisions that future revisions must preserve unless they are explicitly replaced.

Each file should stay focused on its role and avoid duplicating the function of the others.

## Current assumptions

* PM and PMO users need fast project control visibility from the landing page
* The Project Overview should be useful even with AI turned off
* AI value should increase progressively across maturity levels
* The same core project control model should support both non-AI and AI-enhanced experiences
* The first version should prioritize clarity over completeness
* The same stable source files should support regeneration across multiple tools with short prompts

## Open questions

The following areas still need to be defined in later iterations:

* What trust and transparency signals must appear in the UI
* Which actions should be directly available from the overview page
* Whether quality needs a dedicated visibility block in a future version
* Whether higher-maturity simulation patterns should become more explicit in future versions

### Closed in V2

The following questions were open in the initial masterplan and have since been resolved:

* **Top decision-support layer** — the Executive Summary must answer whether the project is on track, whether anything is critical, and whether action is needed now
* **Immediate action placement** — immediate action guidance belongs in the Executive Summary rather than a separate Next Steps section
* **AI placement** — when enabled, AI appears as a dedicated layer directly below the Executive Summary and above diagnostics
* **AI containment** — AI content appears only in the dedicated AI layer, not inside the diagnostic cards
* **AI interaction model** — the AI layer is interactive through AI On/Off and in-place maturity switching; the maturity selector appears only when AI is on
* **Diagnostic structure** — the page uses one unified Diagnostic + Drill-down section rather than separate Main Health and Supporting Drift sections
* **Core vs conditional domains** — Cost, Schedule, Scope, and Resources remain always visible; supporting domains such as Risks, Issues, Dependencies, and Changes are conditionally shown when flagged or newly recovered, with a show-all option
* **Information reveal model** — diagnostic cards are collapsed by default and support progressive reveal through expand/collapse
* **Stakeholder communication visibility** — confirmed as inferred from other signals in V1, with no dedicated block
* **Forecast visibility** — confirmed as a top-layer requirement within the Executive Summary
