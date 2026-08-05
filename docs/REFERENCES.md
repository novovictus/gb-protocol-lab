# References and Prior Art

This file records external work that informs the project. Inclusion does not imply independent reproduction.

## Shonumi: Singer IZEK / Jaguar reverse engineering

Original article:

<https://shonumi.github.io/articles/art22.html>

Archived snapshot:

<https://web.archive.org/web/20260307065209/https://shonumi.github.io/articles/art22.html>

Archive timestamp: 2026-03-07 06:52:09 UTC.

This work builds on prior reverse engineering by Shonumi concerning the Singer IZEK and Jaguar JN Game Boy sewing-machine interface.

Protocol details from the article do not imply that established findings were first discovered by this project.

Current project use:

- background prior art for IZEK/Jaguar Game Boy communication;
- claim-boundary guidance;
- future comparison target for project-generated captures.

## GBE+

Repository:

<https://github.com/shonumi/gbe-plus>

## OSCR / sanni Cart Reader

Repository:

<https://github.com/sanni/cartreader>

## InsideGadgets MBC5 2 MiB / 32 KiB FRAM cart

Project relevance:

- preferred deterministic development cartridge for single-image machine tests;
- reported successful Kirby Family write and redump;
- reported successful OSCR path: `CFI Repro`, `WE=WR`;
- M29F160F-compatible behavior was the relevant flash workflow.

## FunnyPlaying EverSave GB/GBC Flash Cart Pro

Project relevance:

- secondary deterministic rewritable target;
- reported successful Singer/IZEK write and redump;
- treated as an MBC5-class single-ROM flash cart, not an SD menu loader.
