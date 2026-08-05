# Cartridge and ROM Notes

No commercial ROM image belongs in this repository. Record metadata, hashes, tool output, screenshots, and independently produced patches only when redistribution is lawful.

## Separation of cartridge paths

The project has discussed several cartridge classes. They are not interchangeable evidence:

- native GB/GBC flash cartridges are relevant to IZEK tests;
- a GBA flash cartridge may execute GBA software or use an emulation layer and is not automatically a native Game Boy link baseline;
- a DS R4 is part of a separate Pokemon deployment goal and is outside the IZEK protocol path.

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

Status: `decision` plus `observed/reported` successful use. Import flash/redump logs before treating the workflow as artifact-backed.

## Non-IZEK flash validation targets

Two homebrew or preservation-oriented images were discussed as convenient controlled targets for the same InsideGadgets cartridge:

- `Pokemon Picross` beta;
- `Grimace's Birthday`.

Retained project history reports that both images declare:

- cartridge type `0x1B` (`MBC5 + RAM + battery` in the standard header interpretation);
- 32 KiB external RAM.

This is currently `reported`, not artifact-backed. The earlier conclusion that the same 2 MiB MBC5 / 32 KiB FRAM cartridge should support both images is a compatibility inference from the reported headers and capacity, not a completed hardware result.

These images are useful as non-IZEK controls because they can exercise the ordinary flash, boot, save, redump, and hash workflow without implying anything about the sewing-machine protocol.

Required validation for each image:

1. record the lawful source and acquisition date;
2. record file size and SHA-256 without committing the ROM;
3. generate and preserve a machine-readable header report;
4. verify ROM size does not exceed the cartridge capacity;
5. flash with recorded OSCR hardware, firmware, and host-software versions;
6. redump the programmed cartridge and compare the used ROM region byte-for-byte;
7. boot on original GB/GBC hardware and record the exact console model;
8. exercise save creation and reload when supported;
9. redump save data and record size and hash;
10. treat success with either image only as validation of the cartridge workflow, not as evidence about IZEK electrical or protocol compatibility.

The cart is a single-image rewritable cartridge. Switching between these targets requires reflashing; it is not a multi-ROM menu cartridge.

## OSCR status

Retained project history states:

- OSCR is built;
- Game Boy ROM dumping works;
- Game Boy save dumping works;
- output was validated in an emulator.

Required normalization run:

1. identify OSCR PCB revision and firmware;
2. identify host software and version;
3. photograph the assembled unit and test cartridge;
4. dump ROM twice and compare hashes;
5. dump save twice when stable state is expected and compare hashes;
6. record emulator and version;
7. load the exact hashed outputs;
8. record what emulator behavior was observed;
9. commit logs and metadata, not restricted ROM/save content.

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

Status: `reported`, not yet backed by a committed generated header report.

Required follow-up:

1. generate a machine-readable header report from the preserved image;
2. record SHA-256, SHA-1, and file size;
3. record the analysis tool and version;
4. flash to the InsideGadgets cart;
5. redump and compare the programmed ROM region byte-for-byte;
6. preserve only the report and hashes publicly;
7. test boot on original Game Boy hardware;
8. test machine detection separately from ordinary ROM execution.

## Canonical compatibility matrix

A retained external workbook is named:

`izek_test_matrix_canonical_saved_2026-05-03.xlsx`

The workbook reportedly preserves:

- EZ-Flash Jr sweep results;
- a translation key;
- machine/control versus embroidery-unit classifications;
- platform-specific negative controls.

Import a redistribution-safe derivative and hash the source workbook.

## Japanese sewing-software classification retained from prior work

| Title | Current classification | Evidence state |
|---|---|---|
| `Raku x Raku - Mishin` | base sewing-machine control software | observed/reported via canonical matrix |
| `Jaguar Mishin Sashi Senyou Soft - Kirby Family (Japan) (Proto)` | embroidery/design-family path | observed/reported; flash/redump success also retained |
| `Mario Family` | embroidery/design-family path | observed/reported |
| `Raku x Raku - Cut Shuu` | embroidery-unit path | observed/reported |
| `Raku x Raku - Moji` | embroidery-unit path | observed/reported |

Game Boy Pocket results for CGB-only titles should be recorded as negative controls, not cartridge failures, when the header explicitly requires CGB hardware.

## SRAM and FRAM terminology

Original MBC5 + RAM + battery cartridges generally use volatile SRAM held by a coin cell. Modern FRAM replacement carts provide non-volatile save storage without a battery. FRAM is a development convenience and reliability improvement; it should not be described as proof that an original cartridge used FRAM.
