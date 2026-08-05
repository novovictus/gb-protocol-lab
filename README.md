# Game Boy Protocol Lab

Evidence-driven reverse engineering of Game Boy communication protocols, peripherals, cartridges, and undocumented hardware behavior.

The initial target is the Singer IZEK / Jaguar JN sewing-machine interface.

## Current state

The project has working reported ROM/save acquisition and rewritable-cartridge workflows, and the Singer IZEK has produced basic powered motion with a replacement controller. Those results are retained as `observed/reported` until the supporting logs, hashes, photographs, versions, and dated test records are committed.

The machine has not yet been documented forming a valid threaded stitch. No project-generated protocol capture, decoded command stream, replay, or replacement endpoint exists.

## Canonical documents

- [Project status and next actions](docs/STATUS.md)
- [Research notebook, evidence, history, and decisions](docs/NOTEBOOK.md)
- [Prior art and attribution](docs/REFERENCES.md)
- [Hardware inventory](hardware/INVENTORY.md)

## Repository layout

```text
docs/          Canonical project documentation
hardware/      Inventory, fixtures, and hardware notes
captures/      Raw and processed protocol captures
artifacts/     Logs, manifests, hashes, and lawful evidence
firmware/      Embedded implementations
tools/         Analysis and capture utilities
```

## Claim boundary

Current cartridge and tooling results do not establish IZEK connector pinout, voltage levels, signaling direction, serial clock ownership, packet framing, command semantics, timing, stitch encoding, model equivalence, or flash-cart communication with the physical machine.

## Attribution and licensing

This work builds on prior reverse engineering by Shonumi concerning the Singer IZEK and Jaguar JN Game Boy sewing-machine interface.

GBE+ is GPLv2-licensed. Copied or adapted code must retain applicable notices and comply with that license. Independently written work must still document the prior knowledge that informed it.

No repository-wide software license has been selected yet. Do not commit commercial ROMs, proprietary firmware, credentials, or material without redistribution permission.
