# Project Status

Last updated: 2026-08-04

## Phase

Physical baseline validation, cartridge workflow documentation, intended-hardware compatibility testing, and prior-art mapping.

Protocol implementation is intentionally deferred until the machine and software path are validated and a project-generated capture exists.

## Active research target

Singer IZEK / Jaguar JN Game Boy sewing-machine interface.

Related systems retained in scope:

- Singer IZEK 1500
- Jaguar JN-100
- Jaguar JN-2000

## Current project state

### Artifact-backed repository facts

- The repository has an evidence-oriented notebook structure.
- Shonumi's article and its 2026-03-07 Internet Archive snapshot are recorded.
- GBE+ is recorded as relevant GPLv2 prior art.

### Bench results retained from project history

The following are `observed/reported`, not yet fully artifact-backed in this repository:

- OSCR hardware was built successfully.
- Game Boy ROM dumping works.
- Game Boy save dumping works.
- A dumped ROM/save workflow was validated in an emulator.
- A replacement foot controller arrived and was tested with the Singer IZEK.
- The machine demonstrated basic powered sewing-machine functionality.

The last item does not mean that a threaded stitch was produced. Correct threading, bobbin type, spool setup, tension, and end-to-end sewing operation remain unvalidated in the notebook.

### Cartridge and execution work retained from project history

- Original Game Boy hardware is the preferred behavioral baseline.
- EZ-Flash Jr reportedly worked on original hardware after a firmware update and failed on an FPGA GBC.
- InsideGadgets and FunnyPlaying rewritable cartridges were selected or exercised as deterministic cartridge targets.
- A canonical test matrix existed outside this repository and classified `Raku x Raku - Mishin` as the base sewing-machine control path.
- Kirby, Mario, Cut Shuu, and Moji titles were classified as embroidery/design-unit paths rather than simple link failures.
- Game Boy Pocket results for CGB-only titles were treated as expected negative controls.

These points require import of the canonical matrix, exact firmware versions, hashes, and test records before promotion beyond `observed/reported`.

## Current claim boundary

No project-generated IZEK communication capture, voltage measurement, decoded packet, replay trace, endpoint emulator, or independently verified protocol implementation is present.

The repository therefore makes no independent technical claim about:

- connector pinout;
- voltage levels;
- signaling direction;
- serial clock ownership;
- packet format;
- command semantics;
- timing;
- status values;
- coordinate or stitch encoding;
- behavioral differences among machine models.

## Current blockers

1. The machine has not been documented forming a valid stitch.
2. The original cartridge is not recorded as present.
3. Flash-cart operation with the physical IZEK is not yet documented.
4. Existing successful dump and cartridge tests lack committed hashes and logs.
5. Prior-art protocol details have not been mapped claim-by-claim to article sections or GBE+ symbols.
6. No passive electrical capture setup has been documented or executed.

## Immediate next actions

1. Confirm the correct needle, upper thread, bobbin class, bobbin orientation, and threading path.
2. Record one repeatable straight-stitch test on scrap fabric.
3. Inventory the Game Boy, flash carts, OSCR revision, firmware, and host software versions.
4. Reproduce one ROM dump and one save dump with command logs and hashes.
5. Import or reconstruct the canonical software/cart compatibility matrix without committing ROM content.
6. Test the selected native GB/GBC flash cart on original Game Boy hardware, then with the IZEK.
7. Capture machine behavior, prompts, and failure modes before attaching a logic analyzer.
8. Map Shonumi article statements and GBE+ behavior into evidence records.
9. Design and document a protected passive link breakout.
10. Implement code only after a measured protocol question requires it.
