# Rules — Base Working Rules for AI-Assisted Product and Design Initiatives

## Purpose
This file defines the baseline working rules for how AI should behave while supporting any initiative.

These rules are reusable across initiatives. They describe how AI should interpret files, handle uncertainty, preserve decisions, and produce clear outputs.

This file is not initiative-specific. It should work alongside the active initiative files, including the current masterplan, tasks, user journey, and any design guidance.

## AI behavior scope
- These rules govern the behavior of the AI assistant or generator while doing the work.
- These rules do not define the behavior of AI features inside the product being designed.
- Product-specific AI behavior belongs in the initiative's masterplan, user journey, or design guidance.

## File interpretation rules
- Treat the active masterplan file for the current initiative as the primary project source of truth.
- Treat the active tasks file as the source of truth for what should be done next.
- Treat the active user journey file as the source of truth for user flow and task progression.
- When a design-guidelines file exists, treat it as the source of truth for visual, interaction, and consistency decisions.
- Do not assume exact filenames. Use the current initiative's active files even if file names differ from one initiative to another.
- If an initiative file has been renamed, continue using the file based on its role rather than its original name.

## Source-of-truth rules
- Read the relevant project files before proposing, generating, or revising work.
- Prefer the information in the project files over recent conversational wording when a conflict exists.
- Do not overwrite or contradict stable decisions already captured in the files without explicitly surfacing the conflict.
- If a stable decision needs to change, call out the proposed change clearly before applying it.

## Missing-information rules
- Do not invent missing facts, requirements, or business logic.
- If important information is missing, mark it clearly as TBD, assumption, or open question.
- If two or more interpretations are possible, surface the ambiguity instead of choosing silently.
- Prefer explicit gaps over confident but unsupported assumptions.

## File-structure rules
- Keep each file focused on its purpose.
- Do not copy full sections from one file into another unless the content is intentionally repeated for clarity or required for execution.
- Prefer referencing the role of another file over repeating long content that already exists elsewhere.
- When adding new information, place it in the file where it logically belongs instead of forcing it into the current file.

## Output-behavior rules
- Work in small, reviewable steps instead of trying to solve everything at once.
- Keep outputs concise, structured, and easy to scan.
- Prefer direct wording over abstract or decorative phrasing.
- Use existing project terminology consistently. Do not introduce new terms if an established term already exists.
- Reduce confusion by simplifying, clarifying, and grouping related ideas.
- Do not add noise, filler, or repeated explanations unless they improve clarity.

## Review-and-change rules
- Before making meaningful updates, confirm the update aligns with the active masterplan.
- After generating a significant output, check it for contradictions, duplication, and drift from the source files.
- If an output introduces a new assumption, label it clearly.
- If an output changes scope, priorities, or intent, make that change visible rather than burying it in the text.

## Design-specific working rules
- When generating product, UX, or UI outputs, follow the active design-guidelines file if one exists.
- If no design-guidelines file exists, favor clarity, hierarchy, consistency, and readability.
- Keep design recommendations aligned to the initiative's masterplan rather than inventing a separate product direction.
- For AI-related UX, prefer subtle, supportive patterns over loud, distracting, or intimidating ones unless the initiative explicitly requires otherwise.


## Reuse and evolution
- This file is intended to serve as a reusable baseline across initiatives.
- Add initiative-specific rules only when a project has special risks, recurring failure patterns, or constraints not covered here.
- Update this base file when repeated issues appear across multiple initiatives and should become standard practice.

## Task progression and approval
- Complete one task at a time.
- After each task, explain what was done and how it can be reviewed or tested.
- Do not proceed to the next task until the current task has been reviewed and explicitly approved by the user.
- If feedback is provided, revise the current task output before continuing.
