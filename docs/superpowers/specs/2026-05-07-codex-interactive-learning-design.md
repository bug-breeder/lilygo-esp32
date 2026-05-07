# Codex Interactive Learning Design

Date: 2026-05-07
Status: Approved design, pending implementation plan

## Context

The repository currently provides a zero-to-master course scaffold for learning the LilyGO T-Embed CC1101 Plus, Bruce firmware, embedded development, productivity tooling, and authorized white-hat security labs.

The current structure is strong for passive study: course levels, references, templates, and learning notes. The missing piece is an interactive mechanism that makes Codex behave like a tutor, lab coach, project mentor, and progress reviewer inside this repository.

The learner is a computer scientist and software engineer who is new to embedded systems. The course should therefore use the learner's existing software engineering background as a bridge into hardware, firmware, RF concepts, Bruce internals, and practical device projects.

## Research Basis

Codex best-practice findings:

- Codex should be treated as a configured teammate rather than a one-off assistant.
- Durable repository behavior belongs in `AGENTS.md`.
- Repeatable workflows should become skills.
- Skills should be focused, discoverable, and scoped to concrete use cases.
- Automations should wait until a manual workflow is stable.
- Long prompts should not carry durable process rules that belong in `AGENTS.md` or skills.
- A good task loop includes goal, context, constraints, done criteria, verification, and review.

Learning and AI-tutoring findings:

- Interactive and constructive activity produces deeper learning than passive reading.
- Retrieval practice improves long-term retention more than rereading alone.
- Feedback is most useful when it clarifies the goal, the learner's current state, and the next step.
- Self-regulated learning depends on planning, monitoring, and reflection.
- AI tutoring works best when it scaffolds thinking with guiding questions and avoids giving away answers too early.
- For technical mastery, deliberate practice should use clear goals, constrained exercises, fast feedback, and reflection.

Primary references:

- https://developers.openai.com/codex/learn/best-practices
- https://developers.openai.com/codex/skills
- https://developers.openai.com/codex/guides/agents-md
- https://developers.openai.com/codex/app/automations
- https://education.asu.edu/lcl/publications/chi-m-t-h-wylie-r-2014-icap-framework-linking-cognitive-engagement-active-learning
- https://journals.sagepub.com/doi/10.1111/j.1467-9280.2006.01693.x
- https://journals.sagepub.com/doi/10.3102/003465430298487
- https://www.frontiersin.org/articles/10.3389/feduc.2023.1281438/full
- https://arxiv.org/abs/2410.03017

## Goals

- Turn the course from static notes into an interactive Codex-guided learning system.
- Add repo-local Codex skills that can be invoked explicitly during study.
- Make Codex teach with active recall, Socratic prompts, progressive hints, labs, projects, and reflection.
- Keep safety and authorization gates present in every Bruce, RF, NFC, BLE, Wi-Fi, IR, and cybersecurity interaction.
- Preserve the zero-to-master course path while allowing flexible sessions based on time, energy, and interests.
- Make the learning loop produce useful artifacts: plans, lab notes, quiz results, project ideas, and next steps.
- Keep the first version simple enough to test manually before considering automation.

## Non-Goals

- Do not implement a full LMS, web app, spaced-repetition database, or external service integration yet.
- Do not create background automations in the first iteration.
- Do not replace the course map; the skill system should sit on top of it.
- Do not teach unsafe or unauthorized cybersecurity workflows.
- Do not create a general-purpose Codex education plugin yet; start with repo-local skills.
- Do not require hardware connection for every session. Some sessions should be concept-only or planning-only.

## Recommended Approach

Create a repo-local Codex skill suite under `.agents/skills/`.

This is better than prompt-only documentation because Codex can discover and invoke the workflows consistently. It is also better than a plugin or automation right now because the workflow is still project-specific and should be refined manually before distribution or scheduling.

The first implementation should include four skills:

- `lilygo-study-session`
- `lilygo-lab-coach`
- `lilygo-project-mentor`
- `lilygo-progress-review`

Each skill should be instruction-first, with no scripts in the initial version. Scripts can be added later only when deterministic artifact generation becomes useful.

## Skill 1: `lilygo-study-session`

Purpose:

- Run an interactive learning session for a course level, topic, or learner question.

Use when the user says things like:

- "Teach me the next lesson."
- "Start a LilyGO study session."
- "Help me learn ESP32-S3 basics."
- "Quiz me on Bruce before continuing."
- "Explain CC1101 from zero."

Workflow:

1. Identify the topic, level, available time, and desired intensity.
2. Calibrate the learner with 3 to 5 short questions.
3. Choose a mode: explain, quiz, debug, lab prep, or project thinking.
4. Teach in short chunks connected to software engineering concepts.
5. Ask the learner to predict, explain, or recall before revealing answers.
6. End with a short retrieval quiz and next recommended action.
7. Offer to update `notes/learning-log.md` with a compact session summary.

Teaching style:

- Use Socratic prompts before full answers.
- Give progressive hints when the learner is stuck.
- Prefer concrete mental models and diagrams in text or Mermaid when useful.
- Compare embedded concepts to familiar software engineering ideas.
- Keep cybersecurity and RF topics inside safety boundaries.

Expected outputs:

- Session goal.
- Current level/topic.
- Key concepts learned.
- Quiz or challenge results.
- Next step.
- Optional learning-log entry.

## Skill 2: `lilygo-lab-coach`

Purpose:

- Guide hands-on Bruce or firmware labs with safety checks, materials, steps, verification, and cleanup.

Use when the user says things like:

- "Coach me through this lab."
- "Help me test this safely on my device."
- "I want to try an NFC lab."
- "Walk me through flashing or serial logs."
- "Help me debug this LilyGO behavior."

Workflow:

1. Confirm the lab target, hardware state, firmware state, and user authorization.
2. Classify the lab as concept-only, receive-only, local-only, or transmit-capable.
3. Check safety and legal constraints before any potentially sensitive step.
4. Ask for current observations before suggesting fixes.
5. Guide one step at a time.
6. Require verification after each meaningful step.
7. Capture symptoms, commands, versions, and outcomes.
8. End with cleanup, rollback notes, and what was learned.

Safety requirements:

- For wireless, RF, NFC/RFID, BLE, Wi-Fi, IR, and cybersecurity labs, explicitly confirm ownership or authorization.
- Prefer receive-only and observation-first labs.
- Do not provide unauthorized access, credential capture, jamming, stealth, evasion, persistence, bypass, or attack instructions.
- When unsure about legality or scope, pause and narrow the lab.

Expected outputs:

- Lab classification.
- Materials and prerequisites.
- Step-by-step guidance.
- Verification checklist.
- Debug notes.
- Cleanup and rollback.
- Optional lab-note entry.

## Skill 3: `lilygo-project-mentor`

Purpose:

- Turn real-life productivity needs into practical LilyGO/Bruce firmware or tooling projects.

Use when the user says things like:

- "Help me build a productivity tool."
- "Turn this idea into a LilyGO project."
- "Design a focus timer for the device."
- "What useful thing should I build next?"
- "Help me create a Bruce module idea."

Workflow:

1. Ask what real-life workflow the user wants to improve.
2. Translate the workflow into device constraints, inputs, outputs, storage, and interactions.
3. Pick the smallest useful prototype.
4. Identify whether the project belongs in Bruce, custom firmware, host tooling, or notes only.
5. Create a project brief with scope, architecture, risks, and milestones.
6. Add learning objectives so the project advances the course path.
7. Define done criteria and verification.

Project preference:

- Favor daily-use tools over novelty demos.
- Keep UI flows small enough for the T-Embed controls and display.
- Prefer local-first designs with simple data formats.
- Avoid cloud dependencies unless they clearly improve the workflow.
- Treat cybersecurity projects as defensive, authorized, and auditable.

Expected outputs:

- Project brief.
- User workflow.
- Minimal viable prototype.
- Device architecture.
- Course concepts practiced.
- Milestones and done criteria.
- Optional project-template entry.

## Skill 4: `lilygo-progress-review`

Purpose:

- Review the learner's progress and recommend the next best lesson, lab, or project.

Use when the user says things like:

- "Review my progress."
- "What should I learn next?"
- "Quiz me before Level 3."
- "Am I ready for Bruce internals?"
- "Create my next study plan."

Workflow:

1. Inspect the course map, learning log, and relevant notes.
2. Ask the learner to self-rate confidence and recall key ideas without notes.
3. Run a short diagnostic quiz or challenge.
4. Identify strengths, gaps, and unsafe assumptions.
5. Recommend the next lesson, lab, or project.
6. Offer a short plan for the next session.

Assessment style:

- Prefer retrieval and explanation over recognition.
- Ask "why" and "how would you verify" questions.
- Mark gaps as normal next steps, not failures.
- Require safety fluency before advanced wireless or security labs.

Expected outputs:

- Progress summary.
- Skills demonstrated.
- Gaps to revisit.
- Recommended next step.
- Optional learning-log update.

## Shared Learning Loop

All skills should follow this loop unless the user explicitly asks for a different mode:

1. Orient: identify goal, level, timebox, and hardware availability.
2. Gate: check safety, authorization, and scope.
3. Calibrate: ask short questions to estimate current understanding.
4. Teach or coach: provide one chunk, lab step, or design step at a time.
5. Retrieve: ask the learner to recall, predict, or explain.
6. Verify: check understanding or device behavior.
7. Reflect: summarize what changed in the learner's model.
8. Choose next: recommend the next lesson, lab, or project.

This loop should keep sessions active and conversational, not lecture-only.

## Repository Artifacts To Add Later

The implementation plan should add:

```text
.agents/
└── skills/
    ├── lilygo-study-session/
    │   └── SKILL.md
    ├── lilygo-lab-coach/
    │   └── SKILL.md
    ├── lilygo-project-mentor/
    │   └── SKILL.md
    └── lilygo-progress-review/
        └── SKILL.md
docs/
└── interactive/
    ├── codex-learning-loop.md
    ├── session-modes.md
    └── skill-usage.md
templates/
├── study-session.md
└── progress-review.md
```

Optional later artifacts:

```text
tools/
└── learning/
    ├── new-session
    └── review-progress
```

These tools should be deferred until the manual skill workflow proves useful.

## AGENTS.md Updates To Add Later

`AGENTS.md` should be updated to explain:

- This repo contains an interactive course, not only source code.
- Use repo-local LilyGO skills when the user asks to learn, practice, review, or build course projects.
- For teaching tasks, prefer active recall, short explanations, guided questions, verification, and reflection.
- For labs, require safety and authorization checks.
- Do not skip straight to implementation when the user is trying to learn.
- Ask the learner to explain their mental model before correcting it.
- Record durable learning outcomes in `notes/learning-log.md` only when the user wants that.

## User Experience

The ideal user flow:

1. The learner opens Codex in the repository.
2. The learner invokes a skill or asks naturally.
3. Codex chooses the relevant course level and session mode.
4. Codex asks a few calibration questions.
5. Codex teaches or coaches through one focused unit.
6. The learner answers, predicts, tests, or builds.
7. Codex gives feedback and next steps.
8. The learner optionally saves the result to the learning log.

Example prompts:

```text
$lilygo-study-session Teach me the next thing after Level 0.
```

```text
$lilygo-lab-coach Help me safely explore NFC with tags I own.
```

```text
$lilygo-project-mentor I want a productivity tool for focus sessions and quick notes.
```

```text
$lilygo-progress-review Quiz me and tell me whether I am ready for Level 3.
```

## Automation Strategy

Do not create automations in the first implementation.

After the skills have been used manually, consider:

- A weekly progress review automation.
- A spaced-retrieval reminder automation.
- A project-health review automation for `firmware/productivity-toolkit/`.

Automations should use thread heartbeats only when preserving the same learning conversation matters. Project-scoped automations should use a worktree if they may edit files.

## Success Criteria

The design is successful when:

- Codex can reliably enter tutor, lab coach, project mentor, and progress reviewer modes.
- The learner can start an interactive session without rewriting a long prompt.
- Sessions involve recall, prediction, verification, and reflection.
- Safety checks appear before sensitive wireless/security work.
- The skills point back into the course map rather than creating disconnected mini-lessons.
- The workflow can be improved over time through edits to skills and `AGENTS.md`.

## Risks

- Too many skills could make discovery noisy.
- Too much teaching logic in `AGENTS.md` could bloat every Codex task.
- The skills could become lecture scripts instead of interactive workflows.
- The lab coach could accidentally overstep safety boundaries if authorization checks are vague.
- Automations could create low-value noise if added before manual sessions stabilize.

## Open Questions For Implementation Planning

- Should skills be explicitly invocation-only, or should Codex be allowed to invoke them implicitly?
- Should learning-log updates be opt-in every time, or should study/review skills default to proposing a patch?
- Should each skill include shared reference files, or should shared learning guidance live only in `docs/interactive/`?
- Should the first implementation include examples inside each `SKILL.md`, or keep examples centralized in `docs/interactive/skill-usage.md`?
- Should we add a small `agents/openai.yaml` for app display metadata now or later?

## Recommendation

Implement the repo-local skill suite first, with concise `SKILL.md` files and supporting interactive docs. Keep the first version script-free and automation-free. After several real sessions, refine the skills based on friction, then consider lightweight scripts or recurring review automation.
