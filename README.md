# Game Boy Protocol Lab

Evidence-driven reverse engineering of Game Boy communication protocols, peripherals, cartridges, and undocumented hardware behavior.

The initial target is the Singer IZEK / Jaguar JN sewing-machine interface.

## Current state

A completely stock Game Boy Color running Singer/IZEK software from an updated EZ-Flash Jr reportedly communicated with the physical Singer IZEK. Selecting a simple zig-zag operation produced visible lateral needle motion; running without the old upper thread then caused a halt with a thread-related error.

This is retained as `observed/reported` until the exact software hash, EZ-Flash Jr firmware, microSD identity, console revision, machine setup, dated media, and complete repeat record are committed. It establishes an end-to-end behavioral path for one configuration, not protocol semantics, cartridge equivalence, or a valid threaded stitch.

The project also has reported OSCR ROM/save acquisition and deterministic rewritable-cartridge workflows. 

## Documents

- [Project status and next actions](docs/STATUS.md)
- [Research notebook, evidence, history, and decisions](docs/NOTEBOOK.md)
- [Prior art and attribution](docs/REFERENCES.md)
- [Hardware inventory](hardware/INVENTORY.md)

## Attribution and licensing

This work builds on prior reverse engineering by Shonumi concerning the Singer IZEK and Jaguar JN Game Boy sewing-machine interface.
