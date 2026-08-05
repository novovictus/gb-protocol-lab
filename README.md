# Game Boy Protocol Lab

An engineering notebook for preservation, measurement, and reverse engineering of Game Boy communication protocols, peripherals, cartridges, and undocumented hardware behavior.

The initial research target is the Singer IZEK / Jaguar JN sewing-machine interface. The repository is intentionally structured around evidence and reproducibility rather than a finished software product.

## Current phase

The project is in repository setup, asset inventory, prior-art mapping, evidence preservation, and preparation for controlled hardware capture.

No independent protocol implementation, validated Singer/Jaguar communication capture, or confirmed hardware reproduction is claimed yet.

Retained project history records substantial pre-repository bench work, including OSCR validation, rewritable-cartridge flash/redump tests, target-ROM classification, acquisition of a Singer IZEK 1500, and selection of original Game Boy hardware as the current execution baseline. These records remain labeled `reported` until their primary artifacts are attached.

See:

- [Project status](docs/STATUS.md)
- [Research methodology](docs/METHODOLOGY.md)
- [Evidence register](docs/EVIDENCE.md)
- [Evidence and claim matrix](docs/EVIDENCE-MATRIX.md)
- [Hardware and tooling inventory](docs/HARDWARE-INVENTORY.md)
- [Cartridge and ROM notes](docs/CARTRIDGE-NOTES.md)
- [Experiment plan](docs/EXPERIMENT-PLAN.md)
- [Provenance policy](docs/PROVENANCE.md)
- [References and prior art](docs/REFERENCES.md)
- [Roadmap](docs/ROADMAP.md)
- [Research log](docs/RESEARCH-LOG.md)

## Research standard

Every technical claim should identify its basis:

| Label | Meaning |
| --- | --- |
| `observed` | Directly measured or recorded by this project |
| `reproduced` | Prior behavior independently repeated by this project |
| `reported` | Retained from earlier project work but not yet tied to a primary repository artifact |
| `inferred` | Conclusion drawn from evidence but not directly observed |
| `prior-art` | Reported by an external source |
| `code-derived` | Determined by reading an existing implementation |
| `unverified` | Plausible but not yet supported adequately |
| `superseded` | Retained for history but replaced by stronger evidence |

Claims should reference an evidence ID, experiment ID, source citation, artifact hash, or reproducible procedure.

## Repository layout

```text
docs/          Status, methodology, evidence register, references, and research log
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
