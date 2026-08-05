# Research Methodology

## Purpose

This document defines how observations, claims, artifacts, and prior art are recorded. It is intended to prevent retrospective reconstruction, accidental overclaiming, and loss of provenance.

## Identifier scheme

Use stable identifiers:

- Experiments: `EXP-YYYYMMDD-NNN`
- Evidence records: `EVD-YYYYMMDD-NNN`
- Hardware items: `HW-NNN`
- Software or tool environments: `ENV-NNN`
- Claims: `CLM-NNN`

Identifiers are never reused. A corrected record references and supersedes the earlier record.

## Claim classes

### observed

Directly recorded by this project through a measurement, dump, photograph, trace, or repeatable software output.

Minimum support:

- experiment ID;
- setup and procedure;
- raw or source artifact;
- artifact hash;
- result statement;
- known limitations.

### reproduced

A result described in prior art that this project independently repeated.

Minimum support:

- original source;
- independent experiment ID;
- comparison criteria;
- raw evidence;
- discrepancies.

### inferred

A conclusion supported by evidence but not directly measured.

Minimum support:

- referenced evidence IDs;
- reasoning summary;
- alternative explanations;
- confidence level;
- proposed falsification test.

### prior-art

A claim attributed to an external publication, repository, manual, or other source.

Minimum support:

- source citation;
- access date;
- archived reference when available;
- precise location within the source;
- no wording that implies independent discovery.

### code-derived

A behavioral statement determined by inspecting an existing implementation.

Minimum support:

- repository and revision;
- file and symbol or line range;
- license;
- explanation of whether code was merely inspected, adapted, or copied.

### unverified

A working hypothesis or reported fact that has not been supported adequately.

It must not be used as an established premise without explicit qualification.

## Experimental record

Create one Markdown record per experiment under `docs/experiments/`.

Record before execution:

- objective;
- hypothesis;
- equipment and identifiers;
- software versions;
- wiring or topology;
- safety constraints;
- planned procedure;
- expected artifacts.

Record after execution:

- actual procedure and deviations;
- timestamps;
- observations;
- raw artifact locations and hashes;
- interpretation;
- confidence;
- failures and anomalies;
- open questions;
- next experiment.

Do not silently edit an old result to match a later understanding. Add a dated correction or superseding record.

## Artifact integrity

Preferred hashes:

- SHA-256 for all files;
- SHA-1 or CRC values only when required for comparison with an established database.

A manifest should include:

```text
artifact path
byte length
SHA-256
creation or acquisition date
producing experiment
tool and version
redistribution status
notes
```

Raw artifacts should remain immutable. Derived artifacts must identify their source artifacts and transformation steps.

## Cartridge dumping

For each dump attempt, record:

- cartridge label and inventory ID;
- PCB or board revision when visible;
- dumper hardware and firmware;
- software and version;
- connector cleaning or preparation;
- dump count;
- hashes for each dump;
- whether repeated dumps match byte-for-byte;
- any database comparison;
- whether the ROM image may be redistributed.

A single successful-looking dump is not sufficient to establish integrity when repeated dumping is practical.

## Protocol analysis

Separate these layers:

1. Physical layer: connector, voltage, direction, clock, idle state.
2. Framing: bit order, byte boundaries, packet boundaries, checksums.
3. Transport behavior: retries, acknowledgements, flow control, timing.
4. Command semantics: opcodes, fields, statuses, state transitions.
5. Application semantics: coordinates, stitches, patterns, machine actions.

Do not infer higher-layer semantics solely because bytes resemble a known implementation.

## Prior-art handling

Use archived references when available, but retain the original URL.

When recording Shonumi or GBE+ findings:

- label them `prior-art` or `code-derived`;
- cite exact locations;
- record repository revision for source inspection;
- distinguish article statements from emulator implementation choices;
- note when an implementation behavior may be an emulator abstraction rather than observed hardware behavior.

## Code implementation threshold

Do not implement a protocol component merely because prior-art code exists.

Before implementation, document:

- the specific behavior being implemented;
- its evidence basis;
- whether the design is independent or adapted;
- applicable license obligations;
- test fixtures;
- unresolved assumptions.

Implementation may begin earlier for tooling that preserves evidence, validates hashes, parses generic captures, or automates reproducible procedures.
