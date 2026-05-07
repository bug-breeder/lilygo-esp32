# LilyGO T-Embed CC1101 Plus Zero-to-Master Course Design

Date: 2026-05-07
Status: Approved design, pending implementation plan

## Context

This repository starts empty and will become a hands-on course and development workspace for a LilyGO T-Embed CC1101 Plus running Bruce firmware. The learner is a computer scientist and software engineer who is new to embedded software engineering.

The project should teach from embedded zero to advanced practical mastery. It should begin with safe device operation and gradually move into ESP32-S3 development, PlatformIO, Bruce internals, personal productivity tools, and authorized white-hat cybersecurity labs.

Current source context:

- LilyGO product page describes the T-Embed CC1101 Plus as a T-Embed CC1101 with an added nRF24L01 module and lists ESP32-S3, 16MB flash, 8MB PSRAM, Wi-Fi, BLE, IR transmit/receive, PN532 NFC/RFID, CC1101, and ST7789 display capabilities.
- LilyGO wiki documents the T-Embed CC1101 as an ESP32-S3 development board with CC1101, LoRa, NFC, TFT, Quick Start, Pin Overview, related tests, dependent libraries, and PlatformIO-oriented examples.
- The official LilyGO GitHub repository contains firmware/examples and `platformio.ini`.
- Bruce firmware supports LilyGO T-Embed CC1101-class devices and documents installation/building from source with PlatformIO.
- OpenAI Codex best-practice documentation recommends durable repository instructions in `AGENTS.md`, explicit build/test/lint guidance, and verification/review loops.

Primary references:

- https://lilygo.cc/en-us/products/t-embed-cc1101-plus
- https://wiki.lilygo.cc/get_started/en/Wearable/T-Embed-CC1101/T-Embed-CC1101.html
- https://github.com/Xinyuan-LilyGO/T-Embed-CC1101
- https://github.com/BruceDevices/firmware
- https://github.com/pr3y/Bruce/wiki/Building-from-source
- https://developers.openai.com/codex/learn/best-practices
- https://developers.openai.com/codex/guides/agents-md

## Goals

- Create a zero-to-master course repo for learning the LilyGO T-Embed CC1101 Plus and Bruce.
- Teach embedded concepts to a strong software engineer without assuming embedded background.
- Keep Bruce usage and custom firmware development as separate but connected tracks.
- Build toward real-life productivity tools, not only isolated hardware demos.
- Include white-hat cybersecurity education with explicit authorization, legality, and safety boundaries.
- Make the repo easy for Codex to work in through concise instructions, templates, and verification expectations.

## Non-Goals

- Do not flash, replace, or modify the user's device in the first setup milestone.
- Do not clone Bruce or LilyGO source code until the implementation plan chooses the exact workflow.
- Do not provide instructions for unauthorized access, credential capture, stealth, persistence, evasion, jamming, disruption, or attacking third-party devices.
- Do not let experiments, course notes, and firmware build outputs mix in the same directories.

## Audience

The course assumes the learner:

- Is comfortable with software engineering, version control, debugging, and reading code.
- Is new to embedded constraints such as pins, buses, flashing, boot modes, power, storage, and hardware-driven failures.
- Wants advanced depth over a shallow gadget guide.
- Wants productive daily-use projects and responsible security literacy.

## Course Tracks

### Track A: Bruce Operator

This track keeps the installed firmware useful while the learner builds confidence. It covers:

- Device orientation, controls, menus, settings, and safe handling.
- Bruce navigation and feature literacy.
- File workflows with SD or onboard storage where applicable.
- WebUI and serial-command workflows where applicable.
- Safe backup/update habits before any flashing.
- Practical IR, NFC/RFID, BLE, Wi-Fi, CC1101, and nRF24 exploration within authorized boundaries.

### Track B: Builder Lab

This track teaches firmware development separately from the installed Bruce environment. It covers:

- ESP32-S3 development basics.
- PlatformIO setup and build/upload/debug loops.
- Serial logging and failure diagnosis.
- GPIO, SPI, I2C, display, rotary encoder/buttons, SD storage, battery/power, and peripheral integration.
- LilyGO examples before Bruce internals.
- Bruce source build and module customization only after the learner has backup/restore confidence.

## Zero-to-Master Progression

### Level 0: Unbox and Understand

Goal: Understand the hardware and risks before changing anything.

Topics:

- Board anatomy and major chips/modules.
- Bruce at a high level.
- Safe lab rules.
- What each wireless/peripheral capability can and cannot do.
- Personal learning log setup.

### Level 1: Operate Bruce Well

Goal: Become competent using the installed firmware.

Topics:

- Menus, settings, files, WebUI, updates, and backups.
- Known-device experiments with IR/NFC/RFID/BLE/Wi-Fi/RF features.
- Recording observations, versions, and reproducible steps.

### Level 2: Embedded Foundations

Goal: Learn embedded software through small, controlled programs.

Topics:

- ESP32-S3, Arduino framework, ESP-IDF awareness, and PlatformIO.
- Flashing, boot mode, serial logs, build environments.
- GPIO, I2C, SPI, TFT display, input controls, SD storage, battery monitoring.
- Debugging hardware/software symptoms.

### Level 3: Productivity Toolkit

Goal: Build useful daily tools on the device.

Candidate projects:

- On-device dashboard with clock, battery, status, and shortcuts.
- Timers and focus workflows.
- Quick capture to SD: notes, tasks, timestamps, simple logs.
- QR/contact helpers.
- IR and NFC personal automations for owned devices and tags.
- Portable command-center menu that ties features together.

### Level 4: Protocol Literacy

Goal: Understand protocols defensively and experimentally.

Topics:

- NFC/RFID concepts with the user's own tags.
- IR signal learning and replay for owned devices.
- BLE and Wi-Fi discovery as inventory and security posture tools.
- CC1101 and nRF24 receive-first lessons, legal-band awareness, and owned-device experiments.
- Logging, comparing, and explaining signals without abusing them.

### Level 5: Bruce Internals

Goal: Move from user to contributor/customizer.

Topics:

- Bruce repository structure.
- Build environments and board definitions.
- Menu/module architecture.
- Storage/config conventions.
- Adding a small custom module.
- Debugging crashes or missing peripheral behavior.

### Level 6: Capstones

Goal: Demonstrate advanced independent competence.

Capstones:

- Personal productivity toolkit firmware or Bruce module.
- Authorized home/lab security audit workflow.
- Maintainable custom firmware workflow with docs, tests/checks, and rollback notes.

## Repository Structure

The first setup milestone should create this structure:

```text
.
├── AGENTS.md
├── README.md
├── docs/
│   ├── course/
│   │   ├── 00-unbox-and-understand/
│   │   ├── 01-operate-bruce-well/
│   │   ├── 02-embedded-foundations/
│   │   ├── 03-productivity-toolkit/
│   │   ├── 04-protocol-literacy/
│   │   ├── 05-bruce-internals/
│   │   └── 06-capstones/
│   ├── reference/
│   │   ├── hardware.md
│   │   ├── legal-and-safety.md
│   │   ├── glossary.md
│   │   └── resources.md
│   └── superpowers/specs/
├── templates/
│   ├── lesson.md
│   ├── lab.md
│   └── project.md
├── firmware/
│   ├── README.md
│   ├── lilygo-examples/
│   ├── bruce-sandbox/
│   └── productivity-toolkit/
├── tools/
│   └── README.md
└── notes/
    └── learning-log.md
```

## File Responsibilities

- `README.md`: Human entrypoint, course promise, path through levels, and first steps.
- `AGENTS.md`: Codex working rules for this repo, including safety, source freshness, PlatformIO preference, verification, and documentation standards.
- `docs/course/COURSE_MAP.md`: Course overview, level order, milestones, and suggested pacing.
- `docs/course/*/README.md`: Level introductions, learning outcomes, prerequisites, and lesson index.
- `docs/reference/hardware.md`: Board facts, pin/peripheral references, source links, and user observations.
- `docs/reference/legal-and-safety.md`: Authorization model, RF/NFC/Wi-Fi/BLE/IR rules, and prohibited work.
- `docs/reference/glossary.md`: Embedded, Bruce, and protocol terms.
- `docs/reference/resources.md`: Curated official docs and selected learning resources.
- `templates/lesson.md`: Standard lesson format.
- `templates/lab.md`: Standard lab format with safety, materials, steps, verification, and cleanup.
- `templates/project.md`: Standard project format with goals, architecture, data flow, tests, and reflection.
- `firmware/README.md`: Explains dual-track firmware strategy and where source trees will live later.
- `tools/README.md`: Placeholder for future scripts such as environment checks.
- `notes/learning-log.md`: User-owned learning journal.

## Safety and Cybersecurity Model

Every cybersecurity lesson must declare:

- Target ownership or explicit authorization.
- Whether the lab is receive-only, local-only, or allowed to transmit.
- Legal/regulatory considerations for the user's region.
- Cleanup and rollback steps.
- What observations are safe to record.

Allowed:

- Learning Bruce features on owned/authorized targets.
- Defensive inventory and posture checks.
- Reading/writing owned NFC tags.
- IR learning/replay for owned devices.
- BLE/Wi-Fi discovery in owned/authorized environments.
- RF receive-first experiments and legal, owned-device transmission labs when explicitly scoped.

Prohibited:

- Unauthorized access to devices, networks, tags, or systems.
- Credential capture or replay.
- Jamming or disruption.
- Stealth, persistence, evasion, or bypassing access controls.
- Instructions intended to attack third-party systems.

## Firmware Strategy

The repo should start with placeholders and documentation. Source code comes later through an implementation plan.

Planned firmware lanes:

- `firmware/lilygo-examples/`: official LilyGO examples or guided copies used for foundation labs.
- `firmware/bruce-sandbox/`: Bruce source or fork workflow after backup/restore confidence.
- `firmware/productivity-toolkit/`: custom course-built firmware or modules for daily productivity tools.

The implementation plan should decide whether to use submodules, plain clones, copied examples, or scripted setup. The initial course setup should not assume that choice.

## Codex Best-Practice Requirements

The repo should include durable Codex instructions in `AGENTS.md` that say:

- Treat this as an embedded learning and safety-sensitive course repo.
- Prefer current official sources for hardware, Bruce, and PlatformIO facts.
- Keep lessons and labs reproducible, with "done when" checks.
- Keep cybersecurity labs authorized-only and reject unsafe scope.
- Keep firmware build artifacts out of committed docs.
- Add verification steps for every code or environment change.
- Use focused commits and summarize sources when facts may change.

## First Milestone Scope

The first implementation milestone is repository foundation only:

- Initialize git if not already initialized.
- Add README, AGENTS, reference docs, course map, level directories, templates, firmware placeholder, tools placeholder, and learning log.
- Add this design spec under `docs/superpowers/specs/`.
- Do not flash the device.
- Do not clone large upstream source trees.
- Do not implement firmware functionality yet.

## Error Handling and Recovery

Course materials should teach recovery as a normal part of embedded work:

- Record board variant, firmware version, and observations before changing anything.
- Capture backup/restore steps before any flashing lesson.
- Include "if this fails" sections for common embedded failures: missing port, wrong board environment, boot mode, serial permission, dependency download failure, blank screen, missing peripheral, SD not mounted, and build errors.
- Keep destructive operations explicit and separate from learning explanations.

## Verification Strategy

Documentation verification:

- Links point to current official sources where possible.
- Lessons have prerequisites, steps, expected output, and done-when checks.
- Labs declare authorization and safety constraints.
- Templates are internally consistent.

Firmware verification, when code is added later:

- PlatformIO build passes for the selected environment.
- Upload instructions are tested or clearly marked as not yet device-verified.
- Serial output or screen behavior is documented as expected evidence.
- Any Bruce module change includes a source-level review and rollback path.

## Risks and Mitigations

- Risk: Scope becomes too broad.
  Mitigation: Keep each lesson, lab, and project small; use capstones for integration.

- Risk: Bruce or LilyGO docs change.
  Mitigation: Store source links and refresh facts before hardware-specific changes.

- Risk: The learner flashes too early and loses a working device.
  Mitigation: Start with Bruce operation and backup/restore confidence before custom firmware.

- Risk: Cybersecurity content crosses unsafe boundaries.
  Mitigation: Require explicit authorization and prohibit unauthorized access, disruption, stealth, and credential misuse.

- Risk: Firmware and notes become tangled.
  Mitigation: Separate `docs/`, `firmware/`, `templates/`, `tools/`, and `notes/`.

## Acceptance Criteria

The design is implemented when:

- The repository has the agreed course-first structure.
- README clearly communicates the zero-to-master path.
- AGENTS.md gives Codex practical, repo-specific rules.
- Reference docs cover hardware, legal/safety, glossary, and resources.
- Course map and level READMEs define the learning progression.
- Templates make future lessons/labs/projects consistent.
- Firmware directories are documented but do not yet contain unplanned source trees.
- The design spec is committed and reviewed before writing the implementation plan.

## Next Step

After the user reviews and approves this written spec, invoke the writing-plans skill to produce a detailed implementation plan for the first repository setup milestone.
