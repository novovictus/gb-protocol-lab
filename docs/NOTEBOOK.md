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
7. A polished title screen does not prove retail release, successful boot does not prove a clean dump, and emulator behavior does not establish physical-bus behavior.

## Chronology

### 2026-03-07: prior-art preservation

Shonumi's Singer IZEK / Jaguar JN reverse-engineering article was archived at:

`https://web.archive.org/web/20260307065209/https://shonumi.github.io/articles/art22.html`

Classification: `prior-art preservation`.

### 2026-04-18: prior work recognized

The project owner recognized Shonumi's article and GBE+ as substantial existing work rather than a new project discovery. Future work was required to attribute prior art, distinguish reproduction from discovery, and preserve stable references.

Classification: `decision` and `prior-art preservation`.

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

Minimum future validation: two matching reads, cryptographic hashes, valid header/checksum where applicable, preservation-database comparison when available, emulator smoke test, and cautious save read/write testing only after cartridge and voltage handling are understood.

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

##### Sewing-machine software inventory

| Software | Role | Project evidence | Release-status boundary |
|---|---|---|---|
| Sewing Machine Operation Software (USA) (En,Fr,Es) (GB Compatible) | Western Singer IZEK control software | Local image and boot screenshot reported | Exact local dump identity unverified |
| Raku x Raku Mishin | JN-100 base sewing/control software | Boot and menu screenshots reported | Commercial-title classification retained from prior work |
| Raku x Raku Moji | JN-2000 lettering software | Boot and menu screenshots reported | Commercial-title classification retained from prior work |
| Raku x Raku Cut Shuu | JN-2000 design software | Boot and menu screenshots reported | Commercial-title classification retained from prior work |
| Mario Family | JN-2000 licensed embroidery designs | Boot and selection screenshots reported | Commercial-title classification retained from prior work |
| Kirby Family | JN-2000 embroidery software | Local ROM/save and boot screenshots reported | `(Proto)` is catalog metadata; polished presentation does not establish retail release |

A European Western variant is mentioned in prior art, but the project has not established whether it is a distinct ROM, packaging variant, revision, or catalog entry. Additional variants or prototypes require primary-source, physical-artifact, preservation-database, or reproducible hash evidence.

##### Singer operation software header retained from project history

Filename:

`Sewing Machine Operation Software (USA) (En,Fr,Es) (GB Compatible).gbc`

Recorded header interpretation:

| Field | Recorded value | Meaning |
|---|---:|---|
| CGB flag (`0x0143`) | `0x80` | CGB-enhanced / backward compatible |
| cartridge type (`0x0147`) | `0x1B` | MBC5 + RAM + battery |
| ROM size (`0x0148`) | `0x05` | 1 MiB |
| RAM size (`0x0149`) | `0x02` | 8 KiB |
| destination (`0x014A`) | `0x01` | non-Japanese |

Status: `reported`; no generated header report or image hash is committed.

##### Non-IZEK cartridge controls

`Pokemon Picross` beta and `Grimace's Birthday` were identified as controlled non-IZEK targets for validating ordinary flash, boot, save, redump, and hash workflows. Retained history reports that both declare cartridge type `0x1B` and 32 KiB external RAM.

Compatibility with the InsideGadgets MBC5 2 MiB / 32 KiB FRAM cartridge is an inference from reported header and capacity data, not a completed hardware result. Success with either image would validate only the cartridge workflow and would provide no evidence about IZEK electrical or protocol compatibility.

The cartridge is a single-image rewritable target; changing software requires reflashing rather than selecting from a multi-ROM menu.

##### SRAM and FRAM terminology

Original MBC5 + RAM + battery cartridges generally use volatile SRAM maintained by a coin cell. Modern FRAM replacement cartridges provide non-volatile save storage without a battery. FRAM is a development convenience and reliability improvement; it is not evidence that an original cartridge used FRAM.

#### 2026-08-04 handheld and flash-cart side work

Reported results:

- an old R4 SDHC was revived using period firmware sources;
- GameYob and GBARunner2 were made operational on Nintendo DS hardware;
- a Kingston 32 GB SD card failed during the process, with cause unknown;
- ROM files were recovered from an Allwinner-based R36S clone;
- attempts to install an alternate operating system on the R36S clone were unsuccessful;
- a dog-damaged GBA SP was identified as a possible link-port donor and separate repair or consolization project.

These results expand the available test environment but do not establish sewing-machine protocol behavior. The failed SD card must not be attributed to firmware, incompatibility, write amplification, or electrical damage without diagnostics.

### 2026-08-04: repository normalization

- Created and normalized `gb-protocol-lab` as an evidence-driven engineering notebook.
- Recorded Shonumi and GBE+ as prior art.
- Established claim classes and artifact requirements.
- Reconciled retained bench history without presenting it as artifact-backed measurement.
- Deferred protocol code pending physical-machine validation, intended-hardware testing, and project-generated captures.

Classification: `repository-state`.

## Prior-art protocol summary

The following are attributed to Shonumi's article and GBE+ work and are not project discoveries:

- sewing-machine communication alternates clock roles, with Game Boy and machine switching internal and external serial-clock modes;
- machine-clocked Game Boy transfers may not always produce a serial interrupt;
- stitching transfers use packets reported up to 128 bytes;
- `0xB9` and `0xBB` are reported packet-boundary markers;
- JN-100/IZEK stitch data contains a header, coordinate-like body, and checksum-like ending;
- base-format X is treated as an absolute needle position while a Y-like value describes fabric movement around neutral value `0x14`, with the prior Y value affecting the following X movement;
- JN-2000 software checks a one-byte machine status, with `0x06` and `0x07` interpreted in GBE+ as small and large hoops;
- JN-2000 embroidery coordinates use a different signed-direction encoding involving bit 6;
- embroidery jump or relocation structures are reported between `0xBE` and `0xBD`, with 16-bit little-endian shifts and `0xFF` separators;
- designs may transfer as separate color or section passes with absolute starting positions.

These statements require claim-level citation to article sections or pinned GBE+ files and symbols before detailed reliance. Local reproduction should record exact ROM hashes, emulator builds, `SB`/`SC` activity, interrupts, clock selection, timing, raw physical captures, and deviations from prior art.

Open questions include exact clock-phase ownership on local hardware, transport differences between Western and Japanese base software, the European variant, Kirby protocol maturity, integrity fields, status bits, and whether a microcontroller can safely emulate a minimal deterministic endpoint.

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
| EVD-20260804-011 | Sewing software boot/screenshots | observed/reported | hashes and exact emulator records missing |
| EVD-20260804-012 | R4, GameYob, and GBARunner2 side-work | observed/reported | separate from IZEK evidence |
| EVD-20260804-013 | R36S ROM recovery | observed/reported | side investigation |
| EVD-20260804-014 | Kingston SD-card failure | observed/reported | cause unknown |

Current claims:

- A working OSCR-based ROM/save workflow is reported but not artifact-backed.
- The IZEK can be powered and mechanically actuated, but a valid threaded stitch is not established.
- Rewritable cartridge write/redump paths are reported, but flash-cart communication with the physical IZEK is not established.
- Multiple sewing-machine images reportedly booted in emulators, but exact hashes, revisions, and release identities remain unverified.
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
