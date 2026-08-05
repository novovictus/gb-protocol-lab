# Game Boy Protocol Lab

Evidence-driven reverse engineering of Game Boy communication protocols, peripherals, cartridges, and undocumented hardware behavior.

The initial target is the Singer IZEK / Jaguar JN sewing-machine interface.

## Current state

A completely stock Game Boy Color running Singer/IZEK software from an updated EZ-Flash Jr reportedly communicated with the physical Singer IZEK. Selecting a simple zig-zag operation produced visible lateral needle motion; running without the old upper thread then caused a halt with a thread-related error.

This is retained as `observed/reported` until the exact software hash, EZ-Flash Jr firmware, microSD identity, console revision, machine setup, dated media, and complete repeat record are committed. It establishes an end-to-end behavioral path for one configuration, not protocol semantics, cartridge equivalence, or a valid threaded stitch.

The project also has reported OSCR ROM/save acquisition and deterministic rewritable-cartridge workflows. Their logs, hashes, photographs, versions, and dated records remain evidence gaps.

## Canonical documents

- [Project status and next actions](docs/STATUS.md)
- [Research notebook, evidence, history, and decisions](docs/NOTEBOOK.md)
- [Prior art and attribution](docs/REFERENCES.md)
- [Hardware inventory](hardware/INVENTORY.md)

## Compatibility evidence

- [IZEK compatibility test matrix](docs/izek_test_matrix.xlsx)
- [Remote compatibility photo album](https://photos.app.goo.gl/GYaj7Pjwva9XXzap6)

The workbook records structured compatibility results. The remote album retains the corresponding visual evidence. A screen state or successful boot does not by itself establish completed upload, protocol equivalence, electrical compatibility, machine motion, or valid stitch formation.

## Repository layout

```text
docs/          Canonical project documentation and compatibility records
hardware/      Inventory, fixtures, and hardware notes
captures/      Raw and processed protocol captures
firmware/      Embedded implementations
tools/         Analysis and capture utilities
```

## Claim boundary

The reported physical interaction establishes only that the tested software image, updated EZ-Flash Jr, stock GBC, cable, and Singer IZEK exchanged enough information to produce machine motion and a thread-related halt. It does not establish connector pinout, voltage levels, signaling direction, serial clock ownership, packet framing, command semantics, timing, stitch encoding, model equivalence, the source of the halt, or generalized flash-cart compatibility.

## Attribution and licensing

This work builds on prior reverse engineering by Shonumi concerning the Singer IZEK and Jaguar JN Game Boy sewing-machine interface.
