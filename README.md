# Game Boy Protocol Lab

An engineering notebook for preservation, measurement, and reverse engineering of Game Boy communication protocols, peripherals, cartridges, and undocumented hardware behavior.

The initial research target is the Singer IZEK / Jaguar JN sewing-machine interface. The repository is intentionally structured around evidence and reproducibility rather than a finished software product.

## Current phase

The project has progressed beyond repository setup:

- OSCR hardware has been built.
- Game Boy ROM dumping works.
- Game Boy save dumping works.
- At least one dump was validated by successful use in an emulator.
- A replacement foot controller has powered the Singer IZEK and produced basic sewing-machine motion.

These results are retained from project history as `observed/reported`. Raw dump logs, hashes, photographs, exact hardware revisions, and a dated sewing test record are still required before the notebook can promote them to fully artifact-backed observations.

The machine has not yet been documented producing a valid threaded stitch. No independent protocol capture, decoded command stream, replay, or replacement endpoint is claimed.

See:

- [Project status](docs/STATUS.md)
- [Historical reconstruction](docs/HISTORICAL-RECONSTRUCTION.md)
- [Research methodology](docs/METHODOLOGY.md)
- [Evidence register](docs/EVIDENCE.md)
- [Evidence and claim matrix](docs/EVIDENCE-MATRIX.md)
- [References and prior art](docs/REFERENCES.md)
- [Roadmap](docs/ROADMAP.md)
- [Research log](docs/RESEARCH-LOG.md)

## Research standard

Every technical claim should identify its basis:

| Label | Meaning |
| --- | --- |
| `observed` | Directly measured or recorded by this project with supporting artifacts |
| `observed/reported` | Direct bench result retained from project history but not yet backed by repository artifacts |
| `reproduced` | Prior behavior independently repeated by this project |
| `inferred` | Conclusion drawn from evidence but not directly observed |
| `prior-art` | Reported by an external source |
| `code-derived` | Determined by reading an existing implementation |
| `unverified` | Plausible but not yet supported adequately |
| `superseded` | Retained for history but replaced by stronger evidence |

Claims should reference an evidence ID, experiment ID, source citation, artifact hash, or reproducible procedure.

## Claim boundary

The project currently supports a cartridge acquisition and execution workflow, but not an independently verified IZEK protocol implementation.

Established project capabilities do not by themselves prove:

- the IZEK link connector pinout;
- voltage levels or electrical direction;
- serial clock ownership;
- packet framing or command semantics;
- coordinate, stitch, or pattern encoding;
- behavioral equivalence among Singer IZEK 1500, Jaguar JN-100, and Jaguar JN-2000;
- compatibility of a flash cart with the physical sewing machine.

## Repository layout

```text
docs/          Status, methodology, evidence, references, history, and experiments
captures/      Raw and processed communication captures
hardware/      Hardware inventory, pinouts, fixtures, and test configurations
tools/         Host-side analysis, conversion, and capture utilities
firmware/      Embedded or target-side implementations
artifacts/     Reproducible outputs, manifests, hashes, and distributable evidence
```

Each experimental session should receive a stable identifier such as `EXP-YYYYMMDD-001`. Evidence records use `EVD-YYYYMMDD-001`. Hardware inventory records use `HW-###`.

## Provenance and attribution

Research derived from or informed by Shonumi's Singer IZEK / Jaguar JN work must be attributed explicitly.

GBE+ is GPLv2-licensed. Directly copied or adapted GBE+ code must retain applicable notices and comply with that license. A clean-room or independently written implementation should still document the prior art that informed the research and must not present established findings as original discoveries.

No repository-wide software license has been selected yet. Do not add third-party code until its source and license are recorded.

## Artifact policy

Do not commit copyrighted commercial ROM images, proprietary firmware, private keys, credentials, or material without clear redistribution permission.

For non-redistributable inputs, commit metadata where lawful and useful:

- acquisition or dumping procedure;
- tool and version;
- hardware identity;
- date and operator;
- byte length;
- cryptographic hashes;
- photographs or excerpts only when redistribution is permitted;
- relationships between source inputs and generated artifacts.

Large captures should be stored externally or through an appropriate large-file mechanism, with manifests and hashes retained here.

## Scope

This repository supports preservation, interoperability, repair, research, and documentation. It is not a ROM distribution project and it does not currently claim a complete protocol specification or working replacement interface.
