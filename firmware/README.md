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
