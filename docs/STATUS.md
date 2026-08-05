# Project Status

Last updated: 2026-08-04

## Phase

End-to-end intended-hardware baseline documentation, deterministic cartridge workflow verification, compatibility-matrix reconstruction, ordinary sewing setup, protected passive instrumentation, and claim-level prior-art mapping.

Protocol implementation remains deferred.

## Current state

Artifact-backed repository facts:

- Shonumi's article and its 2026-03-07 archive are recorded.
- GBE+ is recorded as relevant GPLv2 prior art.
- The compact canonical notebook, status, references, and hardware inventory remain the documentation surface.
- `artifacts/izek_test_matrix.xlsx` is now committed with SHA-256 `fdb941a3a6936b61b20042d2fc8c103e78ca737df4389bdbfad5c45dccebd9e0`.
- No commercial ROM, proprietary firmware, physical-bus capture, or protocol implementation is committed.

Results retained as `observed/reported`:

- OSCR was assembled; Game Boy ROM and save reads worked; at least one output was usable in an emulator.
- A replacement controller powered the Singer IZEK and produced machine motion.
- An updated EZ-Flash Jr booted the tested software set on a stock Game Boy Color.
- Stock GBC plus EZ-Flash Jr plus Singer/IZEK software produced visible lateral needle motion and later halted with a thread-related error.
- A Singer/IZEK image was written to and redumped from a FunnyPlaying EverSave cart.
- The same FunnyPlaying image reportedly booted on original GBC, Game Boy Pocket, and FP-GBC; machine upload reportedly succeeded from GBC and Pocket but failed from FP-GBC.
- Kirby Family was written to and redumped from an InsideGadgets MBC5 2 MiB / 32 KiB FRAM cart using OSCR `CFI Repro`, `WE=WR`, and M29F160F-compatible behavior.
- Kirby reportedly booted on original GBA but produced an immediate upload error. A later Pocket run also produced an immediate error. Original GBC and FP-GBC reportedly reached upload and displayed different errors.
- EZ-Flash Jr failed to boot on FP-GBC.

## Layered result model

Every compatibility run must record these separately:

1. cartridge write completed;
2. redump matched source;
3. host recognized cartridge;
4. software booted;
5. operational UI reached;
6. machine link initialized;
7. upload started;
8. upload completed;
9. machine moved;
10. valid stitch formed.

A pass at one layer does not imply a pass at the next. `Booted` is not shorthand for machine compatibility.

## Superseded boundary

The earlier statement that no flash-cart communication with the physical IZEK had been observed is superseded. One stock-GBC/EZ-Flash Jr/Singer path produced deterministic machine motion. That does not establish generalized flash-cart compatibility, packet semantics, detailed coordinate transfer, or a valid stitch.

## Claim boundary

Not established:

- a valid threaded stitch or embroidery result;
- electrical equivalence among original, EZ-Flash Jr, FunnyPlaying, and InsideGadgets cartridges;
- equivalence among stock GBC, Pocket, GBA CGB mode, SGB2, FP-GBC, MiSTer, Analogue Pocket, or Chromatic;
- connector pinout, voltage levels, idle states, signaling direction, or clock ownership;
- packet format, commands, timing, status values, integrity fields, or stitch encoding;
- exact cause of the host-specific upload failures or thread-related halt;
- independent reproduction of Shonumi's protocol findings.

## Blocking evidence gaps

1. No row-level mapping from workbook entries to exact experiment and evidence IDs.
2. No exact chronology resolving differing Pocket and FP-GBC observations across Singer and Kirby runs.
3. No exact ROM hashes, cartridge revisions, programmed-image verification, host board revisions, firmware/core versions, cable identities, machine state, error text, timestamps, repetition counts, or artifact hashes for the retained compatibility runs.
4. No documented ordinary threaded straight-stitch baseline.
5. No complete OSCR logs and source/redump hash pairs.
6. No protected passive breakout, voltage survey, or project-generated raw capture.

## Immediate actions

1. Reconstruct each 2026-04-24 and 2026-05-03 run as a separate experiment record.
2. Preserve the workbook unchanged and create a redistribution-safe CSV or Markdown derivative linked to row-level evidence IDs.
3. Retest one exact image/cart/host combination at a time, recording machine power state, attachments, thread state, selected operation, exact screen text, and repetition count.
4. Keep boot, UI, link initialization, upload start, upload completion, physical motion, and stitch formation as separate fields.
5. Reproduce OSCR reads and both write/redump paths with complete logs and SHA-256 comparisons.
6. Document an ordinary threaded stitch before interpreting protocol-driven motion as sewing success.
7. Validate a protected passive fixture and voltage compatibility before active hardware is connected.

## Protocol implementation gate

No active drive, replay, endpoint emulator, or firmware implementation until ordinary machine operation, exact identities, deterministic write/redump verification, protected passive measurement, immutable raw capture, a narrowly stated measured question, a hazard/failback plan, and prior-art provenance are all documented.
