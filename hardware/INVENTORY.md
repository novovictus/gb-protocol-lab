# Hardware Inventory

Status values: `owned`, `validated`, `validated/reported`, `planned`, `failed/reported`, `considered`, or `unknown`.

| ID | Item | Status | Project role | Notes |
|---|---|---|---|---|
| HW-001 | Singer IZEK 1500 | owned / mechanically impaired / validated-reported | Primary peripheral target | Acquired without original foot controller, cartridge, or console. Replacement controller produces motion. Stock GBC plus updated EZ-Flash Jr reportedly caused zig-zag needle motion and a thread-related halt. Feed-dog engagement slider has a broken cam-engagement notch; manual positioning restored downstream engagement. Valid threaded stitch not documented. |
| HW-002 | Singer-compatible replacement foot controller | owned / validated-reported | Powered machine tests | Purchased from Amazon. Manufacturer, model, ratings, connector, and photographs still required. |
| HW-003 | Original Game Boy Color | owned / validated-reported baseline | Ground-truth native cartridge and link tests | Completely stock unit reportedly booted the tested EZ-Flash Jr software set and communicated with the physical IZEK. Kirby on InsideGadgets reportedly reached upload and showed an error. Record exact model and board revision. |
| HW-004 | Game Boy Pocket | owned / validated-reported for selected software | DMG-class compatibility and negative controls | Singer/IZEK software reportedly booted and uploaded successfully in one retained run. A later Kirby run produced a CGB-only rejection screen, expected for CGB-only software. |
| HW-005 | FP-GBC | owned / mixed compatibility reported | FPGA comparison host | EZ-Flash Jr reportedly fails to boot. FunnyPlaying software reportedly booted, but Singer upload failed; Kirby reached upload and produced an error that may differ from original GBC. Record exact firmware/core. |
| HW-006 | OSCR | validated/reported | ROM/save reads and supported-cart writes | Record PCB, firmware, host software, commands, photographs, and hashes. Used for reported FunnyPlaying Singer write/redump and InsideGadgets Kirby write/redump. |
| HW-007 | InsideGadgets MBC5 2 MiB / 32 KiB FRAM cart | validated/reported | Preferred deterministic development cartridge | Kirby reportedly written/redumped using OSCR `CFI Repro`, `WE=WR`, and M29F160F-compatible behavior. Generic `29F Repro` was not the successful path. |
| HW-008 | FunnyPlaying EverSave GB/GBC Flash Cart Pro | validated/reported | Secondary rewritable target | Singer image reportedly written/redumped. Treat as MBC5-class single-image flash cart, not an SD menu loader. Boot and upload results vary by host and need reconstruction. |
| HW-009 | EZ-Flash Jr | validated/reported for one native path | Convenience loader and successful machine-test cart | Firmware updated. Reportedly booted target images on stock GBC and carried a successful Singer/IZEK interaction. Fails on FP-GBC. Not ground truth for cartridge equivalence. |
| HW-010 | Flipper Zero | owned | Possible later active endpoint or replay tool | Existing Game Boy link work is prior art, not an IZEK implementation. Active use is gated. |
| HW-011 | Logic analyzer | not established | Passive capture | Acquire or borrow if existing equipment cannot capture clock and both data directions reliably. |
| HW-012 | Nintendo DS-family consoles | owned | Separate flash-cart and compatibility work | GameYob and GBARunner2 reportedly operational. Not native GB/GBC protocol ground truth. |
| HW-013 | R4 SDHC | validated/reported | Separate DS convenience platform | Revived with period firmware. Exact cart revision and firmware identity remain unrecorded. |
| HW-014 | Kingston 32 GB SD card | failed/reported | R4 failure investigation | Preserve card and adapter; do not assign cause without diagnostics. |
| HW-015 | Allwinner-based R36S clone | owned / partial recovery | Side preservation source | ROM files reportedly recovered; alternate operating-system installation unsuccessful. |
| HW-016 | Damaged Game Boy Advance SP | owned / condition unknown | Candidate non-destructive link breakout source or repair project | Assess board, connector continuity, repair potential, and non-destructive options before harvesting. |
| HW-017 | Protected passive link breakout | planned | First physical capture fixture | Must expose console and machine-side conductors without active drive. |
| HW-018 | High-impedance DMM or scope probes | not established | Idle-state voltage survey | Required before attaching 3.3 V-only instrumentation. |
| HW-019 | Reproduction sewing-machine cartridges | ordered / pending | Deterministic and closer-to-original comparison path | Record supplier, board, mapper, flash/RAM parts, image, write procedure, and redump on arrival. |
| HW-020 | Original Game Boy Advance with ITA-style backlit display and glass lens | owned / reported test platform | Native GB/CGB compatibility-mode host | Display refurbishment improves readability and is not protocol evidence. Distinguish native GB/CGB mode from GBA-cart emulation. Kirby reportedly booted but produced an immediate upload error. |
| HW-021 | MiSTer | owned / unvalidated candidate | FPGA host with possible USERIO link path | Pin exact core, commit, link implementation, adapter design, voltage behavior, and demonstrated peripheral support before use. |
| HW-022 | SFC/SNES plus Super Game Boy 2 | considered | Official DMG/SGB-class host with link port | Not CGB-equivalent. `0x80` software may be testable; `0xC0` software is an expected boot failure. Genuine and clone hosts are separate classes. |
| HW-023 | Analogue Pocket | possible acquisition | Separate commercial FPGA host class | No project result. Test boot, UI, physical link, and machine communication separately. |
| HW-024 | ModRetro Chromatic | possible acquisition | Separate modern GBC-class host | No project result. Verify connector and electrical behavior before machine use. |
| HW-025 | Broken installed sewing needle | observed/reported / replace | Mechanical bring-up fault | Needle was found physically broken while locating the eye. It is unsuitable for valid sewing tests. Preserve or photograph before disposal and identify the authoritative replacement needle system and orientation. |
| HW-026 | Feed-dog engagement slider | damaged / manual engagement reported | Mechanical feed control | Cam-engagement notch is broken. External control cannot reliably engage the mechanism; manual positioning engaged the downstream feed-dog lift path. Durable repair, feed height, timing, and load behavior remain unverified. |
| HW-027 | Correct bobbins from craft store | owned / observed-reported | Ordinary sewing setup | Exact class and package identity need photo and manual confirmation. Bobbin-winder fit behavior should be documented against manual instructions. |
| HW-028 | 100% polyester all-purpose thread | owned / observed-reported | Ordinary sewing setup | Good for basic sewing bring-up, but exact brand, weight, and needle pairing should be recorded. |
| HW-029 | Singer oil | owned / observed-reported | Mechanical service | Record product identity and service points used before operation. |
| HW-030 | Needle multipack from craft store | owned / observed-reported | Replacement needle source | Exact system and size must be confirmed before powered sewing. |

## Immediate mechanical dependency

Before further powered or protocol-driven sewing tests:

- photograph and measure the broken feed-dog slider/notch;
- document engaged and disengaged positions;
- implement a reversible retention or durable repair;
- identify and install the correct needle system and orientation;
- verify unobstructed handwheel rotation;
- confirm upper thread, bobbin, threading, tension, presser-foot state, fabric, and stabilizer;
- produce and document one ordinary valid stitch.

## Fixture requirements

The protected passive breakout must preserve the normal path, default passive or fail-open, expose labeled test points, document connector provenance and orientation, pass continuity/short/isolation checks, record resistance and grounding, provide strain relief, and keep active injection physically disconnected until voltage compatibility is established.

For the damaged GBA SP, connector harvesting should wait until repair potential, continuity, pinout, voltage, and non-destructive alternatives are documented.

## Supporting resources

Project history also records donor GB/GBA hardware, soldering and rework tools, a GQ-4X programmer, and scrap cartridges. These are capabilities, not completed fixtures.
