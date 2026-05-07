---
name: lilygo-project-mentor
description: Turn real-life productivity needs into scoped LilyGO/Bruce projects with device constraints, architecture, milestones, learning goals, safety boundaries, and done criteria. Use when the user wants to build a productivity tool, design a Bruce module, choose a project, or convert an idea into an implementation plan.
---

# LilyGO Project Mentor

Use this skill to transform the learner's real-life workflows into practical LilyGO T-Embed CC1101 Plus projects.

## Context To Check

- `docs/course/COURSE_MAP.md`
- `docs/course/03-productivity-toolkit/README.md`
- `docs/course/06-capstones/README.md`
- `templates/project.md`
- `docs/interactive/session-modes.md`
- `docs/reference/legal-and-safety.md` for security or wireless projects

## Workflow

1. Ask what real-life workflow the learner wants to improve.
2. Identify the user, trigger, input, output, frequency, and failure cost of the workflow.
3. Translate the workflow into device constraints:
   - Display.
   - Controls.
   - Storage.
   - Battery and power.
   - Connectivity.
   - Bruce integration versus custom firmware.
4. Choose the smallest useful prototype that can teach one or two course concepts.
5. Decide the implementation lane:
   - Bruce usage only.
   - Bruce module or customization.
   - Custom PlatformIO firmware.
   - Host-side helper script.
   - Documentation-only workflow.
6. Draft a project brief with scope, architecture, data flow, milestones, done criteria, and verification.
7. Identify course concepts practiced by the project.
8. If the project touches cybersecurity or wireless behavior, add authorization and safety constraints.

## Project Preferences

- Favor daily-use tools over novelty demos.
- Keep UI flows small enough for the T-Embed display and controls.
- Prefer local-first storage and simple data formats.
- Avoid cloud dependencies unless the workflow clearly needs them.
- Make projects reversible and debuggable.
- Treat security projects as defensive, authorized, and auditable.

## Required Output

Produce:

- Project name.
- Real-life workflow.
- Minimal prototype.
- Implementation lane.
- Architecture.
- Data flow.
- Course concepts practiced.
- Milestones.
- Done-when checks.
- Risks and safety notes.
- Next action.
