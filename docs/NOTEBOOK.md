# Research Notebook

Record for project history, evidence, decisions, and reconstructed experiments.

## Chronology

### 2026-03-07: prior-art preservation

Shonumi's Singer IZEK / Jaguar JN article was archived at:

`https://web.archive.org/web/20260307065209/https://shonumi.github.io/articles/art22.html`

### 2026-04-18: prior work recognized

Shonumi's article and GBE+ were recognized as substantial prior work. Future implementation attributes prior art and distinguish reproduction from discovery.

### 2026-05-03: ordinary sewing setup supplies

Amazon sewing-supply purchases were returned and correct supplies were acquired locally from a craft store. The set included correct bobbins, 100% polyester all-purpose thread, a needle multipack, and Singer oil.

Exact bobbin class, needle system, package identity, and manual-backed compatibility are not yet artifact-backed. The bobbin-winder behavior was interpreted as spring-loaded retention rather than free-spinning full-depth seating.

### Historical work

#### OSCR acquisition and dump validation

Assemble OSCR, read ROM, read save, load output in an emulator, and confirm usable behavior.

Results:

- ROM dumping worked.
- Save dumping worked.
- At least one output was usable in an emulator.

#### Singer IZEK powered bring-up

A replacement Singer-compatible foot controller purchased from Amazon powered the Singer IZEK 1500 and produced basic machine motion.

This did not establish correct threading, bobbin setup, tension, fabric feed, lockstitch formation, sustained operation, controller equivalence, or Game Boy communication.

#### Rewritable-cartridge workflows

- a Singer/IZEK image was written to and redumped from a FunnyPlaying EverSave GB/GBC Flash Cart Pro;
- `Jaguar Mishin Sashi Senyou Soft - Kirby Family (Japan) (Proto)` was written to and redumped from an InsideGadgets MBC5 2 MiB / 32 KiB FRAM cartridge;
- the successful InsideGadgets path used OSCR `CFI Repro`, `WE=WR`, and M29F160F-compatible behavior;
- generic `29F Repro` was not the successful path;
- `HEADER CHECKSUM ERROR` was treated as compatible with a blank or uninitialized image, while `Flash ID: 0101 / Unknown flashrom` was the operative blocker before selecting the CFI path.

#### Cartridge compatibility and software inventory

- Original Game Boy hardware is the behavioral baseline.
- EZ-Flash Jr reportedly worked after firmware update on original hardware and failed on FP-GBC.
- Deterministic single-image rewritable cartridges are preferred over SD menu loaders for machine tests.
- `Raku x Raku Mishin` is retained as the base sewing-machine control path.
- Kirby, Mario, Cut Shuu, and Moji are retained as embroidery/design-unit paths.
- Game Boy Pocket failures for CGB-only software are negative controls.

Software inventory:

| Software | Role | Boundary |
|---|---|---|
| Sewing Machine Operation Software (USA) (En,Fr,Es) | Western Singer IZEK control | exact dump identity unverified |
| Raku x Raku Mishin | JN-100 base control | retained from prior work |
| Raku x Raku Moji | JN-2000 lettering | retained from prior work |
| Raku x Raku Cut Shuu | JN-2000 design | retained from prior work |
| Mario Family | JN-2000 licensed designs | retained from prior work |
| Kirby Family | JN-2000 embroidery | `(Proto)` is catalog metadata, not proof of release status |

Singer operation software header:

| Field | Value | Meaning |
|---|---:|---|
| CGB flag `0x0143` | `0x80` | CGB-enhanced / backward compatible |
| cartridge type `0x0147` | `0x1B` | MBC5 + RAM + battery |
| ROM size `0x0148` | `0x05` | 1 MiB |
| RAM size `0x0149` | `0x02` | 8 KiB |
| destination `0x014A` | `0x01` | non-Japanese |

`Pokemon Picross` beta and `Grimace's Birthday` are non-IZEK controls for flash, boot, save, redump, and hash workflow validation.

Original MBC5 + RAM + battery cartridges generally use battery-backed SRAM. Modern FRAM replacement cartridges are a development convenience.

#### 2026-08-04 handheld side work

Reported results:

- an old R4 SDHC was revived with period firmware;
- GameYob and GBARunner2 were made operational on Nintendo DS hardware;
- a Kingston 32 GB SD card failed, with cause unknown;
- ROM files were recovered from an Allwinner-based R36S clone;
- alternate R36S operating-system installation was unsuccessful;
- a damaged GBA SP was identified as a possible non-destructive link-breakout source or repair project.

## Reconstructed experiments

### EXP-20260804-RECON-001: EZ-Flash Jr to Singer IZEK

Setup:

- completely stock original Game Boy Color;
- EZ-Flash Jr updated before testing;
- microSD identity not recorded;
- Singer/IZEK software image, exact filename and SHA-256 not recorded;
- Singer IZEK, machine cable, and replacement foot controller;
- old upper thread initially present, then removed;
- reproduction cartridges not yet received.

Observations:

- six target images plus Pokemon Picross and Grimace's Birthday reportedly booted on the stock GBC;
- EZ-Flash Jr failed or errored on FP-GBC while functioning on original hardware;
- selecting a simple zig-zag operation caused visible lateral needle motion;
- operation without upper thread halted;
- a thread-related error.

Narrow interpretation:

The tested software image, updated EZ-Flash Jr, stock GBC, cable, and Singer IZEK exchanged enough information to produce selected physical needle motion and a thread-related stop condition. This supersedes the earlier statement that flash-cart communication with the physical IZEK had not been observed.

### EXP-RECON-MECH-001: Feed-dog engagement failure

Procedure:

1. Open the bottom panel.
2. Inspect the external feed control and internal mechanism.
3. Observe the slider and cam-engagement path.
4. Move the slider manually into the engaged position.

Observations:

- the external switch mechanically operates a slider that engages a cam;
- the slider's engagement notch was broken;
- the break prevented the external control from engaging the mechanism;
- manually sliding the mechanism into position engaged the downstream feed-dog lift path.

Narrow result:

The immediate feed-dog failure was localized to the broken slider/notch transfer feature, while the downstream cam mechanism could still be engaged manually.

### EXP-RECON-MECH-002: Broken needle discovery

While locating the needle eye, the installed needle was found not to have a normal sharp end and was recognized as broken.

This establishes only that the installed needle was unsuitable for a valid sewing test. It does not establish that the needle caused any specific electronic error, motor stop, red indicator, link error, or earlier motion anomaly.

### EXP-RECON-MECH-003: Ramp, stop, and red indicator

Pressing the sew control reportedly caused the machine to start, ramp in speed, stop, and blink red at the switch or indicator.

Concurrent unresolved conditions included the broken feed-dog engagement slider, manual feed-dog engagement, and a broken needle. Exact sequencing and machine configuration were not preserved.

The behavior is a fault indication, but its source is not established. Do not label it as thread detection, tension sensing, motor overload, position-sensor failure, or a specific service code without authoritative mapping or measurement.

### EXP-RECON-LINK-001: Upper-machine error graphic

The Game Boy software reportedly displayed an error graphic pointing toward the top of the machine.

The graphic may refer to upper threading, spool routing, take-up, tension, or another upper-machine condition. The exact frame and authoritative manual text are not preserved. The observation does not prove a direct thread-presence or tension sensor.

### Compatibility experiments

- Singer image on FunnyPlaying cart with original GBC;
- Singer image on FunnyPlaying cart with Game Boy Pocket;
- Singer image on FunnyPlaying cart with FP-GBC;
- Kirby image on InsideGadgets cart with original GBA;
- Kirby image on InsideGadgets cart with Game Boy Pocket;
- Kirby image on InsideGadgets cart with original GBC;
- Kirby image on InsideGadgets cart with FP-GBC;
- EZ-Flash Jr boot and physical-machine run on stock GBC;
- EZ-Flash Jr failure on FP-GBC.

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
| EVD-20260804-011 | Sewing software boots/screenshots | observed/reported | hashes and exact records missing |
| EVD-20260804-012 | R4, GameYob, and GBARunner2 work | observed/reported | separate from IZEK evidence |
| EVD-20260804-013 | R36S ROM recovery | observed/reported | side investigation |
| EVD-20260804-014 | Kingston SD-card failure | observed/reported | cause unknown |
| EVD-20260804-015 | Updated EZ-Flash Jr boots target set on stock GBC | observed/reported | exact matrix missing |
| EVD-20260804-016 | EZ-Flash Jr fails on FPGA GBC but works on original hardware | observed/reported | exact error record missing |
| EVD-20260804-017 | Six target images plus two controls booted on stock GBC | observed/reported | exact names and hashes incomplete |
| EVD-20260804-018 | EZ-Flash Jr path caused IZEK zig-zag needle motion | observed/reported | experiment artifacts missing |
| EVD-20260804-019 | Thread removal led to a thread-related halt | observed/reported | source and meaning unverified |
| EVD-20260804-020 | End-to-end stock-GBC/EZ-Flash Jr/IZEK path functioned | inferred from reported observations | narrow configuration only |
| EVD-20260804-021 | Valid threaded stitch | unverified | not established |
| EVD-20260804-022 | Reproduction cartridges ordered | reported state | pending receipt and validation |
| EVD-20260804-023 | Feed-dog slider notch broken | observed/reported | photographs and dimensions missing |
| EVD-20260804-024 | Manual slider positioning engaged feed-dog lift path | observed/reported | durability and timing unverified |
| EVD-20260804-025 | Installed needle physically broken | observed/reported | exact needle system unknown |
| EVD-20260804-026 | Sew control caused ramp-stop-red behavior | observed/reported | fault source unresolved |
| EVD-20260804-027 | Game Boy displayed upper-machine error graphic | observed/reported | exact frame and meaning unresolved |
