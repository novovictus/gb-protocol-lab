# Project Status

Last updated: 2026-08-04

## Phase

Physical baseline validation, deterministic cartridge workflow verification, intended-hardware compatibility testing, protected passive instrumentation, and claim-level prior-art mapping.

Protocol implementation remains deferred.

## Current state

Artifact-backed repository facts:

- Shonumi's article and its 2026-03-07 archive are recorded.
- GBE+ is recorded as relevant GPLv2 prior art.
- The project has a compact canonical notebook, status record, reference record, and hardware inventory.
- No ROM, proprietary firmware, physical-bus capture, or protocol implementation is committed.

Results retained as `observed/reported`:

- OSCR was assembled; Game Boy ROM and save reads worked; at least one output was usable in an emulator.
- A replacement controller powered the Singer IZEK and produced basic machine motion.
- A Singer/IZEK image was reportedly written to and redumped from a FunnyPlaying EverSave cart.
- The Kirby sewing title was reportedly written to and redumped from an InsideGadgets MBC5 2 MiB / 32 KiB FRAM cart.
- The successful InsideGadgets path reportedly used OSCR `CFI Repro`, `WE=WR`, and M29F160F-compatible behavior; generic `29F Repro` was not the successful path.
- Original Game Boy hardware is the preferred behavioral baseline; EZ-Flash Jr reportedly differed between original and FPGA hardware.
- The external workbook `izek_test_matrix_canonical_saved_2026-05-03.xlsx` reportedly contains the canonical software compatibility matrix.
- Period R4 firmware, GameYob, and GBARunner2 were revived as a separate DS convenience path.
- A damaged GBA SP was identified as a possible donor for a link connector, while repair and consolization remain separate future work.

## Claim boundary

Not established:

- a valid threaded stitch;
- electrical equivalence of the replacement foot controller;
- flash-cart communication with the physical IZEK;
- connector pinout, voltage levels, idle states, signaling direction, or clock ownership;
- packet format, commands, timing, status values, integrity fields, or stitch encoding;
- model equivalence among Singer IZEK 1500, Jaguar JN-100, and Jaguar JN-2000;
- exact identity or release status of every local software image;
- independent reproduction of Shonumi's protocol findings;
- cause of the Kingston 32 GB SD-card failure.

## Blocking evidence gaps

1. No documented straight-stitch test.
2. No committed OSCR logs, hashes, version records, or cartridge photographs.
3. No imported or hashed safe derivative of the canonical compatibility workbook.
4. No exact source/redump hash pair for either successful rewritable-cartridge path.
5. No original-hardware boot record tied to the exact redumped images.
6. No documented flash-cart test with the physical IZEK.
7. No claim-level map of Shonumi's article and pinned GBE+ files and symbols.
8. No protected passive breakout, voltage survey, or project-generated raw capture.

## Immediate actions and queued experiments

1. **Ordinary straight stitch:** document machine, controller, threading, bobbin, needle, fabric, settings, failures, both fabric sides, and short video.
2. **OSCR repeat-read consistency:** perform two independent ROM and save reads with exact hardware/software identities, complete logs, byte lengths, header report, and SHA-256 hashes.
3. **InsideGadgets write/redump reproduction:** repeat the `CFI Repro` / `WE=WR` path and compare source and redump byte-for-byte. Record generic `29F Repro` only under the same controlled state.
4. **Original-hardware boot matrix:** test exact hashed images on identified original Game Boy platforms. Record bootability separately from link availability and sewing-machine communication.
5. **Compatibility matrix preservation:** create a redistribution-safe derivative and record the source-workbook hash.
6. **Physical IZEK cartridge test:** use the preferred deterministic cartridge without instrumentation first and record prompts, failures, and machine behavior.
7. **Passive fixture continuity and isolation:** validate every conductor, direct-path resistance, ground, shorts, and default active-path isolation while unpowered.
8. **Idle-state voltage survey:** measure every conductor with high-impedance instrumentation before connecting any 3.3 V-only active device.
9. **First passive transaction capture:** preserve the native analyzer file unchanged and store exports, decoding, annotations, and packet hypotheses only as derivatives.
10. **Prior-art map:** pin every relied-upon statement to an article section or GBE+ commit, file, symbol, and license record.

## Artifact and capture rules

For each artifact, preserve the original filename and trustworthy timestamp, device/software/firmware/operator context, SHA-256, byte length, source, redistribution status, experiment ID, claim IDs, and whether it is raw or derived. Do not alter raw evidence in place.

Do not commit commercial ROMs, proprietary firmware, credentials, personal data, or copyrighted material without permission. Record lawful metadata, hashes, header reports, limited screenshots where permitted, and reproducible procedures instead.

The first analyzer or scope session file is immutable evidence. Record instrument and software versions, sample rate, thresholds, coupling, probes, channel mapping, fixture revision, console, cartridge, image hash, machine state, power state, exact action, and timestamps. Derived decodes must identify the raw hash, tool/version, procedure, bit order, polarity, edge, clock assumptions, framing assumptions, and unresolved ambiguity.

A repeatable waveform is not yet a packet. A byte sequence is not yet a command. Correlation with an action is not proof of semantics without controlled variation and negative tests.

## Protocol implementation gate

No active drive, replay, endpoint emulator, or firmware implementation until all of the following exist:

- documented ordinary machine operation;
- exact hardware and software identities;
- verified write, redump, hash comparison, and original-hardware execution;
- a protected passive fixture validated for continuity, isolation, and voltage compatibility;
- at least one immutable project-generated raw capture with complete setup metadata;
- a narrowly stated measured question;
- a hazard and failback plan;
- provenance for every prior-art behavior relied upon.
