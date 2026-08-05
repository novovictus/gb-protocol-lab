# Project Status

Last updated: 2026-08-04

## Phase

Initial repository framing, prior-art review, and evidence preservation.

## Active research target

Singer IZEK / Jaguar JN Game Boy sewing-machine interface.

Known related systems include:

- Singer IZEK 1500
- Jaguar JN-100
- Jaguar JN-2000

## Confirmed resources

- Public reverse-engineering article by Shonumi.
- Archived snapshot of that article.
- Public GBE+ source containing sewing-machine support.
- OSCR cartridge-dumping hardware.
- Physical Game Boy and cartridge hardware suitable for future experiments.

## Confirmed findings

At this stage, the following are confirmed as prior art rather than independent findings:

- A protocol-level reverse-engineering effort has already been published by Shonumi.
- GBE+ implements emulated support for the Singer IZEK 1500 and related Jaguar machines.
- The implementation appears to include a sewing-machine-specific serial state model, buffers, status handling, and coordinate or stitch processing.

## Not yet established independently

- Electrical signaling characteristics on owned hardware.
- Exact pinout and cable wiring for the available hardware.
- Packet captures produced by this project.
- Reproduction of the documented handshake or command flow.
- Independent coordinate or stitch decoding.
- Compatibility differences among IZEK 1500, JN-100, and JN-2000.
- A standalone host, embedded, or Game Boy-side implementation.

## Immediate next steps

1. Inventory all physical hardware, cartridges, cables, adapters, and dumping tools.
2. Record identifying labels, board revisions, cartridge hashes, and photographs.
3. Dump relevant cartridges with OSCR and document the procedure and hashes.
4. Review Shonumi's article and GBE+ implementation in parallel.
5. Produce a protocol evidence table separating prior art, code-derived inference, and independent observation.
6. Identify a safe capture method before connecting test equipment.
7. Establish a chronological research log before active protocol experiments.
