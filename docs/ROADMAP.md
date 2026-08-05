# Roadmap

## Phase 0: Repository and provenance

- Establish project scope.
- Preserve prior-art references.
- Define attribution and licensing boundaries.
- Start a chronological research log.

## Phase 1: Asset inventory and preservation

- Inventory Game Boy systems, cartridges, sewing-machine hardware, cables, and adapters.
- Photograph labels, connectors, boards, and cartridge PCBs.
- Dump relevant cartridges with OSCR.
- Record hashes and dumping conditions.
- Commit only metadata, hashes, procedures, and legally distributable artifacts.

## Phase 2: Prior-art mapping

- Annotate Shonumi's article by protocol stage.
- Locate corresponding GBE+ code paths.
- Map commands, states, packet formats, timing assumptions, status values, and coordinate handling.
- Build an evidence matrix.

## Phase 3: Safe hardware observation

- Confirm connector pinout and voltage levels.
- Design or select non-invasive capture hardware.
- Record idle behavior, startup behavior, clock ownership, packet boundaries, and timing.
- Compare captures against prior art.

## Phase 4: Independent decoder

- Implement a capture parser from independently documented behavior.
- Add fixtures derived from project-generated captures.
- Keep transport, protocol, and visualization layers separate.

## Phase 5: Active implementation

Potential targets:

- Game Boy test ROM
- microcontroller bridge
- PC-side protocol tool
- sewing-pattern visualization
- hardware-in-the-loop test harness
