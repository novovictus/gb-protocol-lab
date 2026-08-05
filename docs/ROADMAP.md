# Roadmap

The roadmap is ordered to preserve evidence and constrain claims before implementation work begins.

## Phase 0: Repository and provenance

- [x] Establish project scope.
- [x] Preserve the known archived prior-art reference.
- [x] Define attribution and licensing boundaries.
- [x] Start a chronological research log.
- [x] Define claim and evidence classes.
- [x] Add inventory, experiment, and artifact templates.

Exit criterion: a contributor can record a result without ambiguity about provenance, evidence class, or artifact handling.

## Phase 1: Asset inventory and preservation

- [ ] Inventory Game Boy systems, cartridges, sewing-machine hardware, cables, adapters, and OSCR equipment.
- [ ] Assign stable hardware IDs.
- [ ] Photograph labels, connectors, boards, and cartridge PCBs.
- [ ] Record ownership and redistribution constraints.
- [ ] Dump relevant cartridges with OSCR.
- [ ] Perform repeated dumps and compare hashes.
- [ ] Record hashes, tool versions, and dumping conditions.
- [ ] Commit only metadata, procedures, and legally distributable artifacts.

Exit criterion: all research inputs are identifiable and cartridge dumps are reproducible and integrity-checked.

## Phase 2: Prior-art mapping

- [ ] Review the archived Shonumi article by protocol layer.
- [ ] Pin the GBE+ revision reviewed.
- [ ] Locate corresponding files and symbols.
- [ ] Separate article claims from implementation behavior.
- [ ] Record commands, states, packet formats, timing assumptions, status values, and coordinate handling as individual evidence entries.
- [ ] Mark each item `prior-art`, `code-derived`, `inferred`, or `unverified`.

Exit criterion: the project can state exactly what is already known, where it came from, and what remains unverified.

## Phase 3: Safe hardware observation

- [ ] Identify connector and cable topology.
- [ ] Establish voltage levels before attaching logic equipment.
- [ ] Document protection, grounding, and current-limiting assumptions.
- [ ] Select a non-invasive capture method.
- [ ] Record idle behavior, startup behavior, clock ownership, packet boundaries, and timing.
- [ ] Preserve raw captures and manifests.
- [ ] Compare observations with prior art without forcing a match.

Exit criterion: at least one project-generated capture is reproducible, hashed, and documented.

## Phase 4: Independent analysis tooling

- [ ] Build generic capture normalization and inspection tools.
- [ ] Implement a parser only for behavior supported by evidence.
- [ ] Add fixtures derived from project-generated or redistributable captures.
- [ ] Keep physical, framing, transport, command, and application layers separate.
- [ ] Add tests for every promoted protocol claim.

Exit criterion: analysis results can be regenerated from preserved inputs.

## Phase 5: Active implementation

Potential targets, selected only after evidence review:

- Game Boy test ROM
- microcontroller bridge
- PC-side protocol tool
- sewing-pattern visualization
- hardware-in-the-loop test harness

Before implementation, document whether each component is independent, adapted, or copied and record all license obligations.
