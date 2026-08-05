# Game Boy Protocol Lab

Research, documentation, and tooling for reverse engineering Game Boy communication protocols, peripherals, and undocumented hardware behavior.

## Purpose

This repository is an engineering notebook and implementation workspace for protocol-level investigation of the Game Boy ecosystem.

The initial focus is communication between Game Boy software and external hardware, beginning with the Singer IZEK / Jaguar JN sewing-machine family and its Game Boy interface. The scope may expand to related serial, cartridge, timing, peripheral, and hardware research as evidence accumulates.

## Current status

The repository is in the initial documentation, preservation, and evidence-gathering phase.

Known prior work has been identified:

- Shonumi published detailed reverse-engineering research covering the Singer IZEK and related Jaguar sewing-machine interface.
- Shonumi's GBE+ emulator includes support for the Singer IZEK 1500, Jaguar JN-100, and Jaguar JN-2000.
- A dated Internet Archive snapshot of the article was captured when the prior work was discovered.
- OSCR cartridge-dumping hardware and compatible cartridges are available for independent inspection and preservation work.
- Physical Game Boy and related hardware are available for future testing.

No independent protocol implementation, validated communication capture, or confirmed hardware reproduction is committed here yet.

See:

- [Current status](docs/STATUS.md)
- [References and prior art](docs/REFERENCES.md)
- [Roadmap](docs/ROADMAP.md)
- [Research log](docs/RESEARCH-LOG.md)

## Research standard

This project will explicitly distinguish:

- direct observation from physical hardware;
- independently reproduced behavior;
- inference based on captures, software, or documentation;
- prior published reverse engineering;
- code adapted from an existing implementation;
- unresolved hypotheses and open questions.

Claims should be supported by captures, measurements, source references, photographs, dumps, or reproducible procedures where possible.

## Repository layout

```text
docs/          Research notes, protocol documentation, status, and references
captures/      Raw and processed communication captures
hardware/      Hardware notes, pinouts, fixtures, and test configurations
tools/         Host-side analysis, conversion, and capture utilities
firmware/      Embedded or target-side implementations
artifacts/     Reproducible outputs and supporting evidence
```

## Attribution and licensing

Research derived from or informed by Shonumi's work must be attributed explicitly.

GBE+ is GPLv2-licensed. Directly copied or adapted GBE+ code must retain applicable notices and comply with that license. Independent implementations should document the prior work that informed them and avoid presenting established findings as original discoveries.

No repository-wide software license has been selected yet.

## Scope boundaries

This repository is intended for preservation, interoperability, repair, research, and documentation.

It is not intended to distribute copyrighted commercial ROM images, proprietary software, or other material without clear permission to redistribute.
