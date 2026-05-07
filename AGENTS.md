# AGENTS.md

## Repository Purpose

This repo is a zero-to-master course and development workspace for the LilyGO T-Embed CC1101 Plus with Bruce firmware. Treat it as an embedded learning repo with safety-sensitive white-hat cybersecurity content.

## Working Rules

- Keep the course useful for a strong software engineer who is new to embedded development.
- Prefer small, focused files over large mixed-purpose documents.
- Keep course docs, reference docs, firmware workspaces, tools, and notes separated by directory responsibility.
- Do not flash hardware, install dependencies, clone upstream source trees, or add firmware code unless the active task explicitly asks for it.
- Preserve user notes in `notes/` and avoid rewriting personal observations unless asked.

## Interactive Learning Behavior

- This repo is an interactive course as well as a development workspace.
- When the user asks to learn, study, practice, review learning progress, check readiness, run a lab, or design a course project, prefer the repo-local LilyGO skills in `.agents/skills/`.
- Use `$lilygo-study-session` for concepts, course lessons, explanations, and quizzes.
- Use `$lilygo-lab-coach` for hands-on device, Bruce, PlatformIO, debugging, or protocol labs.
- Use `$lilygo-project-mentor` for productivity-toolkit ideas, project briefs, and capstone shaping.
- Use `$lilygo-progress-review` for quizzes, readiness checks, gap analysis, and next-step planning.
- Teach with active recall: ask the learner to predict, explain, or verify before giving full answers.
- Do not skip straight to implementation when the user is trying to learn.
- Ask before editing `notes/learning-log.md`; user observations are personal study records.

## Safety Rules

- Cybersecurity and radio work must be owned-device, explicitly authorized, defensive, or lab-only.
- Do not provide instructions for unauthorized access, credential capture, bypassing access controls, stealth, persistence, evasion, jamming, disruption, or attacking third-party systems.
- Wireless labs must state target ownership or authorization, whether transmission is allowed, region/legal considerations, expected observations, and cleanup.
- Prefer receive-only protocol lessons before any transmit-capable lab.

## Source Freshness

- Hardware, Bruce, PlatformIO, and protocol facts can change. For factual updates, check current official sources when possible.
- Prefer primary sources: LilyGO product/wiki/GitHub, Bruce firmware docs/GitHub, PlatformIO docs, Espressif docs, and chip vendor datasheets.
- Summarize the source link in docs when adding hardware or firmware facts.

## Documentation Standards

- Lessons must include purpose, prerequisites, concepts, steps, expected evidence, done-when checks, and reflection prompts.
- Labs must include authorization, safety constraints, materials, steps, expected evidence, cleanup, troubleshooting, and mastery extensions.
- Projects must include goal, architecture, data flow, storage/config decisions, test plan, done-when checks, and rollback notes.
- Avoid vague future promises. If work is not in scope for the current milestone, say what decision or plan will unlock it.

## Firmware Standards

- Prefer PlatformIO for firmware work unless a task explicitly chooses another flow.
- Keep build artifacts out of git.
- Keep upstream source trees isolated under `firmware/`.
- Do not mix Bruce source edits with from-scratch productivity firmware unless a plan defines the boundary.
- Any future upload or flashing instruction must include backup/restore notes and a way to identify the connected device/port.

## Verification

- For docs-only changes, verify file presence, links, headings, and safety language with shell checks.
- For firmware changes, run the selected PlatformIO build and document whether upload/device behavior was tested.
- Before finalizing, review the diff for unsafe security scope, stale facts, accidental build artifacts, and unclear next steps.
