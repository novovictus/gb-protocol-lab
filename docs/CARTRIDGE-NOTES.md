# Cartridge and ROM Notes

No commercial ROM image belongs in this repository. Record metadata, hashes, tool output, screenshots, and independently produced patches only when redistribution is lawful.

## Development cartridge decision

The selected deterministic writable target is:

- InsideGadgets Game Boy MBC5 flash cartridge;
- 2 MiB ROM capacity;
- 32 KiB FRAM;
- ultra-low-power variant.

Reasoning:

- MBC5 covers the known sewing-software cartridge profiles retained in project history;
- 2 MiB capacity covers the current non-excluded target set;
- FRAM avoids coin-cell maintenance and preserves state without battery-backed SRAM;
- a single-image rewritable cart behaves more like a conventional cartridge than an SD menu loader and can be written/redumped by OSCR;
- the 32 KiB FRAM capacity is larger than the 8 KiB declared by several target headers, but software that follows its own header/banking expectations should leave the additional capacity unused. This must still be validated per image.

## Singer operation software record

Filename retained in project history:

`Sewing Machine Operation Software (USA) (En,Fr,Es) (GB Compatible).gbc`

Recorded header interpretation:

| Field | Recorded value | Meaning |
|---|---:|---|
| CGB flag (`0x0143`) | `0x80` | CGB-enhanced / backward compatible |
| cartridge type (`0x0147`) | `0x1B` | MBC5 + RAM + battery |
| ROM size (`0x0148`) | `0x05` | 1 MiB |
| RAM size (`0x0149`) | `0x02` | 8 KiB |
| destination (`0x014A`) | `0x01` | non-Japanese |

Status: **reported**, not yet backed by a committed generated header report in this repository.

Required follow-up:

1. generate a machine-readable header report from the preserved image;
2. record SHA-256, SHA-1, and file size;
3. record the analysis tool and version;
4. flash to the InsideGadgets cart;
5. redump and compare the programmed ROM region byte-for-byte;
6. preserve only the report and hashes publicly.

## Japanese sewing-software classification retained from prior work

| Title | Current classification | Evidence state |
|---|---|---|
| `Raku x Raku - Mishin` | base sewing-machine control software | reported |
| `Jaguar Mishin Sashi Senyou Soft - Kirby Family (Japan) (Proto)` | embroidery/design-family path | reported; flash/redump success also reported |
| `Mario Family` | embroidery/design-family path | reported |
| `Raku x Raku - Cut Shuu` | embroidery-unit path | reported |
| `Raku x Raku - Moji` | embroidery-unit path | reported |

Game Boy Pocket results for CGB-only titles should be recorded as negative controls, not cartridge failures, when the header explicitly requires CGB hardware.

## SRAM and FRAM terminology

Original MBC5 + RAM + battery cartridges generally use volatile SRAM held by a coin cell. Modern FRAM replacement carts provide non-volatile save storage without a battery. FRAM is a development convenience and reliability improvement; it should not be described as proof that an original cartridge used FRAM.
