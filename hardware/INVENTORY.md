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

## Sewing setup still required

- confirmed needle system and size;
- upper thread and spool configuration;
- confirmed bobbin class and orientation;
- threading and tension procedure;
- scrap fabric and stabilizer;
- photographs and video of a repeatable stitch test.

## Supporting resources

Project history also records donor GB/GBA hardware, soldering and rework tools, a GQ-4X programmer, and scrap cartridges. These are capabilities, not completed fixtures.

Any breakout or adapter must have a schematic, continuity measurements, protection details, and photographs before use on rare hardware.

## New-item template

For each added item record manufacturer, model, serial/revision, acquisition source/date, condition, modifications, included cables, power requirements, connector details, photographs, related experiments, and privacy or redistribution constraints.
