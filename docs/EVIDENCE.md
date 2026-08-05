# Evidence Register

This register is the index of technical claims and supporting material. It begins with repository-level facts only. Protocol details should be added after they are tied to precise sources or project-generated evidence.

## Evidence records

| Evidence ID | Date | Class | Subject | Source or experiment | Status | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| EVD-20260307-001 | 2026-03-07 | prior-art | Shonumi article preservation | Internet Archive snapshot listed in `REFERENCES.md` | recorded | Archive existence is recorded; article claims are not yet itemized here |
| EVD-20260804-001 | 2026-08-04 | prior-art | GBE+ sewing-machine support | GBE+ repository listed in `REFERENCES.md` | unreviewed | Exact revision, files, symbols, and behaviors remain to be mapped |
| EVD-20260804-002 | 2026-08-04 | project-state | Repository baseline | Current repository contents | observed | No captures, dumps, measurements, or implementations are present |

## Claim register

| Claim ID | Claim | Class | Evidence | Confidence | Status |
| --- | --- | --- | --- | --- | --- |
| CLM-001 | Prior reverse-engineering work concerning the target interface exists and is attributed to Shonumi. | prior-art | EVD-20260307-001 | high | recorded |
| CLM-002 | The project has not yet committed an independent protocol reproduction or validated hardware capture. | observed | EVD-20260804-002 | high | current |

## Addition template

### EVD-YYYYMMDD-NNN

- **Date:**
- **Class:** observed / reproduced / inferred / prior-art / code-derived / unverified
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
