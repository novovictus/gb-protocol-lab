# Status Addendum: Later Reconstructed Work

Recorded: 2026-08-04

This addendum supplements `STATUS.md` without silently replacing its existing claim boundaries.

## Additional observed/reported results

- A Singer/IZEK software image was written to and redumped from a FunnyPlaying EverSave GB/GBC Flash Cart Pro.
- `Jaguar Mishin Sashi Senyou Soft - Kirby Family (Japan) (Proto)` was written to and redumped from an InsideGadgets MBC5 2 MiB / 32 KiB FRAM cartridge.
- The reported successful InsideGadgets path used OSCR `CFI Repro` with `WE=WR` and an M29F160F device.
- The generic `29F Repro` path was not the successful configuration.

These entries remain `observed/reported` until primary logs, hashes, hardware photographs, and exact versions are committed.

## Revised immediate priorities

1. Reproduce the InsideGadgets write/redump with full transcript and hashes.
2. Reproduce the FunnyPlaying write/redump with full transcript and hashes.
3. Boot each exact redumped image on original hardware and record the result.
4. Test a selected deterministic cartridge with the physical IZEK and record machine prompts and behavior.
5. Complete a basic threaded-stitch validation independent of Game Boy communication.
6. Map Shonumi article claims and GBE+ code-derived behavior into claim-level evidence records.
7. Build and validate a protected passive link breakout before active emulation or replay.
