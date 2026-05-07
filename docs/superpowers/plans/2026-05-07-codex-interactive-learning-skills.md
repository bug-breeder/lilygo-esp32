# Codex Interactive Learning Skills Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a repo-local Codex skill suite that turns the LilyGO/Bruce course into an interactive tutor, lab coach, project mentor, and progress reviewer.

**Architecture:** Add instruction-first Codex skills under `.agents/skills/`, shared learning guidance under `docs/interactive/`, and reusable session templates under `templates/`. Keep the first version script-free and automation-free so the learning workflow can be tested manually before adding deterministic tools.

**Tech Stack:** Markdown, Codex repo-local skills, existing course docs, shell verification.

---

## File Structure

- Create `.agents/skills/lilygo-study-session/SKILL.md`: interactive tutor workflow for lessons, concepts, explanations, and short quizzes.
- Create `.agents/skills/lilygo-lab-coach/SKILL.md`: hands-on lab workflow with authorization, safety gates, verification, and cleanup.
- Create `.agents/skills/lilygo-project-mentor/SKILL.md`: productivity-project ideation and scoping workflow.
- Create `.agents/skills/lilygo-progress-review/SKILL.md`: progress review, retrieval quiz, gap analysis, and next-session planning workflow.
- Create `docs/interactive/codex-learning-loop.md`: shared active-learning loop used by all skills.
- Create `docs/interactive/session-modes.md`: supported tutoring, lab, project, and review modes.
- Create `docs/interactive/skill-usage.md`: user-facing guide with example prompts.
- Create `templates/study-session.md`: optional session summary template.
- Create `templates/progress-review.md`: optional review summary template.
- Modify `AGENTS.md`: add durable repository instructions for interactive learning behavior.
- Modify `README.md`: surface the interactive Codex learning workflow in the human entrypoint.
- Modify `docs/course/COURSE_MAP.md`: add Codex-guided rhythm to the course flow.

Design decisions locked for this first implementation:

- Repo-local skills are allowed to trigger implicitly through descriptions and explicitly through `$skill-name`.
- Learning-log updates are opt-in; skills offer a compact entry but do not edit notes without user agreement.
- Shared teaching rules live in `docs/interactive/`; each `SKILL.md` contains enough local guidance to work when invoked directly.
- Do not add `agents/openai.yaml` in this implementation. Skill frontmatter is enough for discovery.
- Do not add scripts or automations in this implementation.

---

### Task 1: Add Shared Interactive Docs And Templates

**Files:**

- Create: `docs/interactive/codex-learning-loop.md`
- Create: `docs/interactive/session-modes.md`
- Create: `docs/interactive/skill-usage.md`
- Create: `templates/study-session.md`
- Create: `templates/progress-review.md`

- [ ] **Step 1: Create the interactive docs directory**

Run:

```bash
mkdir -p docs/interactive
```

Expected: command exits with status 0.

- [ ] **Step 2: Create `docs/interactive/codex-learning-loop.md`**

Create `docs/interactive/codex-learning-loop.md` with this exact content:

```markdown
# Codex Learning Loop

This course uses Codex as an interactive learning partner, not only as a document writer. A good session should make the learner think, predict, test, explain, and reflect.

## Default Loop

Use this loop for study sessions, labs, projects, and reviews unless the learner asks for a different mode.

1. **Orient:** Identify the learner's goal, course level, topic, available time, and whether hardware is available.
2. **Gate:** Check safety, authorization, and scope before any wireless, cybersecurity, flashing, or hardware-risk step.
3. **Calibrate:** Ask 3 to 5 short questions to estimate current understanding.
4. **Coach:** Teach one concept, lab step, project decision, or debugging move at a time.
5. **Retrieve:** Ask the learner to recall, predict, explain, or diagnose before giving the full answer.
6. **Verify:** Confirm understanding, command output, device behavior, or written reasoning.
7. **Reflect:** Summarize what changed in the learner's mental model.
8. **Choose next:** Recommend the next lesson, lab, project step, or review target.

## Teaching Rules

- Prefer questions and small challenges before long explanations.
- Connect embedded concepts to familiar software engineering ideas.
- Use progressive hints: hint, stronger hint, explanation, answer.
- Use retrieval practice at the end of every session.
- Ask the learner how they would verify claims in hardware, firmware, or logs.
- Keep examples practical and tied to the LilyGO T-Embed CC1101 Plus, Bruce, PlatformIO, or productivity tooling.
- Keep cybersecurity work defensive, owned-device, authorized, and auditable.

## Session Closeout

End each session with:

- What the learner practiced.
- What evidence showed progress.
- One gap or misconception to revisit.
- One recommended next step.
- An offer to add a compact note to `notes/learning-log.md`.
```

- [ ] **Step 3: Create `docs/interactive/session-modes.md`**

Create `docs/interactive/session-modes.md` with this exact content:

```markdown
# Session Modes

Codex can guide the course in several modes. Choose the smallest mode that fits the learner's current goal.

## Tutor Mode

Use for concepts, mental models, and course progression.

Flow:

1. Ask what topic or level the learner wants.
2. Calibrate with short questions.
3. Explain in small chunks.
4. Ask the learner to predict or explain.
5. End with retrieval practice and next steps.

Good for:

- ESP32-S3 basics.
- Bruce feature literacy.
- CC1101, NFC, IR, BLE, Wi-Fi, and nRF24 concepts.
- PlatformIO and embedded debugging concepts.

## Lab Coach Mode

Use for hands-on work with the device, firmware, host tools, or owned test targets.

Flow:

1. Confirm hardware, firmware, target, and authorization.
2. Classify the lab as concept-only, receive-only, local-only, or transmit-capable.
3. Give one step at a time.
4. Ask for observations before diagnosis.
5. Verify after each meaningful step.
6. End with cleanup and rollback notes.

Good for:

- Bruce operation.
- Serial logs.
- PlatformIO build checks.
- Owned NFC tags.
- IR remotes for owned devices.
- Defensive wireless inventory in authorized environments.

## Project Mentor Mode

Use for turning real-life productivity needs into device projects.

Flow:

1. Ask what workflow the learner wants to improve.
2. Identify inputs, outputs, storage, display, controls, and constraints.
3. Pick the smallest useful prototype.
4. Decide whether the work belongs in Bruce, custom firmware, host tooling, or notes.
5. Define milestones and done-when checks.

Good for:

- Focus timers.
- Quick capture tools.
- Local dashboards.
- QR/contact helpers.
- Personal automation helpers for owned devices and tags.

## Progress Review Mode

Use for deciding what to learn next.

Flow:

1. Inspect the course map and learning log.
2. Ask the learner to self-rate confidence.
3. Run a short retrieval quiz.
4. Identify strengths and gaps.
5. Recommend the next lesson, lab, or project.

Good for:

- Level transitions.
- Review before advanced protocol labs.
- Weekly study planning.
- Checking readiness for Bruce internals.
```

- [ ] **Step 4: Create `docs/interactive/skill-usage.md`**

Create `docs/interactive/skill-usage.md` with this exact content:

```markdown
# Skill Usage

This repository includes Codex skills for interactive LilyGO/Bruce learning. You can invoke them explicitly or ask naturally.

## Skills

- `$lilygo-study-session`: Learn a topic, continue the course, get quizzed, or build a mental model.
- `$lilygo-lab-coach`: Work through hands-on labs, device observations, serial logs, or safe experiments.
- `$lilygo-project-mentor`: Turn a real-life productivity need into a device project.
- `$lilygo-progress-review`: Review progress, find gaps, and choose the next step.

## Example Prompts

```text
$lilygo-study-session Teach me the next thing after Level 0.
```

```text
$lilygo-lab-coach Help me safely explore NFC with tags I own.
```

```text
$lilygo-project-mentor I want a focus timer and quick notes workflow on the device.
```

```text
$lilygo-progress-review Quiz me and tell me whether I am ready for Level 3.
```

## Natural Prompts

These should also route to the right workflow:

- "Teach me CC1101 from zero."
- "Coach me through a safe Bruce lab."
- "Help me build a productivity toolkit feature."
- "Review my learning log and tell me what to study next."

## Learning Log

Skills may offer to update `notes/learning-log.md`. Treat that as opt-in. A good entry includes:

- Date.
- Topic.
- What was practiced.
- Evidence or result.
- Questions.
- Next step.

## Safety Reminder

Wireless, radio, NFC/RFID, BLE, Wi-Fi, IR, and cybersecurity labs must be owned-device, explicitly authorized, defensive, or lab-only. When in doubt, narrow the lab to receive-only observation or concept learning.
```

- [ ] **Step 5: Create `templates/study-session.md`**

Create `templates/study-session.md` with this exact content:

```markdown
# Study Session

Date:
Skill:
Course Level:
Topic:
Timebox:
Hardware Available:

## Goal

What should be clearer or more usable by the end of this session?

## Calibration

- Question:
  - Answer:
  - Confidence:
- Question:
  - Answer:
  - Confidence:
- Question:
  - Answer:
  - Confidence:

## Key Ideas

- 

## Retrieval Practice

- Prompt:
  - Answer:
  - Result:
- Prompt:
  - Answer:
  - Result:
- Prompt:
  - Answer:
  - Result:

## Evidence

What did the learner explain, build, observe, or verify?

## Reflection

What changed in the learner's mental model?

## Next Step

One recommended lesson, lab, review, or project step.
```

- [ ] **Step 6: Create `templates/progress-review.md`**

Create `templates/progress-review.md` with this exact content:

```markdown
# Progress Review

Date:
Review Scope:
Course Level:

## Current Position

Where is the learner in the zero-to-master path?

## Evidence Reviewed

- Course map:
- Learning log:
- Labs:
- Projects:
- Device observations:

## Retrieval Results

- Prompt:
  - Answer:
  - Assessment:
- Prompt:
  - Answer:
  - Assessment:
- Prompt:
  - Answer:
  - Assessment:

## Strengths

- 

## Gaps

- 

## Safety Readiness

Owned-device and authorization fluency:

Wireless/radio caution:

Backup/rollback awareness:

## Recommended Next Step

Lesson, lab, or project:

Reason:

Done when:
```

- [ ] **Step 7: Verify shared docs and templates**

Run:

```bash
find docs/interactive templates -maxdepth 2 -type f | sort
```

Expected output includes:

```text
docs/interactive/codex-learning-loop.md
docs/interactive/session-modes.md
docs/interactive/skill-usage.md
templates/lab.md
templates/lesson.md
templates/progress-review.md
templates/project.md
templates/study-session.md
```

Run:

```bash
rg -n "Codex Learning Loop|Session Modes|Skill Usage|Study Session|Progress Review" docs/interactive templates
```

Expected: each new file heading appears at least once.

- [ ] **Step 8: Commit shared docs and templates**

Run:

```bash
git add docs/interactive templates/study-session.md templates/progress-review.md
git commit -m "Add interactive learning docs and templates"
```

Expected: commit succeeds with the five new files.

---

### Task 2: Add Repo-Local Codex Skills

**Files:**

- Create: `.agents/skills/lilygo-study-session/SKILL.md`
- Create: `.agents/skills/lilygo-lab-coach/SKILL.md`
- Create: `.agents/skills/lilygo-project-mentor/SKILL.md`
- Create: `.agents/skills/lilygo-progress-review/SKILL.md`

- [ ] **Step 1: Create skill directories**

Run:

```bash
mkdir -p \
  .agents/skills/lilygo-study-session \
  .agents/skills/lilygo-lab-coach \
  .agents/skills/lilygo-project-mentor \
  .agents/skills/lilygo-progress-review
```

Expected: command exits with status 0.

- [ ] **Step 2: Create `lilygo-study-session`**

Create `.agents/skills/lilygo-study-session/SKILL.md` with this exact content:

```markdown
---
name: lilygo-study-session
description: Run an interactive LilyGO/Bruce course study session with calibration, active recall, progressive hints, and optional learning-log summary. Use when the user wants to learn a topic, continue a lesson, be taught, be quizzed, or understand the device/course.
---

# LilyGO Study Session

Use this skill to teach the learner interactively inside the LilyGO T-Embed CC1101 Plus zero-to-master course.

## Context To Check

- `docs/course/COURSE_MAP.md`
- Relevant `docs/course/*/README.md`
- `docs/reference/legal-and-safety.md` for wireless, radio, NFC/RFID, BLE, Wi-Fi, IR, or cybersecurity topics
- `docs/interactive/codex-learning-loop.md`
- `docs/interactive/session-modes.md`
- `notes/learning-log.md` when the user asks to continue from prior progress

## Workflow

1. Identify the learner's topic, course level, timebox, and whether hardware is available.
2. If the topic touches wireless, radio, NFC/RFID, BLE, Wi-Fi, IR, cybersecurity, flashing, or device modification, state the safety scope before teaching.
3. Ask 3 to 5 short calibration questions. Use questions that require recall or explanation, not multiple-choice recognition unless the learner is stuck.
4. Choose one session mode: concept explanation, retrieval quiz, lab preparation, debugging reasoning, or project thinking.
5. Teach in small chunks. After each chunk, ask the learner to predict, explain, compare, or verify.
6. Use progressive hints when the learner struggles: light hint, stronger hint, explanation, answer.
7. Connect embedded concepts to software engineering concepts the learner already knows.
8. End with a short retrieval quiz and one recommended next action.
9. Offer a compact `notes/learning-log.md` entry, but do not edit the file unless the user agrees.

## Teaching Style

- Be interactive before being encyclopedic.
- Prefer "What do you think will happen and why?" over immediate answers.
- Prefer concrete examples from the LilyGO board, Bruce, ESP32-S3, PlatformIO, or productivity-toolkit projects.
- Keep explanations short enough that the learner can respond.
- Use Mermaid diagrams only when a flow, protocol path, or architecture becomes easier to reason about visually.

## Safety Boundaries

- Do not provide instructions for unauthorized access, credential capture, bypassing access controls, stealth, persistence, evasion, jamming, disruption, or attacking third-party systems.
- For security topics, keep examples defensive, owned-device, authorized, and auditable.
- Prefer concept-only or receive-only explanations before transmit-capable protocol work.

## Required Closeout

End with:

- Topic practiced.
- What the learner could explain or verify.
- One remaining gap.
- Recommended next step.
- Optional learning-log entry offer.
```

- [ ] **Step 3: Create `lilygo-lab-coach`**

Create `.agents/skills/lilygo-lab-coach/SKILL.md` with this exact content:

```markdown
---
name: lilygo-lab-coach
description: Coach hands-on LilyGO/Bruce labs with authorization checks, safety gates, one-step guidance, verification, troubleshooting, cleanup, and optional lab notes. Use when the user wants to test the device, run a lab, inspect Bruce behavior, flash/build carefully, or debug hardware/firmware observations.
---

# LilyGO Lab Coach

Use this skill for hands-on course work involving the LilyGO T-Embed CC1101 Plus, Bruce, PlatformIO, host tools, owned tags/remotes/devices, or lab observations.

## Context To Check

- `docs/reference/legal-and-safety.md`
- `docs/reference/hardware.md`
- Relevant course level in `docs/course/`
- `templates/lab.md`
- `docs/interactive/codex-learning-loop.md`
- `notes/learning-log.md` when the user asks to capture results

## Workflow

1. Confirm the lab goal, hardware state, firmware state, target device or environment, and authorization.
2. Classify the lab as one of:
   - Concept-only.
   - Receive-only.
   - Local-only.
   - Transmit-capable on owned or explicitly authorized targets.
3. If authorization, region, target ownership, or transmit scope is unclear, pause and narrow the lab before giving operational steps.
4. Ask for the learner's current observation before suggesting a fix or next action.
5. Give one step at a time.
6. After each meaningful step, ask for evidence such as screen state, serial output, file contents, command output, or observed device behavior.
7. Troubleshoot from evidence. Separate hardware, firmware, configuration, and expectation errors.
8. End with cleanup, rollback notes, and what the learner should record.

## Safety Boundaries

- Do not help with unauthorized access, credential capture, bypass, stealth, persistence, evasion, jamming, disruption, or attacks on third-party devices.
- Do not provide transmit-capable RF or wireless steps unless the target is owned or explicitly authorized and the scope is narrow.
- Prefer receive-only protocol exploration before any transmit-capable lab.
- For flashing or firmware changes, include backup/restore thinking and device identification before upload steps.

## Evidence To Capture

- Firmware name and version when known.
- Device state before the lab.
- Commands run.
- Serial logs or screen observations.
- Target ownership or authorization statement for wireless/security labs.
- Expected result versus observed result.
- Cleanup and rollback.

## Required Closeout

End with:

- Lab classification.
- What worked.
- What did not work or remains unknown.
- Safety/cleanup status.
- Recommended next lab or study session.
- Optional learning-log entry offer.
```

- [ ] **Step 4: Create `lilygo-project-mentor`**

Create `.agents/skills/lilygo-project-mentor/SKILL.md` with this exact content:

```markdown
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
```

- [ ] **Step 5: Create `lilygo-progress-review`**

Create `.agents/skills/lilygo-progress-review/SKILL.md` with this exact content:

```markdown
---
name: lilygo-progress-review
description: Review LilyGO/Bruce course progress, run retrieval checks, identify gaps, check safety readiness, and recommend the next lesson, lab, or project. Use when the user asks what to learn next, wants a quiz, wants readiness assessment, or wants a study plan.
---

# LilyGO Progress Review

Use this skill to assess course progress and choose the next best learning move.

## Context To Check

- `docs/course/COURSE_MAP.md`
- Relevant course level files in `docs/course/`
- `notes/learning-log.md`
- `docs/reference/legal-and-safety.md`
- `templates/progress-review.md`
- `docs/interactive/codex-learning-loop.md`

## Workflow

1. Identify the requested review scope: whole course, current level, specific topic, lab readiness, project readiness, or safety readiness.
2. Inspect the course map and learning log when available.
3. Ask the learner for a confidence self-rating and what they remember without notes.
4. Run a short retrieval check with 3 to 7 prompts. Prefer explanation and verification questions.
5. Identify demonstrated strengths, gaps, misconceptions, and unsafe assumptions.
6. Recommend one next lesson, lab, or project step.
7. Explain why that next step is the best fit.
8. Offer a compact `notes/learning-log.md` progress-review entry, but do not edit the file unless the user agrees.

## Assessment Rules

- Prefer recall and explanation over recognition.
- Ask "why", "what evidence would prove it", and "what could go wrong" questions.
- Treat gaps as routing information for the next session.
- Require safety fluency before advanced wireless, RF, NFC/RFID, BLE, Wi-Fi, IR, or cybersecurity labs.
- If the learner is not ready for a requested advanced topic, provide a shorter bridge exercise.

## Required Output

Produce:

- Review scope.
- Evidence checked.
- Strengths.
- Gaps.
- Safety readiness when relevant.
- Recommended next step.
- One concrete prompt the learner can use to start that next session.
```

- [ ] **Step 6: Verify skill metadata and safety language**

Run:

```bash
find .agents/skills -maxdepth 3 -type f | sort
```

Expected output:

```text
.agents/skills/lilygo-lab-coach/SKILL.md
.agents/skills/lilygo-progress-review/SKILL.md
.agents/skills/lilygo-project-mentor/SKILL.md
.agents/skills/lilygo-study-session/SKILL.md
```

Run:

```bash
rg -n "^name: lilygo-|^description:" .agents/skills
```

Expected: each `SKILL.md` has one `name` and one `description`.

Run:

```bash
rg -n "authorization|owned|receive-only|unauthorized|learning-log" .agents/skills
```

Expected: safety and learning-log language appears across the skills.

- [ ] **Step 7: Commit repo-local skills**

Run:

```bash
git add .agents/skills
git commit -m "Add LilyGO interactive Codex skills"
```

Expected: commit succeeds with four new `SKILL.md` files.

---

### Task 3: Surface Interactive Learning In Repo Entrypoints

**Files:**

- Modify: `AGENTS.md`
- Modify: `README.md`
- Modify: `docs/course/COURSE_MAP.md`

- [ ] **Step 1: Update `AGENTS.md` with interactive learning behavior**

In `AGENTS.md`, add this section between `## Working Rules` and `## Safety Rules`:

```markdown
## Interactive Learning Behavior

- This repo is an interactive course as well as a development workspace.
- When the user asks to learn, study, practice, review, run a lab, or design a course project, prefer the repo-local LilyGO skills in `.agents/skills/`.
- Use `$lilygo-study-session` for concepts, course lessons, explanations, and quizzes.
- Use `$lilygo-lab-coach` for hands-on device, Bruce, PlatformIO, debugging, or protocol labs.
- Use `$lilygo-project-mentor` for productivity-toolkit ideas, project briefs, and capstone shaping.
- Use `$lilygo-progress-review` for quizzes, readiness checks, gap analysis, and next-step planning.
- Teach with active recall: ask the learner to predict, explain, or verify before giving full answers.
- Do not skip straight to implementation when the user is trying to learn.
- Ask before editing `notes/learning-log.md`; user observations are personal study records.
```

- [ ] **Step 2: Update `README.md` with interactive learning instructions**

In `README.md`, add this section after `## Learning Tracks`:

```markdown
## Interactive Learning With Codex

This repo includes repo-local Codex skills for active learning:

- `$lilygo-study-session` for lessons, explanations, and retrieval quizzes.
- `$lilygo-lab-coach` for safe hands-on labs and debugging.
- `$lilygo-project-mentor` for productivity-toolkit and capstone project design.
- `$lilygo-progress-review` for readiness checks and next-step planning.

You can invoke a skill directly or ask naturally, such as "teach me the next lesson" or "review my progress." Start with `docs/interactive/skill-usage.md`.
```

- [ ] **Step 3: Update `docs/course/COURSE_MAP.md` suggested rhythm**

Replace the `## Suggested Rhythm` list in `docs/course/COURSE_MAP.md` with:

```markdown
## Suggested Rhythm

For each lesson:

1. Start a `$lilygo-study-session` or read the concept section.
2. Use retrieval practice to explain the idea without notes.
3. Run the lab on owned or authorized equipment with `$lilygo-lab-coach`.
4. Capture evidence in `notes/learning-log.md` when useful.
5. Complete the done-when checks.
6. Use `$lilygo-progress-review` before moving to a harder level.
7. Try the mastery extension only after the baseline works.
```

- [ ] **Step 4: Verify entrypoint references**

Run:

```bash
rg -n "Interactive Learning|lilygo-study-session|lilygo-lab-coach|lilygo-project-mentor|lilygo-progress-review" AGENTS.md README.md docs/course/COURSE_MAP.md
```

Expected: all four skill names appear in `AGENTS.md` and `README.md`; study/lab/review names appear in the course map.

- [ ] **Step 5: Commit entrypoint updates**

Run:

```bash
git add AGENTS.md README.md docs/course/COURSE_MAP.md
git commit -m "Document interactive Codex learning workflow"
```

Expected: commit succeeds with three modified files.

---

### Task 4: Final Verification

**Files:**

- Verify: `.agents/skills/*/SKILL.md`
- Verify: `docs/interactive/*.md`
- Verify: `templates/study-session.md`
- Verify: `templates/progress-review.md`
- Verify: `AGENTS.md`
- Verify: `README.md`
- Verify: `docs/course/COURSE_MAP.md`

- [ ] **Step 1: Check the full file set**

Run:

```bash
find .agents/skills docs/interactive templates -maxdepth 3 -type f | sort
```

Expected output includes all four skill files, all three interactive docs, the existing lesson/lab/project templates, and the two new learning templates.

- [ ] **Step 2: Check Markdown structure**

Run:

```bash
rg -n "^# |^## |^### " .agents/skills docs/interactive templates/study-session.md templates/progress-review.md AGENTS.md README.md docs/course/COURSE_MAP.md
```

Expected: headings are visible and no file is empty.

- [ ] **Step 3: Check safety coverage**

Run:

```bash
rg -n "authorization|owned-device|owned|receive-only|unauthorized|jamming|credential capture|Safety" .agents/skills docs/interactive AGENTS.md README.md
```

Expected: lab and study skill files include safety boundaries; `AGENTS.md` and `README.md` still include safety language.

- [ ] **Step 4: Check for placeholder markers**

Run:

```bash
rg -n "REPLACE_ME|PLACEHOLDER|FILL_ME|XXX" .agents/skills docs/interactive templates AGENTS.md README.md docs/course/COURSE_MAP.md
```

Expected: no matches. This command exits with status 1 when there are no matches, which is acceptable for this step.

- [ ] **Step 5: Check Markdown diff cleanliness**

Run:

```bash
git diff --check
```

Expected: no whitespace errors.

- [ ] **Step 6: Inspect final history and status**

Run:

```bash
git log --oneline -5
git status --short --branch
```

Expected: recent commits show the interactive learning work, and `git status` shows a clean branch ahead of `origin/main` until pushed.

- [ ] **Step 7: Push `main`**

Run:

```bash
git push origin main
```

Expected: `main` pushes successfully to `https://github.com/bug-breeder/lilygo-esp32.git`.

---

## Self-Review Notes

Spec coverage:

- Repo-local skills are covered by Task 2.
- Shared active-learning loop and session modes are covered by Task 1.
- Safety and authorization gates are included in both skill content and entrypoint verification.
- Learning-log updates are opt-in in every relevant skill.
- No scripts, app metadata, plugins, or automations are added.
- Entrypoint discoverability is covered by Task 3.

Placeholder scan:

- The plan uses exact file paths and exact Markdown content.
- There are no placeholder markers in the planned file contents.

Consistency check:

- Skill names match across spec, docs, `AGENTS.md`, `README.md`, and verification commands.
- Shared docs paths match skill references.
- Templates match the optional outputs described by the skills.
