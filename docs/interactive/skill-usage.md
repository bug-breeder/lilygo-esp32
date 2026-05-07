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
