# EXP-20260804-003: Historical OSCR write and redump validation

## Record type

Historical reconstruction created 2026-08-04. Exact bench dates have not been recovered.

## Objective

Preserve two reported successful rewritable-cartridge workflows and the configuration detail that resolved the InsideGadgets write failure.

## Experiment A: FunnyPlaying EverSave

### Hardware

- Writer/reader: OSCR, exact revision unknown
- Target: FunnyPlaying EverSave GB/GBC Flash Cart Pro

### Input

- Singer/IZEK operation image
- Exact filename, source provenance, byte length, and hash not recorded in this reconstruction

### Reported procedure

1. Select a compatible OSCR write profile.
2. Write the image to the EverSave cartridge.
3. Read the cartridge back with OSCR.
4. Confirm that the redump completed.

### Reported result

Write and redump succeeded.

Classification: `observed/reported`.

## Experiment B: InsideGadgets MBC5 FRAM cartridge

### Hardware

- Writer/reader: OSCR, exact revision unknown
- Target: InsideGadgets MBC5 2 MiB / 32 KiB FRAM cartridge
- Reported flash device: M29F160F

### Input

- `Jaguar Mishin Sashi Senyou Soft - Kirby Family (Japan) (Proto)`
- Exact filename, byte length, source provenance, and hash not recorded in this reconstruction

### Configuration reported as successful

- OSCR profile: `CFI Repro`
- Write-enable selection: `WE=WR`

### Diagnostic history

- `HEADER CHECKSUM ERROR` appeared while the cartridge was blank or uninitialized and was not treated as the final blocker.
- `Flash ID: 0101 / Unknown flashrom` was the effective blocker under the unsuccessful path.
- The generic `29F Repro` path did not produce the successful result.
- Selecting `CFI Repro` with `WE=WR` produced the reported successful write and redump.

### Reported result

Write and redump succeeded.

Classification: `observed/reported`.

## What is not established

- equality of source image and redump;
- SHA-256 or other hashes;
- exact OSCR build, firmware, and host version;
- complete console transcript;
- number of repeated successful cycles;
- behavior on original Game Boy hardware;
- behavior when connected to the Singer IZEK;
- whether the diagnostic interpretation generalizes to other cartridge revisions.

## Required reproduction package

- cartridge front/back and PCB photographs;
- visible flash and mapper markings;
- OSCR PCB and firmware identification;
- host software version;
- complete read/write/redump transcripts;
- lawful source metadata and SHA-256;
- redump SHA-256 and byte-for-byte comparison result;
- original-hardware boot test;
- machine-interface test recorded as a separate experiment.
