# Hardware and Tooling Inventory

Status values:

- `owned`: physically available;
- `validated`: exercised successfully for the stated purpose;
- `planned`: identified but not completed;
- `unknown`: possession or condition is known, but function for this project is not established.

## Target hardware

| Item | Status | Project role | Notes |
|---|---|---|---|
| Singer IZEK 1500 | owned / unknown functional state | Primary peripheral target | Acquired for USD 150 plus USD 80 shipping, without foot controller, original cartridge, or console. Mechanical and powered bring-up evidence not yet recorded here. |
| Singer-compatible foot controller | missing / planned | Required for controlled powered sewing tests | Exact compatible part and electrical characteristics must be verified; do not substitute a generic potentiometer without characterization. |
| Jaguar JN-100/JN-2000 or embroidery unit | not established | Secondary targets | Embroidery-unit spoofing and design extraction are deferred. |

## Game Boy execution platforms

| Item | Status | Project role | Caveat |
|---|---|---|---|
| Original Game Boy Color hardware | owned / baseline | Ground-truth execution and peripheral tests | Current known-good target for cartridge validation. |
| Other original GB-family systems | owned | Compatibility and negative-control tests | Exact models and revisions should be inventoried. |
| FPGA Game Boy Color | owned | Potential instrumentation and comparison platform | Do not assume peripheral or flash-cart equivalence; EZ-Flash Jr incompatibility is already reported. |
| Original Nintendo DS-family systems | owned but out of path | Separate DS/GBA research | DS hardware is not a substitute for the classic Game Boy link interface. |

## Cartridge tools and media

| Item | Status | Role | Notes |
|---|---|---|---|
| OSCR | validated | ROM/save dumping and supported-cart writing | Record PCB revision, firmware, host software, and build photographs. |
| InsideGadgets MBC5 2 MiB / 32 KiB FRAM ultra-low-power cart | validated/reported | Deterministic single-image development and verification cart | Selected to avoid battery-backed SRAM and SD-loader ambiguity. |
| FunnyPlaying EverSave GB/GBC Flash Cart Pro | validated/reported | Additional rewritable target | Singer operation image reportedly flashed and redumped successfully. |
| EZ-Flash Jr | partially validated | Multi-ROM convenience loader on original hardware | Works on original hardware after firmware update; fails on FPGA GBC. Do not use FPGA failure as evidence against a ROM or peripheral. |
| EZ-Flash GBA cart | owned / unsuitable for native GB link baseline | GBA software | GB/GBC software through GBA-side emulation is not a clean native-link baseline. |

## Capture and implementation platforms

| Item | Status | Role | Notes |
|---|---|---|---|
| Flipper Zero | owned | Future active link endpoint or replay tool | Public Pokemon-trading work is useful implementation prior art, not an IZEK implementation. |
| FPGA GBC instrumentation | planned | Correlate software execution with link activity | Feasibility depends on accessible core instrumentation and accurate external signaling. |
| Dedicated logic analyzer | not reported as owned | Passive capture | A modest analyzer should be the first purchase/borrow if current tools cannot capture both data directions and clock reliably. |
| High-end scope/protocol analyzer | not required at present | Escalation tool | Justified only by measured signal-integrity, threshold, or timing ambiguity. |

## Fixture and rework resources retained in project history

- donor Game Boy/GBA hardware, including a non-working GBA SP considered for EXT-port salvage;
- general soldering and rework tools, including flux, braid, solder sucker, ChipQuik, and heat tools;
- GQ-4X programmer;
- scrap cartridges suitable for non-critical donor parts.

These are capabilities, not completed fixtures. Any breakout or adapter should be documented with photographs, continuity measurements, protection components, and a schematic before use on rare hardware.
