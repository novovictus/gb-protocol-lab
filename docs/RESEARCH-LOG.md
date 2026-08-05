# Research Log

This file is chronological. Detailed experiments live under `docs/experiments/` and are linked from the relevant date.

## 2026-03-07

- Archived Shonumi's Singer IZEK / Jaguar reverse-engineering article.
- Snapshot:
  <https://web.archive.org/web/20260307065209/https://shonumi.github.io/articles/art22.html>

Classification: `prior-art preservation`.

## Historical work, exact dates pending recovery

### OSCR bring-up and dump validation

- OSCR was assembled.
- Game Boy ROM dumping succeeded.
- Game Boy save dumping succeeded.
- Output was validated in an emulator.

Classification: `observed/reported`.

See: `experiments/EXP-20260804-001-oscr-dump-validation.md`.

### Singer IZEK powered bring-up

- A replacement foot controller was obtained.
- Basic powered sewing-machine functionality was observed.
- Correct threading, bobbin, spool, and stitch formation remained unknown.
- The physical validation sequence was explicitly set as: prove ordinary sewing first, then test intended Game Boy hardware or a justified facsimile, then instrument communication.

Classification: `observed/reported` plus `decision`.

See: `experiments/EXP-20260804-002-izek-powered-bringup.md`.

### Cartridge compatibility and software classification

- Original Game Boy hardware was selected as the behavioral baseline.
- EZ-Flash Jr reportedly worked on original hardware after firmware update and failed on FPGA GBC.
- Deterministic MBC5 flash targets were selected for machine tests and redump verification.
- The canonical matrix classified `Raku x Raku - Mishin` as the base machine-control path.
- Kirby and related titles were moved to the embroidery-unit path rather than treated as simple link failures.
- Game Boy Pocket behavior for CGB-only software was retained as expected negative-control behavior.
- DS R4 Pokemon deployment was recognized as a separate project thread.

Classification: `observed/reported` and `decision`.

## 2026-08-04

- Created or normalized `gb-protocol-lab` as a protocol-focused engineering notebook.
- Recorded Shonumi's article and GBE+ as prior art.
- Established requirements to distinguish observation, inference, prior art, code-derived findings, and historical reports.
- Reconciled repository status with retained bench history.
- Kept protocol code deferred pending machine validation, intended-hardware tests, and project-generated capture evidence.

Classification: `repository-state`.

## Entry template

### YYYY-MM-DD

- **Objective:**
- **Experiment IDs:**
- **Evidence IDs:**
- **Hardware IDs:**
- **Work performed:**
- **Observed results:**
- **Interpretation:**
- **Artifacts and hashes:**
- **Prior-art references:**
- **Open questions:**
- **Next action:**
