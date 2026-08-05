# Provenance and Attribution Policy

## Claim sources

Each note, table row, protocol field, or implementation decision should identify its source class.

- **Observed:** directly produced by project-controlled hardware or artifacts, with setup, date, operator, tool versions, raw output, and artifact identifiers.
- **Reproduced:** an observed result repeated under recorded conditions, including what changed and how equivalence was assessed.
- **Prior art:** published externally or present in another implementation, with author, title, URL/archive, repository, license, commit, and source path where applicable.
- **Inferred:** a conclusion derived from evidence, with supporting sources and a falsification test.
- **Reported:** retained from prior project conversation or notebook state but not yet connected to a primary repository artifact.
- **Unverified:** a working possibility that must not be treated as a design requirement.

## Artifact rules

Every committed capture, photograph set, generated report, or binary-derived metadata record should include an artifact ID, date/timezone, operator, hardware identifiers, tool versions, procedure, SHA-256, redistribution status, related notebook entry, and interpretation separated from raw results.

Use [templates/artifact-metadata.md](templates/artifact-metadata.md).

## External code

GBE+ is GPLv2. Copying or adapting code invokes its license obligations. Reading an implementation still requires attribution. Independent implementation work should identify which protocol facts were already known and which were independently confirmed. Do not use `clean room` casually; record who reviewed prior code and what information crossed into implementation.

## ROM and proprietary-data handling

Do not commit commercial ROM images or extracted proprietary design content. Public evidence may include filenames, hashes, header fields, mapper and memory metadata, independently generated screenshots where appropriate, lawful patches, and project-generated protocol captures subject to review.

## Language standard

Avoid `discovered` for prior-art facts, `confirmed` for conversation-only records, `works` without a tested function, `compatible` without a hardware/firmware/procedure matrix, and `protocol decoded` when only repeated bytes have been identified.
