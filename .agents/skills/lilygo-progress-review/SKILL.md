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
