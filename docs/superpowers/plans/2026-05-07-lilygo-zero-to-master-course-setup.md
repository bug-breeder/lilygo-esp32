# LilyGO Zero-to-Master Course Setup Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build the first repository foundation for a zero-to-master LilyGO T-Embed CC1101 Plus course and development workspace.

**Architecture:** This milestone creates documentation and directory scaffolding only. The repo is organized around a human learning path in `docs/course/`, durable agent guidance in `AGENTS.md`, source-backed reference material in `docs/reference/`, reusable authoring templates in `templates/`, and isolated future firmware lanes in `firmware/`.

**Tech Stack:** Markdown, Git, shell verification commands; no firmware build system is installed or cloned in this milestone.

---

## Source Spec

Implement the approved design in `docs/superpowers/specs/2026-05-07-lilygo-zero-to-master-course-design.md`.

## File Structure

Create or modify these files:

- Create: `README.md`
  - Human entrypoint, zero-to-master promise, course path, first steps, and safety stance.
- Create: `AGENTS.md`
  - Codex repository rules: safety boundaries, source freshness, documentation standards, firmware workflow constraints, and verification expectations.
- Create: `docs/course/COURSE_MAP.md`
  - Course level overview, tracks, outcomes, pacing, and milestone definitions.
- Create: `docs/course/00-unbox-and-understand/README.md`
  - Level 0 goals, lessons, labs, done-when checks, and mastery extensions.
- Create: `docs/course/01-operate-bruce-well/README.md`
  - Level 1 goals, lessons, labs, done-when checks, and mastery extensions.
- Create: `docs/course/02-embedded-foundations/README.md`
  - Level 2 goals, lessons, labs, done-when checks, and mastery extensions.
- Create: `docs/course/03-productivity-toolkit/README.md`
  - Level 3 goals, lessons, labs, done-when checks, and mastery extensions.
- Create: `docs/course/04-protocol-literacy/README.md`
  - Level 4 goals, lessons, labs, safety rules, done-when checks, and mastery extensions.
- Create: `docs/course/05-bruce-internals/README.md`
  - Level 5 goals, lessons, labs, done-when checks, and mastery extensions.
- Create: `docs/course/06-capstones/README.md`
  - Level 6 goals, capstone choices, evaluation criteria, and maintenance expectations.
- Create: `docs/reference/hardware.md`
  - Board facts with source links, variant notes, and observation log.
- Create: `docs/reference/legal-and-safety.md`
  - Authorization rules, allowed work, prohibited work, and lab declaration pattern.
- Create: `docs/reference/glossary.md`
  - Embedded, Bruce, and protocol terms used by the course.
- Create: `docs/reference/resources.md`
  - Curated official resources and selected learning categories.
- Create: `templates/lesson.md`
  - Repeatable lesson skeleton.
- Create: `templates/lab.md`
  - Repeatable lab skeleton with safety and verification sections.
- Create: `templates/project.md`
  - Repeatable project skeleton with architecture, testing, and reflection sections.
- Create: `firmware/README.md`
  - Firmware lane explanation and rules for future source setup.
- Create: `firmware/lilygo-examples/.gitkeep`
  - Preserve the directory for future LilyGO example work.
- Create: `firmware/bruce-sandbox/.gitkeep`
  - Preserve the directory for future Bruce source work.
- Create: `firmware/productivity-toolkit/.gitkeep`
  - Preserve the directory for future custom productivity firmware.
- Create: `tools/README.md`
  - Scope for future environment and validation scripts.
- Create: `notes/learning-log.md`
  - User-owned learning log template.

Do not clone upstream repositories, flash hardware, install dependencies, or add firmware source in this milestone.

---

### Task 1: Root Entry Points

**Files:**
- Create: `README.md`
- Create: `AGENTS.md`

- [ ] **Step 1: Create `README.md`**

Create `README.md` with this exact content:

```md
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
```

- [ ] **Step 2: Create `AGENTS.md`**

Create `AGENTS.md` with this exact content:

```md
# AGENTS.md

## Repository Purpose

This repo is a zero-to-master course and development workspace for the LilyGO T-Embed CC1101 Plus with Bruce firmware. Treat it as an embedded learning repo with safety-sensitive white-hat cybersecurity content.

## Working Rules

- Keep the course useful for a strong software engineer who is new to embedded development.
- Prefer small, focused files over large mixed-purpose documents.
- Keep course docs, reference docs, firmware workspaces, tools, and notes separated by directory responsibility.
- Do not flash hardware, install dependencies, clone upstream source trees, or add firmware code unless the active task explicitly asks for it.
- Preserve user notes in `notes/` and avoid rewriting personal observations unless asked.

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
```

- [ ] **Step 3: Verify root entry points**

Run:

```bash
test -f README.md && test -f AGENTS.md
rg -n "zero-to-master|Safety Boundary|PlatformIO|unauthorized access" README.md AGENTS.md
```

Expected:

- `test` exits with status 0.
- `rg` prints lines from both files containing the searched terms.

- [ ] **Step 4: Commit root entry points**

Run:

```bash
git add README.md AGENTS.md
git commit -m "docs: add course entry points"
```

Expected:

- Git creates a commit with `README.md` and `AGENTS.md`.

---

### Task 2: Reference Documents

**Files:**
- Create: `docs/reference/hardware.md`
- Create: `docs/reference/legal-and-safety.md`
- Create: `docs/reference/glossary.md`
- Create: `docs/reference/resources.md`

- [ ] **Step 1: Create `docs/reference/hardware.md`**

Create `docs/reference/hardware.md` with this exact content:

```md
# Hardware Reference

This page records the working hardware model for the LilyGO T-Embed CC1101 Plus course. Recheck official sources before changing pin maps, board environments, or firmware assumptions.

## Board

- Product: LilyGO T-Embed CC1101 Plus.
- MCU: ESP32-S3 dual-core LX7.
- Flash: 16MB.
- PSRAM: 8MB.
- Display: 1.9 inch ST7789V IPS color TFT LCD over SPI.
- Wireless: Wi-Fi 802.11 b/g/n and BLE 5 from ESP32-S3.
- Sub-GHz radio: CC1101.
- 2.4GHz radio on Plus variant: nRF24L01 module.
- NFC/RFID: PN532 module over I2C.
- IR: transmit and receive support.
- Power observation: battery voltage detection is listed on IO04 by LilyGO.

## Source Links

- LilyGO product page: https://lilygo.cc/en-us/products/t-embed-cc1101-plus
- LilyGO wiki: https://wiki.lilygo.cc/get_started/en/Wearable/T-Embed-CC1101/T-Embed-CC1101.html
- LilyGO GitHub examples: https://github.com/Xinyuan-LilyGO/T-Embed-CC1101
- Bruce firmware: https://github.com/BruceDevices/firmware

## Course Assumptions

- The device currently has Bruce installed.
- The first course stage does not replace firmware.
- PlatformIO is the preferred build workflow for later firmware lessons.
- Exact board environment names must be verified from the selected upstream source before building or flashing.

## User Observation Log

Record the physical device details here before flashing or opening the case:

- Purchase date:
- Board label or silkscreen:
- Bruce version:
- Boot behavior:
- Battery behavior:
- SD card present:
- USB serial port name:
- Notes:
```

- [ ] **Step 2: Create `docs/reference/legal-and-safety.md`**

Create `docs/reference/legal-and-safety.md` with this exact content:

```md
# Legal and Safety Rules

This course teaches embedded systems, personal productivity tooling, and white-hat cybersecurity. Every security or wireless exercise must stay inside owned devices, explicit permission, or isolated lab environments.

## Core Rule

Only test systems you own or have explicit permission to test. When permission or legality is unclear, stop and document the uncertainty instead of experimenting.

## Allowed Work

- Learning Bruce features on your own LilyGO device.
- Reading and writing your own NFC tags.
- Learning and replaying IR signals for devices you own.
- BLE and Wi-Fi discovery in your own home, lab, or authorized workspace.
- RF receive-only observations where local law allows passive reception.
- RF transmission only in explicitly scoped labs using owned devices and legal frequencies/settings.
- Defensive inventory, configuration review, and security posture notes.
- Personal productivity tools that store your own data.

## Prohibited Work

- Unauthorized access to devices, networks, tags, accounts, or systems.
- Capturing, storing, replaying, or sharing credentials or secrets.
- Bypassing access controls.
- Jamming, disruption, denial of service, or interference.
- Stealth, persistence, evasion, or covert monitoring.
- Attacking third-party devices or public infrastructure.
- Transmitting RF signals without a clear legal basis and owned or authorized target.

## Lab Declaration Pattern

Every security or wireless lab must state:

- **Target:** The owned or authorized device/environment.
- **Authorization:** Why this activity is allowed.
- **Mode:** Receive-only, local-only, or transmit-capable.
- **Region/legal note:** The rule or uncertainty that matters for the learner's location.
- **Data captured:** What observations are safe to record.
- **Cleanup:** How to restore the environment after the lab.
- **Stop condition:** A clear point where the learner must stop if results are unexpected.

## Practical Safety Habits

- Photograph or write down the current device state before changing firmware.
- Keep version numbers, board variant notes, and serial output in the learning log.
- Prefer read-only observation before writing, transmitting, or replaying.
- Use test tags, owned remotes, and lab devices instead of real access systems.
- Keep backups and rollback instructions close to any flashing lesson.
```

- [ ] **Step 3: Create `docs/reference/glossary.md`**

Create `docs/reference/glossary.md` with this exact content:

```md
# Glossary

## Embedded Basics

- **ESP32-S3:** Espressif microcontroller used by the LilyGO T-Embed CC1101 Plus.
- **Firmware:** Software that runs directly on the device.
- **Flash:** Non-volatile storage used for firmware and persistent data.
- **PSRAM:** External RAM used for larger runtime buffers.
- **GPIO:** General-purpose input/output pins.
- **I2C:** Two-wire bus commonly used for sensors and modules such as PN532.
- **SPI:** High-speed bus commonly used for displays, SD cards, and radio modules.
- **UART/Serial:** Communication channel used for logs, shells, and flashing workflows.
- **Boot mode:** Device state used to receive new firmware over USB/serial.

## Board and Firmware

- **Bruce:** ESP32 firmware focused on security research features and multi-device support.
- **PlatformIO:** Build and project tool commonly used for ESP32 Arduino and embedded projects.
- **Board environment:** A PlatformIO configuration entry that selects board, framework, flags, libraries, and build settings.
- **WebUI:** Browser-based interface exposed by firmware for file or device interaction when supported.

## Protocols and Modules

- **CC1101:** Sub-GHz RF transceiver used for learning radio concepts and owned-device experiments.
- **nRF24L01:** 2.4GHz transceiver module included on the Plus variant.
- **PN532:** NFC/RFID controller used for reading and writing compatible tags.
- **IR:** Infrared light communication commonly used by remote controls.
- **BLE:** Bluetooth Low Energy.
- **Wi-Fi scanning:** Discovery of nearby Wi-Fi networks or device metadata without joining or attacking them.

## Security Terms

- **White-hat:** Authorized security learning or testing intended to improve safety.
- **Authorization:** Explicit permission to test a device, system, or environment.
- **Receive-only:** Observing signals without transmitting.
- **Replay:** Re-sending a previously captured signal; allowed only for owned devices in scoped labs.
- **Jamming:** Deliberate interference or disruption; prohibited in this course.
```

- [ ] **Step 4: Create `docs/reference/resources.md`**

Create `docs/reference/resources.md` with this exact content:

```md
# Resources

Use primary sources when adding hardware, firmware, or protocol facts.

## Official Device Sources

- LilyGO T-Embed CC1101 Plus product page: https://lilygo.cc/en-us/products/t-embed-cc1101-plus
- LilyGO T-Embed CC1101 wiki: https://wiki.lilygo.cc/get_started/en/Wearable/T-Embed-CC1101/T-Embed-CC1101.html
- LilyGO T-Embed CC1101 GitHub repository: https://github.com/Xinyuan-LilyGO/T-Embed-CC1101

## Bruce Sources

- Bruce firmware repository: https://github.com/BruceDevices/firmware
- Bruce website: https://bruce.computer/
- Bruce building from source wiki: https://github.com/pr3y/Bruce/wiki/Building-from-source

## Tooling Sources

- PlatformIO documentation: https://docs.platformio.org/
- Espressif ESP32-S3 documentation: https://docs.espressif.com/projects/esp-idf/en/latest/esp32s3/

## Chip and Protocol Sources

- TI CC1101 product page and datasheet: https://www.ti.com/product/CC1101
- Nordic nRF24L01 product information: https://www.nordicsemi.com/Products/nRF24-series
- NXP PN532 product information: https://www.nxp.com/products/rfid-nfc/nfc-hf/nfc-readers/pn532-c1-near-field-communication-nfc-controller:PN532_C1

## Course Resource Rules

- Prefer official docs and datasheets for facts.
- Use community posts for troubleshooting clues, not as the only source of truth.
- Record the date when a fact is likely to change, such as firmware version behavior or board environment names.
```

- [ ] **Step 5: Verify reference documents**

Run:

```bash
test -f docs/reference/hardware.md
test -f docs/reference/legal-and-safety.md
test -f docs/reference/glossary.md
test -f docs/reference/resources.md
rg -n "ESP32-S3|CC1101|nRF24L01|PN532|unauthorized|PlatformIO" docs/reference
```

Expected:

- Each `test` exits with status 0.
- `rg` prints lines from all four reference files.

- [ ] **Step 6: Commit reference documents**

Run:

```bash
git add docs/reference
git commit -m "docs: add hardware and safety references"
```

Expected:

- Git creates a commit with the four `docs/reference/` files.

---

### Task 3: Course Map and Level Guides

**Files:**
- Create: `docs/course/COURSE_MAP.md`
- Create: `docs/course/00-unbox-and-understand/README.md`
- Create: `docs/course/01-operate-bruce-well/README.md`
- Create: `docs/course/02-embedded-foundations/README.md`
- Create: `docs/course/03-productivity-toolkit/README.md`
- Create: `docs/course/04-protocol-literacy/README.md`
- Create: `docs/course/05-bruce-internals/README.md`
- Create: `docs/course/06-capstones/README.md`

- [ ] **Step 1: Create `docs/course/COURSE_MAP.md`**

Create `docs/course/COURSE_MAP.md` with this exact content:

```md
# Course Map

This course takes a software engineer from embedded zero to confident LilyGO T-Embed CC1101 Plus practice. It uses Bruce first, then moves into PlatformIO, custom firmware, productivity tools, protocol literacy, and advanced capstones.

## Tracks

- **Bruce Operator:** Learn the installed firmware, safe workflows, and practical feature use.
- **Builder Lab:** Learn embedded development and build custom tools in isolated firmware workspaces.

## Levels

| Level | Name | Main Outcome |
| --- | --- | --- |
| 0 | Unbox and Understand | Explain the board, safety model, and current firmware state. |
| 1 | Operate Bruce Well | Use Bruce confidently without changing firmware. |
| 2 | Embedded Foundations | Build and debug small ESP32-S3 programs with PlatformIO. |
| 3 | Productivity Toolkit | Build personal tools such as timers, quick capture, dashboards, and automations. |
| 4 | Protocol Literacy | Understand NFC, IR, BLE, Wi-Fi, CC1101, and nRF24 within authorized labs. |
| 5 | Bruce Internals | Build Bruce from source and add a small custom behavior. |
| 6 | Capstones | Deliver advanced productivity and authorized security workflows. |

## Suggested Rhythm

For each lesson:

1. Read the concept section.
2. Run the lab on owned or authorized equipment.
3. Capture evidence in `notes/learning-log.md`.
4. Complete the done-when checks.
5. Try the mastery extension only after the baseline works.

## Milestones

- **M0:** Course scaffold exists and safety rules are visible.
- **M1:** Device state is documented and Bruce is used safely.
- **M2:** PlatformIO environment builds a known-good example.
- **M3:** First custom productivity feature works on-device or in a simulated build.
- **M4:** Protocol labs are documented with authorization and cleanup notes.
- **M5:** Bruce source is built locally and a small module/customization is understood.
- **M6:** Capstone is documented, reproducible, and reversible.
```

- [ ] **Step 2: Create level README files**

Create `docs/course/00-unbox-and-understand/README.md` with this exact content:

```md
# Level 0: Unbox and Understand

## Goal

Understand the device, its current firmware state, and the safety model before changing anything.

## Lessons

- Board anatomy and major components.
- What Bruce is and what it can do.
- How to record device state.
- Safety rules for wireless and security learning.

## Labs

- Inspect the board without disassembly.
- Record firmware version, boot behavior, buttons, display behavior, and serial port name.
- Create the first learning-log entry.

## Done When

- You can name the major modules: ESP32-S3, display, PN532, CC1101, nRF24L01, IR, and storage.
- You have recorded the current device state in `notes/learning-log.md`.
- You have read `docs/reference/legal-and-safety.md`.

## Mastery Extension

Draw your own block diagram of the device and explain which modules use SPI, I2C, RF, IR, or USB/serial.
```

Create `docs/course/01-operate-bruce-well/README.md` with this exact content:

```md
# Level 1: Operate Bruce Well

## Goal

Use Bruce confidently while preserving a working device and documenting behavior.

## Lessons

- Bruce navigation and settings.
- File and storage workflows.
- WebUI or serial workflows when supported by the installed version.
- Backup and update concepts before flashing.

## Labs

- Navigate core menus and record what is available on this board.
- Change a harmless setting and restore it.
- Explore file access without deleting unknown files.
- Record the installed Bruce version and visible board-specific features.

## Done When

- You can navigate Bruce without guessing.
- You have a written backup/update plan before any future flashing.
- You can identify which features are available on your exact installed firmware.

## Mastery Extension

Create a personal Bruce operator checklist that you can run before every experiment.
```

Create `docs/course/02-embedded-foundations/README.md` with this exact content:

```md
# Level 2: Embedded Foundations

## Goal

Learn the embedded development loop for ESP32-S3 using small, controlled programs.

## Lessons

- ESP32-S3 mental model for a software engineer.
- PlatformIO project structure.
- Build, upload, serial monitor, and boot mode.
- GPIO, I2C, SPI, display, input, storage, and battery concepts.
- Debugging hardware/software symptoms.

## Labs

- Install and verify PlatformIO in a later planned milestone.
- Build a known-good LilyGO example in a later planned milestone.
- Read serial logs and map expected output to code.
- Exercise one peripheral at a time.

## Done When

- You can explain the build/upload/monitor loop.
- You can distinguish compile errors, upload errors, serial errors, and runtime hardware symptoms.
- You can find the board environment used by a selected PlatformIO project.

## Mastery Extension

Write a debugging decision tree for blank screen, missing serial port, failed upload, and missing peripheral cases.
```

Create `docs/course/03-productivity-toolkit/README.md` with this exact content:

```md
# Level 3: Productivity Toolkit

## Goal

Build practical tools that make the device useful in daily life.

## Lessons

- Small-device UX and menu design.
- SD-backed notes, tasks, and logs.
- Timers, dashboard state, and status display.
- QR/contact helpers.
- Personal automations through owned IR devices and NFC tags.

## Projects

- Device dashboard with clock, battery, status, and shortcuts.
- Timer and focus workflow.
- Quick capture to SD.
- QR helper for personal links or contact data.
- IR or NFC routine for an owned device or tag.

## Done When

- At least one productivity tool has a clear user story.
- Data storage and recovery behavior are documented.
- The tool can fail gracefully without losing existing notes or tasks.

## Mastery Extension

Design a portable command-center menu that ties capture, timers, dashboard, and automations into one flow.
```

Create `docs/course/04-protocol-literacy/README.md` with this exact content:

```md
# Level 4: Protocol Literacy

## Goal

Understand NFC, IR, BLE, Wi-Fi, CC1101, and nRF24 from a defensive, authorized perspective.

## Safety Rule

Every lab in this level must declare target, authorization, mode, legal note, captured data, cleanup, and stop condition before any experiment.

## Lessons

- NFC/RFID concepts using owned tags.
- IR remote concepts using owned devices.
- BLE and Wi-Fi discovery as inventory and posture review.
- CC1101 and nRF24 receive-first radio concepts.
- Why replay, transmission, and interference require strict boundaries.

## Labs

- Read an owned NFC tag and document its type.
- Learn an IR signal from an owned remote and replay only to the owned device.
- Inventory your own BLE/Wi-Fi environment without joining or attacking networks.
- Observe legal, owned RF signals in receive-only mode before any transmit-capable lab.

## Done When

- Each lab has an authorization declaration.
- You can explain what was observed without claiming more than the data supports.
- No lab requires unauthorized access, disruption, credential handling, or stealth.

## Mastery Extension

Write a defensive report for your own home/lab environment that lists assets, observations, risks, and improvements.
```

Create `docs/course/05-bruce-internals/README.md` with this exact content:

```md
# Level 5: Bruce Internals

## Goal

Move from Bruce user to careful Bruce builder and customizer.

## Lessons

- Bruce repository structure.
- PlatformIO environments and board definitions.
- Menu and module organization.
- Configuration and storage conventions.
- Debugging crashes, missing peripherals, and board-specific behavior.

## Labs

- Clone or reference Bruce source in a later planned milestone.
- Build the selected board environment.
- Trace one menu item from UI entry to implementation.
- Add a small custom behavior only after backup and rollback steps are documented.

## Done When

- You can build Bruce locally for the selected board environment.
- You can explain where a module lives and how it reaches the menu.
- You have a rollback path before flashing custom Bruce builds.

## Mastery Extension

Design a small Bruce module for one productivity workflow and document how it should be tested before flashing.
```

Create `docs/course/06-capstones/README.md` with this exact content:

```md
# Level 6: Capstones

## Goal

Demonstrate advanced, independent competence through documented and reversible projects.

## Capstone Options

- **Personal Productivity Toolkit:** A polished device workflow for capture, timers, status, and personal automations.
- **Authorized Security Audit Kit:** A documented process for inventorying and improving your own home/lab environment.
- **Maintainable Firmware Workflow:** A reproducible build, test, flash, observe, and rollback workflow for custom firmware or Bruce customization.

## Evaluation Criteria

- The project has a clear user story.
- The architecture is documented.
- Safety and authorization boundaries are explicit.
- Build or reproduction steps are clear.
- Failure modes and rollback steps are documented.
- Evidence is captured in the learning log.

## Done When

- Another careful engineer could reproduce the workflow from the docs.
- The project avoids unsafe cybersecurity scope.
- The final result is useful enough that you would keep it on the device.

## Mastery Extension

Write a retrospective: what you understand now that you did not understand at Level 0, and what the next serious firmware or security research project should be.
```

- [ ] **Step 3: Verify course files**

Run:

```bash
test -f docs/course/COURSE_MAP.md
find docs/course -name README.md | sort
rg -n "Goal|Done When|Mastery Extension|Authorization|PlatformIO|Productivity" docs/course
```

Expected:

- `test` exits with status 0.
- `find` prints seven level README files.
- `rg` prints matches across the course map and level guides.

- [ ] **Step 4: Commit course map and level guides**

Run:

```bash
git add docs/course
git commit -m "docs: add zero-to-master course map"
```

Expected:

- Git creates a commit with `docs/course/COURSE_MAP.md` and seven level README files.

---

### Task 4: Authoring Templates

**Files:**
- Create: `templates/lesson.md`
- Create: `templates/lab.md`
- Create: `templates/project.md`

- [ ] **Step 1: Create `templates/lesson.md`**

Create `templates/lesson.md` with this exact content:

```md
# Lesson: <Title>

## Level

Course level:

## Purpose

Explain what the learner will understand after this lesson.

## Prerequisites

- Required prior lesson:
- Required hardware:
- Required software:

## Concepts

- Concept 1:
- Concept 2:
- Concept 3:

## Walkthrough

1. Read the concept.
2. Inspect the relevant file, menu, board part, or tool.
3. Record the observation in `notes/learning-log.md`.

## Expected Evidence

- Observation:
- Screenshot/photo/serial output:
- Link to source used:

## Done When

- The learner can explain the concept without copying the lesson.
- The learner has recorded one concrete observation.
- The learner knows which lab or project uses this concept next.

## Reflection

- What surprised you?
- What still feels unclear?
- What would you test next?
```

- [ ] **Step 2: Create `templates/lab.md`**

Create `templates/lab.md` with this exact content:

```md
# Lab: <Title>

## Level

Course level:

## Purpose

State the skill this lab builds.

## Authorization and Safety

- **Target:**
- **Authorization:**
- **Mode:** Receive-only, local-only, or transmit-capable.
- **Region/legal note:**
- **Data captured:**
- **Cleanup:**
- **Stop condition:**

## Materials

- LilyGO T-Embed CC1101 Plus:
- Cable:
- SD card:
- Owned target device/tag/network:
- Software:

## Steps

1. Prepare the device.
2. Confirm the target and authorization.
3. Run the experiment.
4. Capture expected evidence.
5. Clean up and restore settings.

## Expected Evidence

- Device state:
- Serial output or screen behavior:
- Files created:
- Notes captured:

## Troubleshooting

- If the device is not detected, record the cable, port, and OS behavior.
- If the screen is blank, record boot behavior and whether serial logs appear.
- If a peripheral is missing, stop and verify board variant and firmware version.

## Done When

- The lab goal is met.
- Evidence is recorded in `notes/learning-log.md`.
- Cleanup is complete.
- No safety boundary was crossed.

## Mastery Extension

Describe one safe variation that deepens the same concept.
```

- [ ] **Step 3: Create `templates/project.md`**

Create `templates/project.md` with this exact content:

```md
# Project: <Title>

## Level

Course level:

## User Story

As the device owner, I want to <capability> so that <daily value>.

## Scope

### In Scope

- Capability 1:
- Capability 2:

### Out of Scope

- Capability intentionally excluded:
- Unsafe or unrelated behavior excluded:

## Architecture

Describe the modules, inputs, outputs, storage, and device UI.

## Data Flow

1. Input:
2. Processing:
3. Storage or transmission:
4. Output:

## Safety and Privacy

- Personal data stored:
- Wireless behavior:
- Authorization requirement:
- Cleanup or deletion path:

## Implementation Plan

1. Build the smallest useful version.
2. Verify the behavior.
3. Add error handling for the observed failure modes.
4. Document evidence and rollback.

## Test Plan

- Build check:
- Device behavior:
- Failure case:
- Data recovery:

## Done When

- The project satisfies the user story.
- The build or reproduction steps work.
- Evidence is recorded.
- Rollback or cleanup is documented.

## Reflection

- What design decision mattered most?
- What would you improve in a second version?
- What did this teach about embedded constraints?
```

- [ ] **Step 4: Verify templates**

Run:

```bash
test -f templates/lesson.md
test -f templates/lab.md
test -f templates/project.md
rg -n "Done When|Authorization and Safety|User Story|Expected Evidence" templates
```

Expected:

- Each `test` exits with status 0.
- `rg` prints template sections for lesson, lab, and project files.

- [ ] **Step 5: Commit templates**

Run:

```bash
git add templates
git commit -m "docs: add course authoring templates"
```

Expected:

- Git creates a commit with the three template files.

---

### Task 5: Firmware, Tools, and Learning Log

**Files:**
- Create: `firmware/README.md`
- Create: `firmware/lilygo-examples/.gitkeep`
- Create: `firmware/bruce-sandbox/.gitkeep`
- Create: `firmware/productivity-toolkit/.gitkeep`
- Create: `tools/README.md`
- Create: `notes/learning-log.md`

- [ ] **Step 1: Create firmware lane files**

Create `firmware/README.md` with this exact content:

```md
# Firmware Workspace

This directory is reserved for firmware work after the course scaffold is in place.

## Lanes

- `lilygo-examples/`: Future workspace for official LilyGO examples or guided copies used in embedded foundation labs.
- `bruce-sandbox/`: Future workspace for Bruce source builds and carefully scoped customizations.
- `productivity-toolkit/`: Future workspace for custom firmware or modules focused on daily productivity tools.

## Rules

- Do not clone upstream source trees into this directory without an implementation plan.
- Do not flash hardware until backup, board environment, serial port, and rollback steps are documented.
- Keep build artifacts out of git.
- Keep experiments isolated by lane.
- Prefer PlatformIO unless a later plan explicitly chooses another workflow.

## Future Verification

When firmware code is added later, each change should document:

- Build command.
- Selected board environment.
- Upload command, if tested.
- Serial output or screen evidence.
- Rollback path.
```

Create these directory marker files with empty content:

```bash
mkdir -p firmware/lilygo-examples firmware/bruce-sandbox firmware/productivity-toolkit
: > firmware/lilygo-examples/.gitkeep
: > firmware/bruce-sandbox/.gitkeep
: > firmware/productivity-toolkit/.gitkeep
```

- [ ] **Step 2: Create `tools/README.md`**

Create `tools/README.md` with this exact content:

```md
# Tools

This directory is reserved for small helper scripts that make the course more reproducible.

Future scripts may check:

- Required command-line tools.
- PlatformIO installation.
- Connected serial ports.
- Markdown link health.
- Expected course file structure.

No helper script is required for the first scaffold milestone.
```

- [ ] **Step 3: Create `notes/learning-log.md`**

Create `notes/learning-log.md` with this exact content:

```md
# Learning Log

Use this file to record observations, commands, serial output, device state, mistakes, and questions.

## Device Baseline

- Date:
- Board:
- Bruce version:
- USB cable/port:
- SD card:
- Battery state:
- Boot behavior:
- Notes:

## Entries

### 2026-05-07: Course Scaffold

- Created the repo structure for the zero-to-master course.
- No firmware flashing or device modification happened in this milestone.
```

- [ ] **Step 4: Verify firmware, tools, and notes**

Run:

```bash
test -f firmware/README.md
test -f firmware/lilygo-examples/.gitkeep
test -f firmware/bruce-sandbox/.gitkeep
test -f firmware/productivity-toolkit/.gitkeep
test -f tools/README.md
test -f notes/learning-log.md
rg -n "PlatformIO|No firmware flashing|serial ports|Bruce version" firmware tools notes
```

Expected:

- Each `test` exits with status 0.
- `rg` prints matches from `firmware/README.md`, `tools/README.md`, and `notes/learning-log.md`.

- [ ] **Step 5: Commit firmware, tools, and notes**

Run:

```bash
git add firmware tools notes
git commit -m "docs: add firmware lanes and learning log"
```

Expected:

- Git creates a commit with firmware lane documentation, directory marker files, tools README, and learning log.

---

### Task 6: Final Verification

**Files:**
- Verify: all files created in Tasks 1-5
- Verify: `docs/superpowers/specs/2026-05-07-lilygo-zero-to-master-course-design.md`

- [ ] **Step 1: Verify expected file set**

Run:

```bash
find . -path ./.git -prune -o -type f -print | sort
```

Expected output includes exactly these project files, plus the existing design spec and this plan:

```text
./AGENTS.md
./README.md
./docs/course/00-unbox-and-understand/README.md
./docs/course/01-operate-bruce-well/README.md
./docs/course/02-embedded-foundations/README.md
./docs/course/03-productivity-toolkit/README.md
./docs/course/04-protocol-literacy/README.md
./docs/course/05-bruce-internals/README.md
./docs/course/06-capstones/README.md
./docs/course/COURSE_MAP.md
./docs/reference/glossary.md
./docs/reference/hardware.md
./docs/reference/legal-and-safety.md
./docs/reference/resources.md
./docs/superpowers/plans/2026-05-07-lilygo-zero-to-master-course-setup.md
./docs/superpowers/specs/2026-05-07-lilygo-zero-to-master-course-design.md
./firmware/README.md
./firmware/bruce-sandbox/.gitkeep
./firmware/lilygo-examples/.gitkeep
./firmware/productivity-toolkit/.gitkeep
./notes/learning-log.md
./templates/lab.md
./templates/lesson.md
./templates/project.md
./tools/README.md
```

- [ ] **Step 2: Verify safety language**

Run:

```bash
rg -n "unauthorized|credential|jamming|owned|authorized|receive-only|Safety" README.md AGENTS.md docs templates firmware notes
```

Expected:

- Matches appear in `README.md`, `AGENTS.md`, `docs/reference/legal-and-safety.md`, `docs/course/04-protocol-literacy/README.md`, and `templates/lab.md`.

- [ ] **Step 3: Verify no accidental firmware/source setup**

Run:

```bash
find firmware -maxdepth 3 -type f | sort
```

Expected output:

```text
firmware/README.md
firmware/bruce-sandbox/.gitkeep
firmware/lilygo-examples/.gitkeep
firmware/productivity-toolkit/.gitkeep
```

- [ ] **Step 4: Verify clean Git state**

Run:

```bash
git status --short
```

Expected:

- No output.

- [ ] **Step 5: Summarize implementation**

In the final response, include:

- Files created by category.
- Verification commands run.
- Confirmation that no firmware flashing, upstream cloning, or dependency installation happened.
- Suggested next course milestone: begin Level 0 by recording device baseline.

---

## Self-Review Notes

Spec coverage:

- Zero-to-master course path is implemented by `README.md`, `docs/course/COURSE_MAP.md`, and seven level README files.
- Dual-track Bruce/operator and builder/lab structure is implemented by `README.md`, `docs/course/COURSE_MAP.md`, and `firmware/README.md`.
- Productivity focus is implemented by Level 3 and capstone docs.
- Authorized cybersecurity scope is implemented by `AGENTS.md`, `docs/reference/legal-and-safety.md`, Level 4, and lab template.
- Codex best practices are implemented by `AGENTS.md` and verification tasks.
- First milestone avoids flashing, cloning, dependencies, and firmware implementation.

Plan checks:

- Every planned file has a path and exact initial content.
- Every task has shell verification and a commit step except the final verification task.
- The plan creates documentation and directory structure only.
