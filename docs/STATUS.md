# Project Status

Last updated: 2026-08-04

## Phase

End-to-end intended-hardware baseline documentation, deterministic cartridge workflow verification, ordinary sewing setup, protected passive instrumentation, and claim-level prior-art mapping.

Protocol implementation remains deferred.

## Current state

Artifact-backed repository facts:

- Shonumi's article and its 2026-03-07 archive are recorded.
- GBE+ is recorded as relevant GPLv2 prior art.
- The project has a compact canonical notebook, status record, reference record, and hardware inventory.
- No ROM, proprietary firmware, physical-bus capture, or protocol implementation is committed.

Results retained as `observed/reported`:

- OSCR was assembled; Game Boy ROM and save reads worked; at least one output was usable in an emulator.
- A replacement controller powered the Singer IZEK and produced machine motion.
- An updated EZ-Flash Jr booted the tested software set on a completely stock Game Boy Color.
- Six target images spanning Mario, Kirby, Singer, and Raku software reportedly booted; Pokemon Picross and Grimace's Birthday were also exercised as control cases.
- The EZ-Flash Jr failed on the FPGA GBC while the corresponding path worked on original hardware.
- A stock GBC running Singer/IZEK software from the EZ-Flash Jr communicated with the physical machine: selecting a simple zig-zag operation produced visible lateral needle motion.
- Running without the old upper thread caused the system to halt with a thread-related error.
- A valid threaded stitch has not been documented. Work paused pending correct threading, bobbin, tension, needle, fabric, stabilizer, and ordinary operating procedure.
- A Singer/IZEK image was reportedly written to and redumped from a FunnyPlaying EverSave cart.
- The Kirby sewing title was reportedly written to and redumped from an InsideGadgets MBC5 2 MiB / 32 KiB FRAM cart.
- The successful InsideGadgets path reportedly used OSCR `CFI Repro`, `WE=WR`, and M29F160F-compatible behavior; generic `29F Repro` was not the successful path.
- The external workbook `izek_test_matrix_canonical_saved_2026-05-03.xlsx` reportedly contains the canonical software compatibility matrix.

## Superseded boundary

The earlier statement that no flash-cart communication with the physical IZEK had been observed is superseded.

For one reported configuration, this chain functioned sufficiently to produce deterministic physical behavior:

`software image -> updated EZ-Flash Jr -> stock GBC -> link cable -> Singer IZEK -> lateral needle motion / thread-related halt`

This is stronger than a boot or menu-navigation test. It does not establish why the halt occurred, which sensor or status mechanism was involved, whether detailed stitch coordinates were transferred, or whether the EZ-Flash Jr is electrically or temporally equivalent to an original cartridge.

## Claim boundary

Not established:

- a valid threaded stitch or embroidery result;
- correct threading, bobbin setup, tension, needle choice, stabilizer, or fabric handling;
- electrical equivalence of the replacement foot controller;
- communication using an original or reproduction sewing-machine cartridge;
- generalized EZ-Flash Jr compatibility beyond the tested configuration;
- connector pinout, voltage levels, idle states, signaling direction, or clock ownership;
- packet format, commands, timing, status values, integrity fields, or stitch encoding;
- the exact source or meaning of the thread-related halt;
- model equivalence among Singer IZEK 1500, Jaguar JN-100, and Jaguar JN-2000;
- exact identity or release status of every local software image;
- independent reproduction of Shonumi's protocol findings;
- cause of the Kingston 32 GB SD-card failure.

## Blocking evidence gaps

1. No complete contemporaneous experiment record for the stock-GBC/EZ-Flash Jr/IZEK interaction.
2. No exact software hash, EZ-Flash Jr firmware identity, microSD identity, console revision, cable identity, machine settings, error text, repetition count, or dated media tied to that interaction.
3. No documented ordinary threaded straight-stitch baseline.
4. No committed OSCR logs, hashes, version records, or cartridge photographs.
5. No imported or hashed safe derivative of the canonical compatibility workbook.
6. No exact source/redump hash pair for either successful rewritable-cartridge path.
7. No original-hardware boot matrix tied to exact hashed images.
8. No claim-level map of Shonumi's article and pinned GBE+ files and symbols.
9. No protected passive breakout, voltage survey, or project-generated raw capture.

## Immediate actions and queued experiments

1. **Preserve the successful interaction:** reconstruct the stock-GBC/EZ-Flash Jr/IZEK test in the notebook with exact identities, hashes, firmware, setup, prompts, motion, halt behavior, alternatives, and limitations.
2. **Ordinary straight stitch:** learn and document correct upper threading, bobbin, needle, presser foot, tension, fabric, stabilizer, and settings. Photograph both fabric sides and capture short video.
3. **Controlled zig-zag repeat:** after correct setup, repeat the same selection at least three times and separate UI selection, machine motion, actual stitch formation, and status/error response. Include a negative or control condition.
4. **OSCR repeat-read consistency:** perform two independent ROM and save reads with complete logs, byte lengths, header report, and SHA-256 hashes.
5. **InsideGadgets write/redump reproduction:** repeat the `CFI Repro` / `WE=WR` path and compare source and redump byte-for-byte.
6. **Original-hardware boot matrix:** test exact hashed images on identified original Game Boy platforms. Record bootability separately from link availability and machine communication.
7. **Compatibility matrix preservation:** create a redistribution-safe derivative and record the source-workbook hash.
8. **Reproduction-cartridge intake:** on arrival, record supplier, board, mapper, flash and RAM parts, programmed image, write procedure, redump, and hashes before physical-machine use.
9. **Passive fixture continuity and isolation:** validate every conductor, resistance, ground, shorts, and default active-path isolation while unpowered.
10. **Idle-state voltage survey:** measure every conductor with high-impedance instrumentation before connecting any 3.3 V-only active device.
11. **First passive transaction capture:** preserve the native analyzer file unchanged and store exports, decoding, annotations, and packet hypotheses only as derivatives.
12. **Prior-art map:** pin every relied-upon statement to an article section or GBE+ commit, file, symbol, and license record.

## Artifact and capture rules

For each artifact, preserve the original filename and trustworthy timestamp, device/software/firmware/operator context, SHA-256, byte length, source, redistribution status, experiment ID, claim IDs, and whether it is raw or derived. Do not alter raw evidence in place.

Do not commit commercial ROMs, proprietary firmware, credentials, personal data, or copyrighted material without permission. Record lawful metadata, hashes, header reports, limited screenshots where permitted, and reproducible procedures instead.

The first analyzer or scope session file is immutable evidence. Record instrument and software versions, sample rate, thresholds, coupling, probes, channel mapping, fixture revision, console, cartridge, image hash, machine state, power state, exact action, and timestamps. Derived decodes must identify the raw hash, tool/version, procedure, bit order, polarity, edge, clock assumptions, framing assumptions, and unresolved ambiguity.

A repeatable waveform is not yet a packet. A byte sequence is not yet a command. Correlation with an action is not proof of semantics without controlled variation and negative tests.

## Protocol implementation gate

No active drive, replay, endpoint emulator, or firmware implementation until all of the following exist:

- documented ordinary machine operation and at least one valid threaded stitch;
- exact hardware and software identities for the successful native interaction;
- verified write, redump, hash comparison, and original-hardware execution;
- a protected passive fixture validated for continuity, isolation, and voltage compatibility;
- at least one immutable project-generated raw capture with complete setup metadata;
- a narrowly stated measured question;
- a hazard and failback plan;
- provenance for every prior-art behavior relied upon.
