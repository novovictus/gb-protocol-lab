# Hardware and Tooling Inventory

Status values:

- `owned`: physically available;
- `validated`: exercised successfully for the stated purpose with repository artifacts;
- `validated/reported`: exercised successfully but primary artifacts are not yet committed;
- `planned`: identified but not completed;
- `unknown`: possession or condition is known, but function for this project is not established.

## Target hardware

| Item | Status | Project role | Notes |
|---|---|---|---|
| Singer IZEK 1500 | owned / powered motion validated-reported | Primary peripheral target | Acquired for USD 150 plus USD 80 shipping, without original foot controller, original cartridge, or console. Replacement pedal produces basic powered operation. Threaded stitch formation is not yet validated. |
| Replacement Singer-compatible foot controller | owned / validated-reported | Controlled powered sewing tests | Purchased from Amazon. Record manufacturer, model, electrical rating, connector, and photographs. Do not infer equivalence to the original controller beyond observed operation. |
| Jaguar JN-100/JN-2000 or embroidery unit | not established | Secondary targets | Embroidery-unit spoofing and design extraction remain deferred. |

## Sewing consumables and setup

| Item | Status | Notes |
|---|---|---|
| Upper thread/spool | not established | Confirm ordinary household thread compatibility from manual or experienced operator. |
| Bobbin | not established | Do not record a class by guess; confirm from machine/manual or physical fit. |
| Needle | not established | Record system and size before testing. |
| Scrap fabric and stabilizer | planned | Use for repeatable basic stitch validation. |
| Threading and bobbin procedure | not established | Photograph each path and record tension/settings once demonstrated. |

## Game Boy execution platforms

| Item | Status | Project role | Caveat |
|---|---|---|---|
| Original Game Boy Color hardware | owned / baseline | Ground-truth execution and peripheral tests | Preferred known-good target for native cartridge and link behavior. |
| Other original GB-family systems | owned | Compatibility and negative-control tests | Exact models and revisions should be inventoried. |
| Game Boy Pocket | owned/reported test platform | Negative-control and compatibility testing | CGB-only failures are expected and must not be mislabeled as cart or link failures. |
| FPGA Game Boy Color | owned | Potential instrumentation and comparison platform | EZ-Flash Jr incompatibility is reported; do not assume peripheral equivalence. |
| Original Nintendo DS-family systems | owned but out of IZEK path | Separate DS/GBA research | DS R4 Pokemon deployment is unrelated to the classic Game Boy sewing-machine protocol. |

## Cartridge tools and media

| Item | Status | Role | Notes |
|---|---|---|---|
| OSCR | validated/reported | ROM/save dumping and supported-cart writing | Built; ROM and save dumping work; output validated in emulator. Record PCB revision, firmware, host software, commands, and hashes. |
| InsideGadgets MBC5 2 MiB / 32 KiB FRAM ultra-low-power cart | validated/reported | Deterministic single-image development and verification cart | Selected to avoid battery-backed SRAM and SD-loader ambiguity. |
| FunnyPlaying EverSave GB/GBC Flash Cart Pro | validated/reported | Additional rewritable target | Singer operation image reportedly flashed and redumped successfully. |
| EZ-Flash Jr | partially validated/reported | Multi-ROM convenience loader on original hardware | Works on original hardware after firmware update; fails on FPGA GBC. |
| EZ-Flash GBA cart | owned / unsuitable for native GB link baseline | GBA software | Testing may be useful for inventory, but does not prove native GB/GBC link behavior. |
| DS R4 | owned / out of scope | Separate DS software deployment | Do not mix its results into IZEK protocol evidence. |

## Capture and implementation platforms

| Item | Status | Role | Notes |
|---|---|---|---|
| Flipper Zero | owned | Future active link endpoint or replay tool | Related Game Boy link work is implementation prior art, not an IZEK implementation. |
| FPGA GBC instrumentation | planned | Correlate software execution with link activity | Feasibility depends on accessible core instrumentation and accurate external signaling. |
| Dedicated logic analyzer | not reported as owned | Passive capture | A modest analyzer should be the first purchase/borrow if existing tools cannot capture clock and both data directions reliably. |
| High-end scope/protocol analyzer | not required at present | Escalation tool | Justified only by measured signal-integrity, threshold, or timing ambiguity. |

## Fixture and rework resources retained in project history

- donor Game Boy/GBA hardware, including a non-working GBA SP considered for EXT-port salvage;
- general soldering and rework tools, including flux, braid, solder sucker, ChipQuik, and heat tools;
- GQ-4X programmer;
- scrap cartridges suitable for non-critical donor parts.

These are capabilities, not completed fixtures. Any breakout or adapter should be documented with photographs, continuity measurements, protection components, and a schematic before use on rare hardware.
