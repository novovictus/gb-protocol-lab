# EXP-20260804-001: Historical OSCR dump validation

## Record type

Historical reconstruction created 2026-08-04. Exact bench date not yet recovered.

## Objective

Preserve the reported completion state of the OSCR acquisition workflow without inventing missing metadata.

## Hardware

- OSCR: built; revision unknown
- Game Boy cartridge: identity not recorded in this reconstruction
- Host computer: not recorded

## Software

- OSCR firmware: not recorded
- Host software/version: not recorded
- Emulator/version: not recorded

## Procedure retained from history

1. Build OSCR.
2. Dump Game Boy ROM data.
3. Dump Game Boy save data.
4. Load produced output in an emulator.
5. Confirm usable behavior.

## Observed results retained from history

- ROM dumping worked.
- Save dumping worked.
- Output was validated in an emulator.

Classification: `observed/reported`.

## What is not established

- exact source cartridge;
- exact image/save filenames;
- cryptographic hashes;
- repeated-dump equality;
- emulator identity/version;
- scope of emulator validation;
- write/flash behavior during this specific experiment;
- relevance to the IZEK communication protocol.

## Required reproduction package

- hardware photographs;
- OSCR PCB and firmware versions;
- host software/version;
- complete command transcript;
- cartridge label and header metadata;
- ROM and save byte lengths;
- SHA-256 hashes from two independent reads;
- emulator/version and launch procedure;
- screenshot or video showing the exact hashed output in use;
- redistribution statement.

## Related evidence

- EVD-20260804-003
- EVD-20260804-004
- EVD-20260804-005
- EVD-20260804-006
