# Research Notebook

Canonical record for project history, evidence, decisions, and reconstructed experiments. Raw captures and protocol traces belong under `captures/`; this file records what the retained evidence supports.

## Evidence discipline

- `observed`: directly supported by committed project evidence
- `observed/reported`: direct operator observation without complete committed evidence
- `reproduced`: external behavior independently repeated with project evidence
- `inferred`: interpretation drawn from observations
- `prior-art`: external published claim
- `code-derived`: behavior identified from an implementation
- `unverified`: plausible but unsupported
- `superseded`: retained historically but replaced by stronger evidence

Do not convert memory into measurement. Record exact hardware, software, firmware, setup, procedure, raw observations, limitations, hashes, and evidence paths. Preserve source evidence unchanged and create derivatives separately. Successful boot does not prove a clean dump; emulator behavior does not prove physical-bus behavior; a repeatable waveform is not yet a packet; a byte sequence is not yet a command.

## Chronology

### 2026-03-07: prior-art preservation

Shonumi's Singer IZEK / Jaguar JN article was archived at:

`https://web.archive.org/web/20260307065209/https://shonumi.github.io/articles/art22.html`

Classification: `prior-art preservation`.

### 2026-04-18: prior work recognized

Shonumi's article and GBE+ were recognized as substantial prior work. Future implementation must attribute prior art and distinguish reproduction from discovery.

Classification: `decision` and `prior-art preservation`.

### 2026-05-03: ordinary sewing setup supplies

Reported result: Amazon sewing-supply purchases were returned and correct supplies were acquired locally from a craft store. The set included correct bobbins, 100% polyester all-purpose thread, a needle multipack, and Singer oil.

Classification: `observed/reported`.

Boundary: exact bobbin class, needle system, package identity, and manual-backed compatibility are not yet artifact-backed. The bobbin-winder behavior was interpreted as spring-loaded retention rather than free-spinning full-depth seating, but authoritative manual confirmation is still needed.

### Historical work, exact dates not recovered

#### OSCR acquisition and dump validation

Reported sequence: assemble OSCR, read ROM, read save, load output in an emulator, and confirm usable behavior.

Reported results:

- ROM dumping worked.
- Save dumping worked.
- At least one output was usable in an emulator.

Classification: `observed/reported`.

Missing evidence: OSCR revision and firmware, host software, source cartridge, filenames, lengths, repeated-read equality, hashes, emulator identity, screenshots, and command transcript.

#### Singer IZEK powered bring-up

A replacement Singer-compatible foot controller purchased from Amazon powered the Singer IZEK 1500 and produced basic machine motion.

Classification: `observed/reported`.

This did not establish correct threading, bobbin setup, tension, fabric feed, lockstitch formation, sustained operation, controller equivalence, or Game Boy communication.

#### Rewritable-cartridge workflows

Reported results:

- a Singer/IZEK image was written to and redumped from a FunnyPlaying EverSave GB/GBC Flash Cart Pro;
- `Jaguar Mishin Sashi Senyou Soft - Kirby Family (Japan) (Proto)` was written to and redumped from an InsideGadgets MBC5 2 MiB / 32 KiB FRAM cartridge;
- the successful InsideGadgets path used OSCR `CFI Repro`, `WE=WR`, and M29F160F-compatible behavior;
- generic `29F Repro` was not the successful path;
- `HEADER CHECKSUM ERROR` was treated as compatible with a blank or uninitialized image, while `Flash ID: 0101 / Unknown flashrom` was the operative blocker before selecting the CFI path.

Classification: write/redump results are `observed/reported`; diagnostic interpretation is `inferred`.

Source-intake rule: every future OSCR or programmer session must record source image provenance, exact filename, byte length, SHA-256, tool and firmware versions, cartridge identity, profile selection, write-enable setting, console output, redump hash, and byte-for-byte comparison result. A cartridge filename alone is not provenance.

#### Cartridge compatibility and software inventory

- Original Game Boy hardware is the behavioral baseline.
- EZ-Flash Jr reportedly worked after firmware update on original hardware and failed on FP-GBC.
- Deterministic single-image rewritable cartridges are preferred over SD menu loaders for machine tests.
- `Raku x Raku Mishin` is retained as the base sewing-machine control path.
- Kirby, Mario, Cut Shuu, and Moji are retained as embroidery/design-unit paths.
- Game Boy Pocket failures for CGB-only software are negative controls.
- Structured compatibility results are maintained in [`docs/izek_test_matrix.xlsx`](izek_test_matrix.xlsx).
- Corresponding visual evidence is maintained in the [remote compatibility photo album](https://photos.app.goo.gl/GYaj7Pjwva9XXzap6).

Reported software inventory:

| Software | Role | Boundary |
|---|---|---|
| Sewing Machine Operation Software (USA) (En,Fr,Es) | Western Singer IZEK control | exact dump identity unverified |
| Raku x Raku Mishin | JN-100 base control | retained from prior work |
| Raku x Raku Moji | JN-2000 lettering | retained from prior work |
| Raku x Raku Cut Shuu | JN-2000 design | retained from prior work |
| Mario Family | JN-2000 licensed designs | retained from prior work |
| Kirby Family | JN-2000 embroidery | `(Proto)` is catalog metadata, not proof of release status |

Singer operation software reported header:

| Field | Value | Meaning |
|---|---:|---|
| CGB flag `0x0143` | `0x80` | CGB-enhanced / backward compatible |
| cartridge type `0x0147` | `0x1B` | MBC5 + RAM + battery |
| ROM size `0x0148` | `0x05` | 1 MiB |
| RAM size `0x0149` | `0x02` | 8 KiB |
| destination `0x014A` | `0x01` | non-Japanese |

`Pokemon Picross` beta and `Grimace's Birthday` are non-IZEK controls for flash, boot, save, redump, and hash workflow validation. Success with either does not support an IZEK protocol claim.

Original MBC5 + RAM + battery cartridges generally use battery-backed SRAM. Modern FRAM replacement cartridges are a development convenience and are not evidence that an original cartridge used FRAM.

#### 2026-08-04 handheld side work

Reported results:

- an old R4 SDHC was revived with period firmware;
- GameYob and GBARunner2 were made operational on Nintendo DS hardware;
- a Kingston 32 GB SD card failed, with cause unknown;
- ROM files were recovered from an Allwinner-based R36S clone;
- alternate R36S operating-system installation was unsuccessful;
- a dog-damaged GBA SP was identified as a possible non-destructive link-breakout source or repair project.

These results do not establish IZEK protocol behavior.

## Reconstructed experiments

### EXP-20260804-RECON-001: EZ-Flash Jr to Singer IZEK

Exact bench date not recovered. Classification: `observed/reported`.

Reported setup:

- completely stock original Game Boy Color;
- EZ-Flash Jr updated before testing;
- microSD identity not recorded;
- Singer/IZEK software image, exact filename and SHA-256 not recorded;
- Singer IZEK, machine cable, and replacement foot controller;
- old upper thread initially present, then removed;
- reproduction cartridges not yet received.

Reported observations:

- six target images plus Pokemon Picross and Grimace's Birthday reportedly booted on the stock GBC;
- EZ-Flash Jr failed or errored on FP-GBC while functioning on original hardware;
- selecting a simple zig-zag operation caused visible lateral needle motion;
- operation without upper thread halted;
- a thread-related error was reported.

Narrow interpretation:

The tested software image, updated EZ-Flash Jr, stock GBC, cable, and Singer IZEK exchanged enough information to produce selected physical needle motion and a thread-related stop condition. This supersedes the earlier statement that flash-cart communication with the physical IZEK had not been observed.

Not established:

- valid stitch formation;
- exact software hash, cart firmware, microSD, console revision, error text, or repeat count;
- protocol bytes, framing, timing, clock ownership, or command semantics;
- operation with an original or reproduction sewing-machine cartridge;
- compatibility with other consoles, carts, software, or machine models;
- whether the halt came from thread presence, tension, a generic fault, another interlock, or software-side interpretation.

### EXP-RECON-MECH-001: Feed-dog engagement failure

Exact bench date not recovered. Classification: `observed/reported`.

Reported procedure:

1. Open the bottom panel.
2. Inspect the external feed control and internal mechanism.
3. Observe the slider and cam-engagement path.
4. Move the slider manually into the engaged position.

Reported observations:

- the external switch mechanically operates a slider that engages a cam;
- the slider's engagement notch was broken;
- the break prevented the external control from engaging the mechanism;
- manually sliding the mechanism into position engaged the downstream feed-dog lift path.

Narrow result:

The immediate feed-dog failure was localized to the broken slider/notch transfer feature, while the downstream cam mechanism could still be engaged manually.

Not established: long-term stability, correct feed height or timing, stitch-length calibration, durable repair, or valid fabric feed under threaded load.

### EXP-RECON-MECH-002: Broken needle discovery

Exact bench date not recovered. Classification: `observed/reported`.

While locating the needle eye, the installed needle was found not to have a normal sharp end and was recognized as broken.

This establishes only that the installed needle was unsuitable for a valid sewing test. It does not establish that the needle caused any specific electronic error, motor stop, red indicator, link error, or earlier motion anomaly.

### EXP-RECON-MECH-003: Ramp, stop, and red indicator

Exact bench date not recovered. Classification: `observed/reported`.

Pressing the sew control reportedly caused the machine to start, ramp in speed, stop, and blink red at the switch or indicator.

Concurrent unresolved conditions included the broken feed-dog engagement slider, manual feed-dog engagement, and a broken needle. Exact sequencing and machine configuration were not preserved.

The behavior is a fault indication, but its source is not established. Do not label it as thread detection, tension sensing, motor overload, position-sensor failure, or a specific service code without authoritative mapping or measurement.

### EXP-RECON-LINK-001: Upper-machine error graphic

Exact bench date not recovered. Classification: `observed/reported`.

The Game Boy software reportedly displayed an error graphic pointing toward the top of the machine.

The graphic may refer to upper threading, spool routing, take-up, tension, or another upper-machine condition. The exact frame and authoritative manual text are not preserved. The observation does not prove a direct thread-presence or tension sensor.

Required evidence: exact screen capture, software filename and SHA-256, cartridge/loader configuration, machine indicator state, thread route, presser-foot state, and immediately preceding action.

### Reconstructed compatibility experiments

The workbook and retained history must be decomposed into separate runs rather than one blended result. At minimum preserve these as distinct experiments:

- Singer image on FunnyPlaying cart with original GBC;
- Singer image on FunnyPlaying cart with Game Boy Pocket;
- Singer image on FunnyPlaying cart with FP-GBC;
- Kirby image on InsideGadgets cart with original GBA;
- Kirby image on InsideGadgets cart with Game Boy Pocket;
- Kirby image on InsideGadgets cart with original GBC;
- Kirby image on InsideGadgets cart with FP-GBC;
- EZ-Flash Jr boot and physical-machine run on stock GBC;
- EZ-Flash Jr failure on FP-GBC.

For every run record write completion, redump equality, host recognition, boot, UI, link initialization, upload start, upload completion, machine motion, and stitch formation as separate fields. Do not merge observations from different dates, ROM revisions, cartridges, or hosts.

## Compatibility result model

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

A pass at one layer does not imply a pass at the next.

## Prior-art protocol summary

The following are attributed to Shonumi and GBE+ and are not project discoveries:

- communication alternates clock roles between Game Boy and machine;
- machine-clocked transfers may not always produce a serial interrupt;
- stitching transfers use packets reported up to 128 bytes;
- `0xB9` and `0xBB` are reported packet-boundary markers;
- JN-100/IZEK stitch data includes a header, coordinate-like body, and checksum-like ending;
- base-format X is treated as an absolute needle position while a Y-like value describes fabric movement around neutral `0x14`;
- JN-2000 status values `0x06` and `0x07` are interpreted in GBE+ as small and large hoops;
- JN-2000 coordinates use a different signed-direction encoding involving bit 6;
- embroidery relocation structures are reported between `0xBE` and `0xBD`, with little-endian shifts and `0xFF` separators;
- designs may transfer as separate color or section passes.

Each relied-upon statement still requires an article section or pinned GBE+ commit, file, symbol, and license record.

## Decisions

### Deterministic cartridge strategy

Use original Game Boy hardware and deterministic single-image native GB/GBC cartridges as the primary path. InsideGadgets MBC5 FRAM is the preferred development cartridge; FunnyPlaying EverSave is secondary; EZ-Flash Jr is a validated convenience and machine-test path for one reported configuration, not the ground-truth cartridge.

### Mechanical baseline before protocol work

Do not interpret protocol-driven motion while the machine has unresolved mechanical faults. Repair or stabilize the feed-dog slider, install the correct needle, verify free handwheel motion, establish correct threading and bobbin setup, and document one valid ordinary stitch before repeated machine-link tests.

### Notebook before code

Do not implement the protocol merely because prior art exists. First establish ordinary machine operation, exact identities, deterministic cartridge verification, protected passive measurement, immutable captures, and claim-level provenance.

### Source-before-claim rule

Before relying on an external article, ROM catalog entry, emulator behavior, hardware manual, or source-code implementation, preserve the exact source identity. Record URL or file origin, archive location, access date, revision or commit, license, relevant section or symbol, extracted claim, and independent reproduction status. Search-engine snippets and memory are discovery aids, not evidence.

## Evidence register

| ID | Evidence | Class | Status |
|---|---|---|---|
| EVD-20260307-001 | Shonumi article archive | prior-art | recorded |
| EVD-20260804-001 | GBE+ sewing-machine support | prior-art/code-derived | commit and symbols not pinned |
| EVD-20260804-003 | OSCR assembled | observed/reported | awaiting artifacts |
| EVD-20260804-004 | ROM dumping works | observed/reported | awaiting logs and hashes |
| EVD-20260804-005 | Save dumping works | observed/reported | awaiting logs and hashes |
| EVD-20260503-001 | Sewing supplies acquired locally | observed/reported | package photos and exact identities missing |
| EVD-20260503-002 | Bobbin-winder spring-retention interpretation | inferred | authoritative manual confirmation missing |
| EVD-20260804-009 | FunnyPlaying write/redump | observed/reported | awaiting artifacts |
| EVD-20260804-010 | InsideGadgets CFI write/redump | observed/reported | awaiting artifacts |
| EVD-20260804-011 | Sewing software boots/screenshots | observed/reported | workbook and remote album retained; exact hashes incomplete |
| EVD-20260804-012 | R4, GameYob, and GBARunner2 work | observed/reported | separate from IZEK evidence |
| EVD-20260804-013 | R36S ROM recovery | observed/reported | side investigation |
| EVD-20260804-014 | Kingston SD-card failure | observed/reported | cause unknown |
| EVD-20260804-015 | Updated EZ-Flash Jr boots target set on stock GBC | observed/reported | exact matrix incomplete |
| EVD-20260804-016 | EZ-Flash Jr fails on FPGA GBC but works on original hardware | observed/reported | exact error record missing |
| EVD-20260804-017 | Six target images plus two controls booted on stock GBC | observed/reported | exact names and hashes incomplete |
| EVD-20260804-018 | EZ-Flash Jr path caused IZEK zig-zag needle motion | observed/reported | repeat evidence incomplete |
