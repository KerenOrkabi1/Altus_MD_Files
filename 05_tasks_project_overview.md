# Tasks — Project Overview (High Level)

## Purpose
This file breaks the Project Overview work into small, reviewable tasks.

Each task should be completed using the active initiative files as the source of truth:
- the active masterplan file
- the shared rules base file
- the shared design-guidelines base file
- the active user-journey file

Tasks should be completed in sequence. Do not proceed to the next task until the current task has been reviewed and explicitly approved.

## Working rule for all tasks
For every task:
- complete only the current task
- explain what was done
- explain how it can be reviewed or tested
- clearly label assumptions, gaps, or open questions
- wait for user approval before continuing to the next task

---

## Task 1 — Define the core page sections

### Purpose
Define the main sections that must appear on the Project Overview page.

### Inputs
- Active masterplan file
- Active user-journey file

### Expected output
A proposed set of high-level page sections in priority order, based on:
- the immediate user need
- the primary scan flow
- the required information blocks

### What to report back
- Explain the proposed page sections
- Explain why they are ordered this way
- Call out any assumptions or missing information

### How to review or test
- Check whether the section order matches the intended scan flow
- Check whether the structure supports the first 5-second user questions
- Check whether the page remains high-level and not overly detailed

### Approval to continue
Wait for explicit user approval before starting Task 2.

---

## Task 2 — Map decisions to supporting signals

### Purpose
Map each high-level user decision to the signals or information that support it.

### Inputs
- Active masterplan file
- Active user-journey file

### Expected output
A decision-to-signal mapping for each major decision, including:
- escalation
- reallocate resources
- adjust schedule
- risk mitigation
- stakeholder communication
- budget correction
- scope or change approval

### What to report back
- Explain which signals support each decision
- Explain where signal coverage is strong or weak
- Call out any missing decision support

### How to review or test
- Check whether each decision has enough visible support
- Check whether the signals fit a high-level overview
- Check whether any critical signal is missing or too detailed

### Approval to continue
Wait for explicit user approval before starting Task 3.

---

## Task 3 — Define AI maturity behavior in the experience

### Purpose
Translate the AI maturity model into clear UI and content behavior for the page.

### Inputs
- Active masterplan file
- Active user-journey file
- Shared `design-guidelines.md`

### Expected output
A clear definition of how each AI level appears in the experience:
- Level 1 = what
- Level 2 = why
- Level 3 = prediction
- Level 4 = recommendation / next step

This should describe how each level changes the user’s understanding without changing the core control model.

### What to report back
- Explain how each AI level differs from the others
- Explain what the user gains at each level
- Call out any overlap or ambiguity between levels

### How to review or test
- Check whether each level feels meaningfully different
- Check whether the progression is logical and easy to understand
- Check whether AI remains supportive and not overwhelming

### Approval to continue
Wait for explicit user approval before starting Task 4.

---

## Task 4 — Define the information hierarchy

### Purpose
Decide what information should be primary, secondary, and drill-down only.

### Inputs
- Active masterplan file
- Active user-journey file
- Shared `design-guidelines.md`

### Expected output
A proposed hierarchy for:
- top-level summary
- main health domains
- supporting drift domains
- secondary details
- drill-down navigation points

### What to report back
- Explain what is primary, secondary, and drill-down only
- Explain why this hierarchy supports the user journey
- Call out anything that may feel overloaded or underrepresented

### How to review or test
- Check whether the hierarchy supports the first 5-second scan
- Check whether the most important information is prioritized
- Check whether the hierarchy reduces noise and supports focus

### Approval to continue
Wait for explicit user approval before starting Task 5.

---

## Task 5 — Draft the first page structure concept

### Purpose
Create a first structural concept for the Project Overview page.

### Inputs
- Active masterplan file
- Active user-journey file
- Shared `design-guidelines.md`

### Expected output
A high-level structural concept describing:
- section order
- what appears above the fold
- where AI support appears
- where drill-down actions begin

This task should focus on structure only, not final visual polish.

### What to report back
- Explain the proposed structure
- Explain how the layout supports both non-AI and AI-enhanced states
- Call out assumptions, tradeoffs, or unresolved layout questions

### How to review or test
- Check whether the structure aligns with the intended scan flow
- Check whether the layout feels clear, calm, and usable
- Check whether AI is integrated appropriately without overpowering the core experience

### Approval to continue
Wait for explicit user approval before starting Task 6.

---

## Task 6 — Review the concept against the source files

### Purpose
Check the first concept against the current project files before going deeper.

### Inputs
- Active masterplan file
- Shared `rules.md`
- Shared `design-guidelines.md`
- Active user-journey file
- Outputs from Tasks 1–5

### Expected output
A short review of:
- what aligns well
- what conflicts with the source files
- what needs correction before further refinement

### What to report back
- Explain which parts align well
- Explain which parts conflict or drift
- Recommend what should be corrected next

### How to review or test
- Check whether the concept still aligns with the masterplan
- Check whether any rule has been violated
- Check whether the journey and design guidance are still reflected clearly

### Approval to continue
Wait for explicit user approval before starting Task 7.

---

## Task 7 — Capture stable refinements back into the files

### Purpose
Update the relevant files if new stable decisions emerge during review.

### Inputs
- Outputs from Tasks 1–6
- All current project files

### Expected output
Stable decisions, patterns, or clarifications added back into the correct file:
- active masterplan file for initiative truth
- shared `rules.md` for reusable AI behavior
- shared `design-guidelines.md` for reusable design standards
- active user-journey file for flow changes

### What to report back
- Explain what was updated
- Explain why each update belongs in that file
- Call out any items that should remain unresolved for now

### How to review or test
- Check whether each update is truly stable and reusable
- Check whether the update was added to the correct file
- Check whether duplication across files has been avoided

### Approval to continue
Wait for explicit user approval before creating any new tasks or moving to deeper design work.