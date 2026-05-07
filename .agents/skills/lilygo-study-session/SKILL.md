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
