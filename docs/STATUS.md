# Project Status

Last updated: 2026-08-04

## Phase

Repository framing, prior-art review, asset inventory preparation, and evidence-preservation planning.

## Active research target

Singer IZEK / Jaguar JN Game Boy sewing-machine interface.

Known related systems named in the current repository:

- Singer IZEK 1500
- Jaguar JN-100
- Jaguar JN-2000

## Repository-confirmed resources

The current repository records the following resources as available or identified:

- Shonumi's public reverse-engineering article.
- A dated Internet Archive snapshot of that article.
- Public GBE+ source containing sewing-machine support.
- OSCR cartridge-dumping hardware.
- Physical Game Boy and cartridge hardware suitable for future experiments.

These entries document project resources and prior art. They are not protocol findings.

## Current claim boundary

No project-generated capture, protocol reproduction, electrical measurement, cartridge hash, hardware inventory, decoder, firmware implementation, or sewing-machine communication test is currently present in the repository.

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

## Work products now defined

The notebook structure defines:

- claim and evidence labels;
- stable experiment, evidence, and hardware identifiers;
- inventory and experiment templates;
- artifact manifests and hash requirements;
- explicit separation of prior art, code-derived findings, inference, and observation.

## Immediate next actions

1. Complete the physical asset inventory using `hardware/INVENTORY.md`.
2. Create the first experiment record before operating OSCR or attaching measurement equipment.
3. Record cartridge dump metadata and hashes without committing restricted ROM content.
4. Map article statements and GBE+ behavior into `docs/EVIDENCE.md` as `prior-art` or `code-derived`.
5. Document the intended electrical capture setup and safety assumptions before connecting it.
6. Add project-generated observations only after artifacts and procedures exist.
