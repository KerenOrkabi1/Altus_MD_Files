# Demo Test Scenarios — Base

## Purpose
This file defines reusable demo and test scenarios for evaluating AI-generated product designs, prototypes, and screen outputs across tools.

It is intended to support:
- short-prompt generation against stable files
- comparison across different AI tools
- review of whether a design works in calm, problematic, and improving states
- checking whether AI maturity behavior is meaningfully distinct

This file is a testing and generation companion file.
It is not a source of product truth.
It does not replace the masterplan, screen spec, or decision log.

## Role in the File System
Use this file when:
- generating demo or prototype outputs
- testing whether a screen behaves correctly under different project states
- comparing outputs across Claude, Lovable, Figma Make, or other tools
- checking whether AI On/Off and maturity-level behavior is working as intended

Do not use this file to:
- redefine initiative purpose
- override the screen structure
- introduce product logic that belongs in initiative-specific files
- replace real production data definitions

## How to Use This File
When generating a demo or prototype:
1. Use the active initiative files as the source of truth.
2. Use this file to select the scenario state to demonstrate.
3. Adapt domain names, signals, and examples to the initiative context.
4. Preserve the structure, rules, and interaction model defined in the active files.

## Core Scenario Set
This base file starts with three reusable scenario types:
- Healthy / On Track
- At Risk / Needs Action
- Recovered / Recently Improved

These scenarios should be supported by both:
- baseline non-AI screen behavior
- AI-enabled screen behavior across maturity levels

---

## Scenario 1 — Healthy / On Track

### Intent
Demonstrate a project or initiative that is stable, under control, and not currently demanding urgent intervention.

### What the user should conclude quickly
- I am on track.
- Nothing critical is happening right now.
- I do not need to act immediately.

### Expected Executive Summary behavior
The executive summary should:
- clearly confirm the overall state is healthy
- avoid creating unnecessary urgency
- show no critical intervention signal
- keep the message calm and concise

### Expected Diagnostic behavior
Diagnostics should:
- show the core domains in a mostly healthy state
- avoid cluttering the screen with unnecessary negative emphasis
- optionally show mild watch-outs if they are relevant
- avoid making healthy states look suspicious or unstable without reason

### Expected AI behavior by maturity level
- **AI Off**: no AI section visible
- **Descriptive**: summarize the healthy state without adding concern
- **Diagnostic**: explain why the state appears stable, if relevant
- **Predictive**: identify only realistic watch-outs, not invented risk
- **Agentic**: recommend continued monitoring or light follow-up only when justified

### What should not happen
- AI should not manufacture drama
- diagnostics should not over-index on minor noise
- the screen should not imply urgent action when none is needed

---

## Scenario 2 — At Risk / Needs Action

### Intent
Demonstrate a project or initiative that has meaningful drift, requires attention, and should guide the user toward action.

### What the user should conclude quickly
- I am not fully on track.
- Something important is wrong or drifting.
- I need to act now, or very soon.

### Expected Executive Summary behavior
The executive summary should:
- make the risk or instability obvious
- indicate whether the issue is critical or emerging
- state whether immediate action is required
- provide a clear primary next action when appropriate

### Expected Diagnostic behavior
Diagnostics should:
- show which domains are driving the issue
- distinguish between main control domains and supporting drift drivers
- help the user see cause, severity, source, and fix path
- make drill-down destinations clear

### Expected AI behavior by maturity level
- **AI Off**: no AI section visible
- **Descriptive**: summarize what is happening clearly
- **Diagnostic**: explain likely drivers and cross-domain relationships
- **Predictive**: show what is likely to worsen if no action is taken
- **Agentic**: recommend the next best action or intervention options while keeping the user in control

### What should not happen
- the screen should not hide the seriousness of the issue
- AI should not make vague or generic recommendations
- diagnostics should not duplicate the executive summary instead of adding evidence and path to fix

---

## Scenario 3 — Recovered / Recently Improved

### Intent
Demonstrate a project or initiative where one or more domains have recently improved, especially where a previously problematic area has turned green since the last review.

### What the user should conclude quickly
- The situation has improved.
- Some areas may now be under control.
- I may still need to monitor or close out follow-up actions.

### Expected Executive Summary behavior
The executive summary should:
- acknowledge improvement clearly
- avoid pretending the project has always been healthy
- help the user understand whether action is still needed or only monitoring is required

### Expected Diagnostic behavior
Diagnostics should:
- surface domains that recently improved when relevant
- use a recovery or improving trend cue where appropriate
- make it clear whether the issue is resolved or simply stabilizing
- avoid removing useful recent-history context too early

### Expected AI behavior by maturity level
- **AI Off**: no AI section visible
- **Descriptive**: state what improved
- **Diagnostic**: explain what likely contributed to recovery
- **Predictive**: indicate whether the improved state looks stable or fragile
- **Agentic**: recommend whether to monitor, confirm, or close follow-up actions

### What should not happen
- the screen should not erase the improvement signal
- AI should not continue describing the project as fully at risk if key conditions have changed
- recovered states should not look identical to always-healthy states

---

## Cross-Tool Evaluation Checks
Use these checks when comparing outputs across tools.

### Structural checks
- Does the output preserve the structure defined in the active screen spec?
- Does the scenario meaning remain clear without long explanation?
- Does the design stay readable and scannable?

### Behavior checks
- Does AI On/Off work as intended?
- Does switching AI maturity level update the right content?
- Does the baseline non-AI structure remain stable while AI changes in place?

### Content checks
- Does the executive summary answer the top questions quickly?
- Does the diagnostic area add evidence rather than duplication?
- Are action signals appropriate to the scenario?
- Do recovered states feel meaningfully different from both healthy and at-risk states?

### Quality checks
- Does the tool avoid generic filler?
- Does the healthy scenario stay calm?
- Does the at-risk scenario feel actionable?
- Does the recovered scenario show progress without losing context?
- Does each AI maturity level behave meaningfully differently?

## Reuse Rule
Future initiatives may reuse this file as a base test framework.
They may adapt domain labels, signal examples, and scenario details to fit the initiative.
They should not override the structural truth defined by the initiative’s active files.

## Versioning Note
If repeated evaluation needs emerge across initiatives, extend this file gradually rather than overloading it with tool-specific instructions.
Keep it reusable, scenario-driven, and lightweight.
