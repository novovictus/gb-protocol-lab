# Hardware Inventory

Status values: `owned`, `validated`, `validated/reported`, `planned`, or `unknown`.

| ID | Item | Status | Project role | Notes |
|---|---|---|---|---|
| HW-001 | Singer IZEK 1500 | owned / validated-reported | Primary peripheral target | Acquired for USD 150 plus USD 80 shipping without original foot controller, cartridge, or console. Replacement controller produces basic motion; threaded stitch not validated. |
| HW-002 | Singer-compatible replacement foot controller | owned / validated-reported | Powered machine tests | Purchased from Amazon. Manufacturer, model, ratings, connector, and photographs still required. |
| HW-003 | Original Game Boy Color | owned / baseline | Ground-truth native cartridge and link tests | Preferred execution baseline. Record exact model and revision. |
| HW-004 | Game Boy Pocket | owned / reported test platform | Compatibility and negative controls | CGB-only failures are expected controls, not cartridge failures. |
| HW-005 | FPGA Game Boy Color | owned | Instrumentation and comparison | EZ-Flash Jr incompatibility reported; do not assume peripheral equivalence. |
| HW-006 | OSCR | validated/reported | ROM/save reads and supported-cart writes | Record PCB, firmware, host software, commands, photographs, and hashes. |
| HW-007 | InsideGadgets MBC5 2 MiB / 32 KiB FRAM cart | validated/reported | Preferred deterministic development cartridge | Reported successful write/redump using `CFI Repro`, `WE=WR`, and M29F160F-compatible behavior. |
| HW-008 | FunnyPlaying EverSave GB/GBC Flash Cart Pro | validated/reported | Secondary rewritable target | Singer operation image reportedly written and redumped. |
| HW-009 | EZ-Flash Jr | partially validated/reported | Original-hardware convenience loader | Reportedly works after firmware update on original hardware and fails on FPGA GBC. |
| HW-010 | Flipper Zero | owned | Possible later active endpoint or replay tool | Existing Game Boy link work is prior art, not an IZEK implementation. |
| HW-011 | Logic analyzer | not established | Passive capture | Acquire or borrow if existing equipment cannot capture clock and both data directions reliably. |
| HW-012 | Nintendo DS-family consoles | owned | Separate flash-cart and compatibility work | GameYob and GBARunner2 reportedly operational. Not native GB/GBC protocol ground truth. |
| HW-013 | R4 SDHC | validated/reported | Separate DS convenience platform | Revived with period firmware. Exact cart revision and firmware identity remain unrecorded. |
| HW-014 | Kingston 32 GB SD card | failed/reported | R4 failure investigation | Reportedly failed during R4 revival. Preserve card and adapter; do not assign cause without media or electrical diagnostics. |
| HW-015 | Allwinner-based R36S clone | owned / partial recovery | Side preservation source | ROM files reportedly recovered; alternate operating-system installation unsuccessful. |
| HW-016 | Damaged Game Boy Advance SP | owned / condition unknown | Candidate link connector donor or repair project | Dog-damaged. Assess board, connector continuity, repair potential, and non-destructive alternatives before harvesting. |
| HW-017 | Protected passive link breakout | planned | First physical capture fixture | Must expose console and machine-side conductors without active drive. Record connector provenance, schematic, component values, continuity, isolation, grounding, strain relief, and photographs. |
| HW-018 | High-impedance DMM or scope probes | not established | Idle-state voltage survey | Required before attaching 3.3 V-only instrumentation. Record instrument identity, probe impedance, coupling, reference point, and uncertainty. |

## Sewing setup still required

- confirmed needle system and size;
- upper thread and spool configuration;
- confirmed bobbin class and orientation;
- threading and tension procedure;
- scrap fabric and stabilizer;
- photographs and video of a repeatable stitch test.

## Supporting resources

Project history also records donor GB/GBA hardware, soldering and rework tools, a GQ-4X programmer, and scrap cartridges. These are capabilities, not completed fixtures.

For the damaged GBA SP, connector harvesting should wait until the board is photographed, repair potential is assessed, continuity is checked, pinout and voltage are independently verified, and strain relief and keyed orientation are designed.

## Passive breakout requirements

The first breakout revision should be passive by default and fail open rather than drive the bus. Before connection to rare hardware, document:

- connector source and orientation;
- one-to-one conductor map derived from continuity, not assumed pin numbering;
- direct-path resistance for every conductor;
- absence of adjacent and cross-conductor shorts;
- a common reference path only when verified appropriate;
- test points on every relevant conductor;
- default isolation of any later active branch;
- optional series resistance or other protection, with values and rationale recorded;
- keyed connections, strain relief, labels, and enclosure state;
- unpowered continuity and isolation results;
- powered idle-state voltage results before analyzer or microcontroller attachment.

Do not attach a 3.3 V-only analyzer, microcontroller, or active endpoint until voltage compatibility is measured. Do not connect an active branch until independent output-enable control, failback, and no-contention behavior are demonstrated.

## New-item template

For each added item record manufacturer, model, serial/revision, acquisition source/date, condition, modifications, included cables, power requirements, connector details, photographs, related experiments, and privacy or redistribution constraints.
