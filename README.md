# LilyGO T-Embed CC1101 Plus: Zero-to-Master Course

This repository is a hands-on course and development workspace for learning the LilyGO T-Embed CC1101 Plus with Bruce firmware, starting from embedded zero and building toward advanced custom firmware, personal productivity tools, and responsible white-hat cybersecurity labs.

The learner is expected to be a capable software engineer who is new to embedded software engineering. The course explains hardware, buses, flashing, serial debugging, radio safety, and firmware architecture without slowing down for basic programming concepts.

## Course Promise

By the end of this course, you should be able to:

- Use Bruce confidently on the LilyGO T-Embed CC1101 Plus.
- Understand the board's ESP32-S3, display, input, storage, power, and radio peripherals.
- Build and debug PlatformIO projects for the board.
- Create personal productivity tools that run on the device.
- Read Bruce source, build it locally, and add small custom behavior.
- Run authorized security labs for your own devices and environments.
- Keep experiments documented, reversible, and safe.

## Learning Tracks

The course has two connected tracks:

- **Bruce Operator:** Learn the installed firmware first so the device stays useful while you build confidence.
- **Builder Lab:** Learn embedded development in a clean sandbox before modifying Bruce or building custom tools.

## Zero-to-Master Path

1. **Unbox and Understand:** Board anatomy, safety, Bruce overview, and learning log.
2. **Operate Bruce Well:** Menus, files, WebUI, settings, updates, backups, and safe experiments.
3. **Embedded Foundations:** ESP32-S3, PlatformIO, serial logs, GPIO, buses, display, input, storage, and power.
4. **Productivity Toolkit:** Dashboard, timers, quick capture, QR helpers, and personal automations.
5. **Protocol Literacy:** NFC, IR, BLE, Wi-Fi, CC1101, and nRF24 from a defensive, authorized perspective.
6. **Bruce Internals:** Source builds, board environments, menus, modules, storage, and debugging.
7. **Capstones:** Personal toolkit, authorized lab audit workflow, and maintainable custom firmware.

Start with `docs/course/COURSE_MAP.md`.

## Safety Boundary

This course is for owned devices, explicit permission, lab environments, defensive learning, and personal productivity. It does not include instructions for unauthorized access, credential capture, bypassing access controls, stealth, persistence, jamming, disruption, or attacking third-party systems.

Before any wireless or security lab, read `docs/reference/legal-and-safety.md`.

## Repository Map

- `docs/course/`: Zero-to-master course levels.
- `docs/reference/`: Hardware facts, safety rules, glossary, and source links.
- `templates/`: Standard formats for future lessons, labs, and projects.
- `firmware/`: Future isolated firmware workspaces.
- `tools/`: Future helper scripts.
- `notes/`: Personal learning log.
- `docs/superpowers/`: Design specs and implementation plans for Codex-driven work.

## First Steps

1. Read `docs/reference/legal-and-safety.md`.
2. Read `docs/reference/hardware.md`.
3. Open `docs/course/COURSE_MAP.md`.
4. Start `notes/learning-log.md`.
5. Begin Level 0 before flashing or changing firmware.

## Current Milestone

This repo currently contains the course scaffold. Firmware source trees, PlatformIO projects, and device flashing steps will be added through later implementation plans.
