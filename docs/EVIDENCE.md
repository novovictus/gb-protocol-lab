# Evidence Register

This register indexes technical claims and supporting material. Conversation-derived bench history remains `observed/reported` until primary artifacts are attached.

## Evidence records

| Evidence ID | Date | Class | Subject | Source or experiment | Status | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| EVD-20260307-001 | 2026-03-07 | prior-art | Shonumi article preservation | Internet Archive snapshot listed in `REFERENCES.md` | recorded | Stable archive exists; article claims still require itemized extraction |
| EVD-20260804-001 | 2026-08-04 | prior-art | GBE+ sewing-machine support | GBE+ repository listed in `REFERENCES.md` | unreviewed | Pin commit, source paths, symbols, behavior, and license notices |
| EVD-20260804-002 | 2026-08-04 | project-state | Repository baseline | Upstream `main` tree reviewed 2026-08-04 | observed | Evidence-oriented structure exists; no captures or implementations are committed |
| EVD-20260804-003 | date not recovered | observed/reported | OSCR assembled | Historical reconstruction; EXP-20260804-001 | pending artifacts | Record PCB revision, firmware, photographs, and build notes |
| EVD-20260804-004 | date not recovered | observed/reported | Game Boy ROM dumping works | Historical reconstruction; EXP-20260804-001 | pending artifacts | Record source cart metadata, command log, byte length, hashes, and redump comparison |
| EVD-20260804-005 | date not recovered | observed/reported | Game Boy save dumping works | Historical reconstruction; EXP-20260804-001 | pending artifacts | Record save type, command log, byte length, and hashes |
| EVD-20260804-006 | date not recovered | observed/reported | Dump validated in emulator | Historical reconstruction; EXP-20260804-001 | pending artifacts | Record emulator/version, launch procedure, observed behavior, and screenshot/video |
| EVD-20260804-007 | date not recovered | observed/reported | Replacement foot controller operates IZEK | Historical reconstruction; EXP-20260804-002 | pending artifacts | Basic powered motion only; stitch formation not established |
| EVD-20260804-008 | 2026-05-03 filename date | observed/reported | Canonical IZEK compatibility matrix | `izek_test_matrix_canonical_saved_2026-05-03.xlsx` retained outside repository | not imported | Add workbook hash or export a redistribution-safe CSV/Markdown derivative |

## Claim register

| Claim ID | Claim | Class | Evidence | Confidence | Status |
| --- | --- | --- | --- | --- | --- |
| CLM-001 | Prior reverse-engineering work concerning the target interface exists and is attributed to Shonumi. | prior-art | EVD-20260307-001 | high | recorded |
| CLM-002 | The repository does not yet contain an independent IZEK protocol capture or implementation. | observed | EVD-20260804-002 | high | current |
| CLM-003 | The project has a working OSCR-based Game Boy ROM dumping path. | observed/reported | EVD-20260804-003, EVD-20260804-004 | medium | awaiting artifacts |
| CLM-004 | The project has a working OSCR-based Game Boy save dumping path. | observed/reported | EVD-20260804-003, EVD-20260804-005 | medium | awaiting artifacts |
| CLM-005 | At least one dumped software/save workflow produced usable emulator output. | observed/reported | EVD-20260804-006 | medium | awaiting artifacts |
| CLM-006 | The Singer IZEK can be powered and mechanically actuated with the acquired replacement foot controller. | observed/reported | EVD-20260804-007 | medium | awaiting artifacts |
| CLM-007 | The Singer IZEK has been proven to form a valid threaded stitch. | unverified | none | low | not established |
| CLM-008 | Flash-cart software has been proven to communicate with the physical IZEK. | unverified | none | low | not established |
| CLM-009 | The project has independently verified Shonumi's protocol findings. | unverified | none | low | not established |

## Addition template

### EVD-YYYYMMDD-NNN

- **Date:**
- **Class:** observed / observed-reported / reproduced / inferred / prior-art / code-derived / unverified
- **Subject:**
- **Source or experiment:**
- **Artifact paths:**
- **SHA-256:**
- **Finding:**
- **Limitations:**
- **Related claims:**
- **Redistribution status:**
- **Notes:**

### CLM-NNN

- **Claim:**
- **Class:**
- **Evidence IDs:**
- **Confidence:** low / medium / high
- **Alternatives:**
- **Falsification test:**
- **Status:** active / superseded / withdrawn
