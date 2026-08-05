# References and Prior Art

This file records external work that informs the project. Inclusion does not imply independent reproduction.

## Citation requirements

For each source, record where practical:

- author or project;
- title;
- original URL;
- archived URL;
- access date;
- publication or revision date;
- repository commit or tag;
- license;
- exact section, file, symbol, or line range used;
- how the source informed this project;
- independent reproduction status.

## Shonumi: Singer IZEK / Jaguar reverse engineering

Original article:

<https://shonumi.github.io/articles/art22.html>

Archived snapshot:

<https://web.archive.org/web/20260307065209/https://shonumi.github.io/articles/art22.html>

Archive timestamp: 2026-03-07 06:52:09 UTC.

Recommended general attribution:

> This work builds on prior reverse engineering by Shonumi concerning the Singer IZEK and Jaguar JN Game Boy sewing-machine interface.

Protocol details from the article should be entered individually in the evidence register within `docs/NOTEBOOK.md` with precise section references. Do not imply that established findings were first discovered by this project.

Current project use:

- background prior art for IZEK/Jaguar Game Boy communication;
- claim-boundary guidance;
- future comparison target for project-generated captures.

Independent reproduction status:

- not yet independently reproduced by committed project capture evidence.

## GBE+

Repository:

<https://github.com/shonumi/gbe-plus>

Known repository-level relevance recorded by this project:

- sewing-machine-related support exists;
- the current notebook associates that support with Singer IZEK 1500, Jaguar JN-100, and Jaguar JN-2000.

Before relying on implementation details, record:

- inspected commit SHA;
- files and symbols;
- applicable license notice;
- whether the finding is an emulator design choice, article-derived behavior, or behavior tied to hardware evidence;
- exact claim extracted into the evidence register in `docs/NOTEBOOK.md`.

GBE+ is GPLv2-licensed. Direct copying or adaptation carries GPL obligations. Independent implementation should still acknowledge the source of prior knowledge.

## OSCR / sanni Cart Reader

Repository:

<https://github.com/sanni/cartreader>

Project relevance:

- OSCR is the reported ROM/save dumping and flash-cart write/redump tool.
- For the InsideGadgets MBC5 2 MiB / 32 KiB FRAM cart, the reported successful path was `CFI Repro` with `WE=WR` and M29F160F-compatible behavior.
- Generic `29F Repro` was not the successful reported path for that cartridge.

Independent status:

- write/redump success is currently `observed/reported` until logs, firmware version, hashes, and photographs are committed.

## InsideGadgets MBC5 2 MiB / 32 KiB FRAM cart

Project relevance:

- preferred deterministic development cartridge for single-image machine tests;
- reported successful Kirby Family write and redump;
- reported successful OSCR path: `CFI Repro`, `WE=WR`;
- M29F160F-compatible behavior was the relevant flash workflow.

Needed references:

- product page archive;
- board revision and flash/RAM markings from the received cart;
- OSCR log.

## FunnyPlaying EverSave GB/GBC Flash Cart Pro

Project relevance:

- secondary deterministic rewritable target;
- reported successful Singer/IZEK write and redump;
- treated as an MBC5-class single-ROM flash cart, not an SD menu loader.

Needed references:

- product page archive;
- cart revision and board/chip markings;
- OSCR log and source/redump hashes.

## Source review template

### Source ID

- **Author/project:**
- **Title:**
- **Original URL:**
- **Archived URL:**
- **Accessed:**
- **Revision/commit:**
- **License:**
- **Relevant locations:**
- **Claims extracted:**
- **How used:**
- **Independent reproduction status:**
