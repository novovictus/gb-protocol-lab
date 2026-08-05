# Project Status

Last updated: 2026-08-04

## Phase

Engineering-notebook consolidation before code. Current work is end-to-end intended-hardware baseline documentation, deterministic cartridge workflow verification, mechanical restoration, compatibility-matrix reconstruction, source attribution, and passive-measurement planning.

Protocol implementation remains deferred.

## Current state

Repository facts from the current default branch:

- Canonical documentation exists under `README.md`, `docs/NOTEBOOK.md`, `docs/STATUS.md`, `docs/REFERENCES.md`, and `hardware/INVENTORY.md`.
- `artifacts/izek_test_matrix.xlsx` is committed with SHA-256 `fdb941a3a6936b61b20042d2fc8c103e78ca737df4389bdbfad5c45dccebd9e0`.
- A dated photo-backed evidence index is committed under `artifacts/2026-05-03-compatibility-evidence/`.
- The committed contact-sheet derivative has SHA-256 `631f990bdf22d4e80851b35b48505fd7c77c2358dbf695ec26bb4fced5e023ea`.
- The evidence manifest records SHA-256 hashes for all sixteen original source photos and identifies an alternate workbook revision with SHA-256 `a1bb3aa68c7cec801a31c387377345be2a513a7677a2c83d6f8c18c97cc86d9d`.
- The alternate workbook differs from the previously committed root workbook. Both identities are preserved; neither silently supersedes the other.
- No commercial ROM, proprietary firmware, physical-bus capture, or protocol implementation is committed.

Artifact-backed compatibility observations:

- Original GBA and original GBC visibly reached software prompt, machine-check, or embroidery-unit requirement screens for the tested titles.
- Game Boy Pocket visibly displayed the Game Boy Color-only rejection screen for the tested CGB-only titles.
- Original GBC and FP-GBC visibly reached different STOP/error states in the retained comparison images.
- These images establish screen states only. They do not establish completed upload, machine motion, stitch formation, electrical equivalence, timing equivalence, or the exact meaning of every screen.

Results retained as `observed/reported` unless later backed by committed evidence:

- OSCR was assembled; Game Boy ROM and save reads worked; at least one output was usable in an emulator.
- A replacement controller powered the Singer IZEK and produced machine motion.
- The feed-dog lift failure was traced to a broken notch on the mechanical slider that engages the cam. Manually positioning the slider restored engagement of the downstream mechanism.
- The installed needle used during initial bring-up was physically broken and unsuitable for a valid sewing test.
- During the unresolved bring-up state, pressing sew reportedly caused the machine to accelerate, stop, and blink red at the switch or indicator.
- The Game Boy software displayed an error graphic pointing toward the upper area of the machine during the same general troubleshooting period.
- These mechanical and UI observations do not establish a direct thread-presence sensor, tension sensor, motor-overload code, position-sensor fault, or any specific protocol status.
- Correct bobbins, 100% polyester all-purpose thread, a needle pack, and Singer oil were later obtained from a craft store. Exact package identities and the authoritative needle system still need evidence.
- An updated EZ-Flash Jr reportedly booted the tested software set on a stock Game Boy Color.
- Stock GBC plus EZ-Flash Jr plus Singer/IZEK software reportedly produced visible lateral needle motion and later halted with a thread-related error.
- A Singer/IZEK image was reportedly written to and redumped from a FunnyPlaying EverSave cart.
- `Jaguar Mishin Sashi Senyou Soft - Kirby Family (Japan) (Proto)` was reportedly written to and redumped from an InsideGadgets MBC5 2 MiB / 32 KiB FRAM cart using OSCR `CFI Repro`, `WE=WR`, and M29F160F-compatible behavior.
- EZ-Flash Jr reportedly failed to boot on FP-GBC.
- DS-family side work revived an R4 SDHC with period firmware and made GameYob/GBARunner2 operational. That path is separate from native GB/GBC IZEK protocol evidence.

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

The earlier statement that no flash-cart communication with the physical IZEK had been observed is superseded. One stock-GBC/EZ-Flash Jr/Singer path reportedly produced deterministic machine motion. That does not establish generalized flash-cart compatibility, packet semantics, detailed coordinate transfer, or a valid stitch.

## Current claim boundary

Not established:

- a valid threaded stitch or embroidery result;
- completed upload for the photo-backed 2026-05-03 compatibility runs;
- correct feed height, feed timing, stitch length, or durable feed-dog repair;
- the specific cause of the ramp-stop-red indication;
- whether the upper-machine graphic represents threading, spool routing, take-up, tension, or another machine condition;
- direct sensing of missing thread or thread tension;
- electrical equivalence among original, EZ-Flash Jr, FunnyPlaying, and InsideGadgets cartridges;
- equivalence among stock GBC, Pocket, GBA CGB mode, SGB2, FP-GBC, MiSTer, Analogue Pocket, or Chromatic;
- connector pinout, voltage levels, idle states, signaling direction, or clock ownership;
- packet format, commands, timing, status values, integrity fields, or stitch encoding;
- exact cause of the host-specific upload failures or thread-related halt;
- independent reproduction of Shonumi's protocol findings.

## Blocking evidence gaps

1. The original sixteen photos are hash-identified, but only the contact-sheet derivative is committed through the current repository connector.
2. No row-level mapping from every source photo and workbook row to exact experiment and evidence IDs.
3. No exact chronology resolving differing Pocket, GBA, GBC, and FP-GBC observations across Singer and Kirby runs.
4. No exact ROM hashes, cartridge revisions, programmed-image verification, host board revisions, firmware/core versions, cable identities, machine state, error text, timestamps, repetition counts, or artifact hashes for the retained compatibility runs.
5. No photographs or dimensions of the broken feed-dog slider notch, engaged/disengaged positions, or durable repair.
6. No photograph or authoritative identification of the broken needle or validated replacement needle system/orientation.
7. No synchronized record of machine motion, red-indicator cadence, Game Boy screen, mechanical state, threading state, and exact sequence for the fault run.
8. No documented ordinary threaded straight-stitch baseline.
9. No complete OSCR logs and source/redump hash pairs.
10. No protected passive breakout, voltage survey, or project-generated raw capture.
11. No pinned GBE+ commit, files, symbols, and license extraction for each code-derived claim.

## Immediate actions

1. Map each original photo hash and workbook row to a separate experiment/evidence record.
2. Preserve both workbook revisions and document their chronology and content differences.
3. Retest one exact image/cart/host combination at a time, recording machine power state, attachments, thread state, selected operation, exact screen text, and repetition count.
4. Keep boot, UI, link initialization, upload start, upload completion, physical motion, and stitch formation as separate fields.
5. Photograph the broken slider/notch, measure it, record engaged and disengaged positions, and document a reversible retention or durable repair.
6. Identify the correct needle system from an authoritative source, install a known-good needle in the correct orientation, and verify unobstructed handwheel rotation before powered operation.
7. Document ordinary sewing setup: bobbin type, upper thread route, bobbin winding, presser-foot state, feed-dog state, fabric, stabilizer, and tension settings.
8. Produce and document one ordinary valid stitch before interpreting protocol-driven motion as sewing success.
9. Reproduce OSCR reads and both write/redump paths with complete logs and SHA-256 comparisons.
10. Validate a protected passive fixture and voltage compatibility before active hardware is connected.
11. Pin GBE+ commit and source locations before using implementation details.

## Protocol implementation gate

No active drive, replay, endpoint emulator, or firmware implementation until all of the following are documented:

- ordinary machine operation and at least one valid stitch;
- exact software, cartridge, host, cable, machine, and firmware identities;
- deterministic write/redump verification with hashes;
- protected passive measurement fixture;
- idle-state voltage survey;
- immutable raw capture;
- a narrowly stated measured question;
- hazard/failback plan;
- prior-art provenance and license boundaries.
