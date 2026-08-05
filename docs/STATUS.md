# Project Status

Last updated: 2026-08-04

## Phase

Physical baseline validation, deterministic cartridge workflow verification, intended-hardware compatibility testing, and prior-art mapping.

Protocol implementation remains deferred until the machine and software path are validated and a project-generated capture exists.

## Current state

Artifact-backed repository facts:

- Shonumi's article and its 2026-03-07 archive are recorded.
- GBE+ is recorded as relevant GPLv2 prior art.
- The project now has a compact canonical notebook and inventory structure.

Results retained as `observed/reported`:

- OSCR was assembled; Game Boy ROM and save reads worked; at least one output was usable in an emulator.
- A replacement controller powered the Singer IZEK and produced basic machine motion.
- A Singer/IZEK image was reportedly written to and redumped from a FunnyPlaying EverSave cart.
- The Kirby sewing title was reportedly written to and redumped from an InsideGadgets MBC5 2 MiB / 32 KiB FRAM cart.
- The successful InsideGadgets path reportedly used OSCR `CFI Repro`, `WE=WR`, and M29F160F-compatible behavior; generic `29F Repro` was not the successful path.
- Original Game Boy hardware is the preferred behavioral baseline; EZ-Flash Jr reportedly differed between original and FPGA hardware.
- The external workbook `izek_test_matrix_canonical_saved_2026-05-03.xlsx` reportedly contains the canonical software compatibility matrix.

## Claim boundary

Not established:

- a valid threaded stitch;
- flash-cart communication with the physical IZEK;
- connector pinout or voltage levels;
- signaling direction or clock ownership;
- packet format, commands, timing, status values, or stitch encoding;
- model equivalence among Singer IZEK 1500, Jaguar JN-100, and Jaguar JN-2000;
- independent reproduction of Shonumi's protocol findings.

## Blockers

1. No documented straight-stitch test.
2. No committed OSCR logs, hashes, version records, or cartridge photographs.
3. No imported or hashed safe derivative of the canonical compatibility workbook.
4. No documented flash-cart test with the physical IZEK.
5. No claim-level map of Shonumi's article and GBE+ symbols.
6. No protected passive breakout or project-generated electrical capture.

## Immediate actions

1. Record one repeatable straight-stitch test with both sides photographed.
2. Inventory exact console, cartridge, OSCR, firmware, and host-software revisions.
3. Reproduce ROM/save reads and both write/redump paths with complete logs and SHA-256 hashes.
4. Import a redistribution-safe compatibility-matrix derivative and hash the source workbook.
5. Boot exact redumped images on original hardware.
6. Test the preferred deterministic cartridge with the physical IZEK and record prompts and failure modes.
7. Map prior-art claims to article sections and pinned GBE+ files and symbols.
8. Design and validate a protected passive link breakout before active replay or emulation.
