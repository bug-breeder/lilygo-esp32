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
