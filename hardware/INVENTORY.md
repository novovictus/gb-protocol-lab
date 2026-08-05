# Hardware Inventory

Status values: `owned`, `validated`, `validated/reported`, `planned`, or `unknown`.

| ID | Item | Status | Project role | Notes |
|---|---|---|---|---|
| HW-001 | Singer IZEK 1500 | owned / validated-reported | Primary peripheral target | Acquired without original foot controller, cartridge, or console. Replacement controller produces motion. Stock GBC plus updated EZ-Flash Jr reportedly caused zig-zag needle motion and a thread-related halt. Valid threaded stitch not yet documented. |
| HW-002 | Singer-compatible replacement foot controller | owned / validated-reported | Powered machine tests | Purchased from Amazon. Manufacturer, model, ratings, connector, and photographs still required. |
| HW-003 | Original Game Boy Color | owned / validated-reported baseline | Ground-truth native cartridge and link tests | Completely stock unit reportedly booted the tested EZ-Flash Jr software set and communicated with the physical IZEK. Record exact model and board revision. |
| HW-004 | Game Boy Pocket | owned / reported test platform | Compatibility and negative controls | CGB-only failures are expected controls, not cartridge failures. |
| HW-005 | FPGA Game Boy Color | owned / incompatibility reported | Instrumentation and comparison | EZ-Flash Jr reportedly errors or fails while the same general path works on original hardware. Record exact device and firmware. |
| HW-006 | OSCR | validated/reported | ROM/save reads and supported-cart writes | Record PCB, firmware, host software, commands, photographs, and hashes. |
| HW-007 | InsideGadgets MBC5 2 MiB / 32 KiB FRAM cart | validated/reported | Preferred deterministic development cartridge | Reported successful write/redump using `CFI Repro`, `WE=WR`, and M29F160F-compatible behavior. |
| HW-008 | FunnyPlaying EverSave GB/GBC Flash Cart Pro | validated/reported | Secondary rewritable target | Singer operation image reportedly written and redumped. |
| HW-009 | EZ-Flash Jr | validated/reported for one native path | Current convenience loader and successful machine-test cart | Firmware updated. Reportedly booted six target images plus Pokemon Picross and Grimace's Birthday on stock GBC and carried a successful Singer/IZEK interaction. Not equivalent to an original or deterministic single-image cart; fails on FPGA GBC. |
| HW-010 | Flipper Zero | owned | Possible later active endpoint or replay tool | Existing Game Boy link work is prior art, not an IZEK implementation. |
| HW-011 | Logic analyzer | not established | Passive capture | Acquire or borrow if existing equipment cannot capture clock and both data directions reliably. |
| HW-012 | Nintendo DS-family consoles | owned | Separate flash-cart and compatibility work | GameYob and GBARunner2 reportedly operational. Not native GB/GBC protocol ground truth. |
| HW-013 | R4 SDHC | validated/reported | Separate DS convenience platform | Revived with period firmware. Exact cart revision and firmware identity remain unrecorded. |
| HW-014 | Kingston 32 GB SD card | failed/reported | R4 failure investigation | Preserve card and adapter; do not assign cause without media or electrical diagnostics. |
| HW-015 | Allwinner-based R36S clone | owned / partial recovery | Side preservation source | ROM files reportedly recovered; alternate operating-system installation unsuccessful. |
| HW-016 | Damaged Game Boy Advance SP | owned / condition unknown | Candidate non-destructive link breakout source or repair project | Assess board, connector continuity, repair potential, and non-destructive breakout options before harvesting. |
| HW-017 | Protected passive link breakout | planned | First physical capture fixture | Must expose console and machine-side conductors without active drive. Record provenance, schematic, component values, continuity, isolation, grounding, strain relief, and photographs. |
| HW-018 | High-impedance DMM or scope probes | not established | Idle-state voltage survey | Required before attaching 3.3 V-only instrumentation. |
| HW-019 | Reproduction sewing-machine cartridges | ordered / pending | Deterministic and closer-to-original comparison path | Not yet received or tested. Record supplier, board design, mapper, flash/RAM parts, image, write procedure, and redump on arrival. |

## Immediate mechanical dependency

Correct ordinary sewing-machine operation must be established before repeated stitch experiments:

- confirmed needle system and size;
- upper thread and spool configuration;
- confirmed bobbin class and orientation;
- threading and tension procedure;
- presser-foot state;
- scrap fabric and stabilizer;
- photographs and video of a repeatable valid stitch.

Dry needle motion is useful evidence but should not be repeated unnecessarily because machine safety logic and lubrication or load assumptions may expect normal sewing setup.

## Fixture requirements

The protected passive breakout must:

- preserve the normal console-to-machine path;
- default to passive or fail-open behavior;
- expose labeled test points without introducing active drive;
- document connector provenance and keyed orientation;
- include continuity, short, and isolation checks before power;
- record direct-path resistance and grounding arrangement;
- provide strain relief and physical protection;
- keep active injection paths physically disconnected until explicitly enabled;
- prohibit connection of 3.3 V-only equipment until idle and active voltage levels are measured.

For the damaged GBA SP, connector harvesting should wait until the board is photographed, repair potential is assessed, continuity is checked, pinout and voltage are independently verified, and non-destructive alternatives are exhausted.

## Supporting resources

Project history also records donor GB/GBA hardware, soldering and rework tools, a GQ-4X programmer, and scrap cartridges. These are capabilities, not completed fixtures.

## New-item template

For each added item record manufacturer, model, serial/revision, acquisition source/date, condition, modifications, included cables, power requirements, connector details, photographs, related experiments, and privacy or redistribution constraints.
