# Historical Reconstruction

This document imports project history that existed in conversation and external working notes before the repository became the canonical notebook.

## Status of reconstructed entries

Unless a linked artifact is present, reconstructed bench results are labeled `observed/reported`. This means the operator reported a direct observation, but the repository does not yet contain enough primary material to audit the result.

Reconstruction must not silently convert memory into measurement. Exact dates, hardware revisions, firmware versions, filenames, hashes, photographs, and logs should be added when recovered.

## Reconstructed sequence

### Prior-art discovery and preservation

- Shonumi's Singer IZEK / Jaguar JN reverse-engineering article was discovered.
- The work was recognized as substantial prior art rather than treated as a new project discovery.
- A stable Internet Archive snapshot was created or retained at:
  `https://web.archive.org/web/20260307065209/https://shonumi.github.io/articles/art22.html`
- Future reverse engineering and implementation were explicitly required to attribute Shonumi and distinguish new observations from prior work.

Classification: `prior-art preservation`.

### OSCR acquisition and validation

- OSCR was assembled.
- Game Boy ROM dumping succeeded.
- Game Boy save dumping succeeded.
- Output was validated in an emulator.

Classification: `observed/reported`.

Limits:

- exact OSCR hardware revision is not recorded here;
- firmware and host software versions are not recorded here;
- cartridge identity and dump hashes are not recorded here;
- emulator name, version, and validation procedure are not recorded here;
- emulator success confirms usability of the tested output, not necessarily a perfect dump of every inaccessible or unused byte.

### Singer IZEK physical bring-up

- The machine was acquired without a working foot controller in hand.
- A replacement foot controller was obtained from Amazon.
- The controller powered the machine and basic sewing-machine motion was observed.
- The operator did not yet know the threading path or required bobbin/spool consumables.
- The next physical goal was to confirm that the machine could form an actual stitch before treating it as a trustworthy protocol endpoint.

Classification: `observed/reported`.

Limits:

- no threaded stitch is claimed;
- no under-load sewing test is claimed;
- no electrical characterization of the replacement controller is claimed;
- no service, lubrication, timing, feed, or tension inspection is claimed.

### Cartridge and software path

Project history retained a distinction between native Game Boy work and unrelated DS/R4 deployment:

- DS R4 testing was considered for a separate Pokemon game deployment and is not part of the IZEK protocol baseline.
- A GBA flash cart is not automatically equivalent to native GB/GBC cartridge execution or the classic Game Boy link interface.
- Original Game Boy hardware was selected as the baseline for IZEK testing.
- EZ-Flash Jr compatibility differed between original hardware and an FPGA GBC.
- Deterministic single-image rewritable carts were preferred for machine testing and redump verification.

Classification: mixture of `decision` and `observed/reported`.

### Software compatibility matrix

A canonical external workbook was retained under the name:

`izek_test_matrix_canonical_saved_2026-05-03.xlsx`

The retained classifications included:

- EZ-Flash Jr sweep results;
- a translation key;
- Kirby reclassified as requiring the embroidery unit rather than representing a link failure;
- `Raku x Raku - Mishin` identified as the key base sewing-machine control ROM;
- Game Boy Pocket results for CGB-only software treated as expected negative controls.

Classification: `observed/reported` until the workbook is imported or linked with a hash.

## Reconciliation rules

When primary artifacts are recovered:

1. preserve this reconstruction rather than rewriting history invisibly;
2. add the artifact and hash to the evidence register;
3. create a dated experiment record;
4. promote only the supported portion from `observed/reported` to `observed`;
5. retain discrepancies and superseded interpretations explicitly.
