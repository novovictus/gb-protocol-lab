# Research Notebook

This is the canonical record for project history, methodology, evidence, decisions, and reconstructed experiments. Detailed raw artifacts belong under `artifacts/` or `captures/`; this file records what they support.

## Evidence classes

- `observed`: directly measured with repository-backed artifacts
- `observed/reported`: direct bench result retained from project history but not yet artifact-backed
- `reproduced`: prior behavior independently repeated
- `inferred`: conclusion drawn from evidence but not directly observed
- `prior-art`: external published work
- `code-derived`: determined from an existing implementation
- `unverified`: plausible but unsupported
- `superseded`: retained historically but replaced by stronger evidence

Historical reconstruction must not silently convert memory into measurement. Promote a claim only when the supporting logs, photographs, hashes, captures, or reproducible procedure are attached.

## Research rules

1. Record hardware identity, software and firmware versions, setup, procedure, raw observations, interpretation, and limitations.
2. Preserve original artifacts unchanged; derive processed outputs separately.
3. Hash non-redistributable inputs and commit only lawful metadata and derivatives.
4. Separate prior art, code-derived behavior, inference, and independent observation.
5. Record negative results and expected compatibility failures.
6. Do not implement or replay a protocol until a measured question and safe test setup exist.

## Chronology

### 2026-03-07: prior-art preservation

Shonumi's Singer IZEK / Jaguar JN reverse-engineering article was archived at:

`https://web.archive.org/web/20260307065209/https://shonumi.github.io/articles/art22.html`

Classification: `prior-art preservation`.

### Historical work, exact dates not recovered

#### OSCR acquisition and dump validation

Reported sequence:

1. Assemble OSCR.
2. Read Game Boy ROM data.
3. Read Game Boy save data.
4. Load produced output in an emulator.
5. Confirm usable behavior.

Reported results:

- ROM dumping worked.
- Save dumping worked.
- At least one output was usable in an emulator.

Classification: `observed/reported`.

Missing evidence: OSCR revision and firmware, host software and version, source cartridge identity, filenames, byte lengths, repeated-read equality, hashes, emulator/version, screenshots, and command transcript.

#### Singer IZEK powered bring-up

A replacement Singer-compatible foot controller purchased from Amazon powered the Singer IZEK 1500 and produced basic machine motion.

Classification: `observed/reported`.

This does not establish correct threading, bobbin setup, tension, fabric feed, lockstitch formation, sustained operation, electrical equivalence to the original controller, or Game Boy communication.

Decision sequence:

1. prove ordinary sewing-machine operation;
2. prove operation with intended Game Boy hardware or a justified facsimile;
3. observe and capture communication;
4. decode or implement only after evidence exists.

#### Rewritable-cartridge write and redump

Two paths were reported:

- a Singer/IZEK software image was written to and redumped from a FunnyPlaying EverSave GB/GBC Flash Cart Pro;
- `Jaguar Mishin Sashi Senyou Soft - Kirby Family (Japan) (Proto)` was written to and redumped from an InsideGadgets MBC5 2 MiB / 32 KiB FRAM cartridge.

For the InsideGadgets cartridge, the successful OSCR configuration was reported as:

- cartridge profile: `CFI Repro`;
- write-enable selection: `WE=WR`;
- flash behavior consistent with M29F160F;
- generic `29F Repro` was not the successful path.

Diagnostic interpretation retained from the work:

- `HEADER CHECKSUM ERROR` was compatible with a blank or uninitialized cartridge and was not itself the blocking fault;
- `Flash ID: 0101 / Unknown flashrom` was the operative blocker before selecting the CFI path.

Classification: write/redump results are `observed/reported`; diagnostic interpretation is `inferred` from reported tool behavior.

Missing evidence: exact source and redump hashes, byte-for-byte comparison, complete console output, OSCR revisions, photographs, and original-hardware boot record.

#### Cartridge compatibility and software classification

- Original Game Boy hardware was selected as the behavioral baseline.
- EZ-Flash Jr reportedly worked on original hardware after a firmware update and failed on an FPGA GBC.
- Deterministic single-image rewritable cartridges were preferred over SD menu loaders for machine tests.
- `Raku x Raku - Mishin` was classified as the base sewing-machine control path.
- Kirby, Mario, Cut Shuu, and Moji titles were classified as embroidery/design-unit paths.
- Game Boy Pocket failures for CGB-only software were retained as expected negative controls.
- The external workbook `izek_test_matrix_canonical_saved_2026-05-03.xlsx` reportedly contains the canonical compatibility matrix and translation key.

Classification: mixture of `decision` and `observed/reported` until the workbook or a hashed safe derivative is imported.

#### DS flash-cart side work

DS/R4, Ace3DS+, EZ-Flash Parallel, and DSPico work is a separate deployment and implementation thread. It may inform general cartridge-development practice but is not evidence for native GB/GBC cartridge timing, link-port signaling, or IZEK compatibility.

### 2026-08-04: repository normalization

- Created and normalized `gb-protocol-lab` as an evidence-driven engineering notebook.
- Recorded Shonumi and GBE+ as prior art.
- Established claim classes and artifact requirements.
- Reconciled retained bench history without presenting it as artifact-backed measurement.
- Deferred protocol code pending physical-machine validation, intended-hardware testing, and project-generated captures.

Classification: `repository-state`.

## Decisions

### Deterministic flash-cart strategy

Use original Game Boy hardware and deterministic single-image native GB/GBC cartridges as the primary software path. The InsideGadgets MBC5 2 MiB / 32 KiB FRAM cartridge is the preferred development target; FunnyPlaying EverSave is a secondary rewritable target; EZ-Flash Jr remains a convenience loader rather than the ground-truth cartridge path.

Rationale: reduce ambiguity from menu firmware, SD access, compatibility layers, and battery-backed SRAM while enabling write/redump verification.

### Notebook before code

Do not begin protocol implementation merely because prior art exists. First establish provenance, physical-machine behavior, intended-hardware software execution, passive measurement, and claim-level evidence. Code should answer a measured question rather than create an implementation in search of evidence.

## Evidence and claim register

| ID | Claim or evidence | Class | Status |
|---|---|---|---|
| EVD-20260307-001 | Shonumi article archive | prior-art | recorded |
| EVD-20260804-001 | GBE+ sewing-machine support | prior-art/code-derived | source paths and commit not yet pinned |
| EVD-20260804-002 | Evidence-oriented repository baseline | observed | current |
| EVD-20260804-003 | OSCR assembled | observed/reported | awaiting artifacts |
| EVD-20260804-004 | Game Boy ROM dumping works | observed/reported | awaiting logs and hashes |
| EVD-20260804-005 | Game Boy save dumping works | observed/reported | awaiting logs and hashes |
| EVD-20260804-006 | Dumped output validated in emulator | observed/reported | awaiting emulator record |
| EVD-20260804-007 | Replacement controller operates IZEK | observed/reported | basic motion only |
| EVD-20260804-008 | Canonical compatibility workbook exists | observed/reported | not imported |
| EVD-20260804-009 | FunnyPlaying write/redump path | observed/reported | awaiting artifacts |
| EVD-20260804-010 | InsideGadgets CFI write/redump path | observed/reported | awaiting artifacts |

Current claims:

- A working OSCR-based ROM/save workflow is reported but not artifact-backed.
- The IZEK can be powered and mechanically actuated, but a valid threaded stitch is not established.
- Rewritable cartridge write/redump paths are reported, but flash-cart communication with the physical IZEK is not established.
- No project-generated IZEK capture, voltage measurement, decoded packet, replay trace, endpoint emulator, or independently verified protocol implementation exists.
- Shonumi's protocol findings have not been independently reproduced by this project.

## Experiment record template

For future work, append a dated section containing:

- objective and experiment ID;
- hardware IDs and configuration;
- software/firmware versions;
- safety constraints;
- procedure;
- raw observations;
- artifact paths and SHA-256 hashes;
- interpretation and alternatives;
- explicit claim boundary;
- next action.
