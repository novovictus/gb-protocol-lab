# Notebook Update: Reconstructed Work Since Initial Setup

Date recorded: 2026-08-04

## Purpose

This document captures later project details reconstructed from prior working conversations. It is not a substitute for primary bench artifacts. Unless an artifact is later attached and linked, the entries below remain `observed/reported`.

## Reconstructed bench results

### OSCR acquisition workflow

The project history reports that:

- OSCR hardware was assembled and operated successfully;
- Game Boy ROM reads completed successfully;
- Game Boy save reads completed successfully;
- at least one dumped ROM/save workflow was exercised in an emulator;
- repeated reads and hashes were not preserved in the current repository record.

These results establish a working acquisition path, not protocol behavior.

### Rewritable cartridge workflow

Two distinct write/redump paths were reported:

1. A Singer/IZEK software image was written to a FunnyPlaying EverSave GB/GBC Flash Cart Pro and subsequently redumped.
2. `Jaguar Mishin Sashi Senyou Soft - Kirby Family (Japan) (Proto)` was written to an InsideGadgets MBC5 2 MiB / 32 KiB FRAM cartridge and subsequently redumped.

For the InsideGadgets cartridge, OSCR reportedly succeeded using:

- cartridge type: `CFI Repro`;
- write-enable selection: `WE=WR`;
- flash device behavior consistent with an M29F160F device;
- the generic `29F Repro` path did not provide the successful write path.

The exact OSCR revision, firmware revision, host software version, command transcript, source-image hash, and redump hash remain unrecorded here.

### Diagnostic interpretation retained from the work

During initial handling of the blank or uninitialized rewritable cartridge:

- `HEADER CHECKSUM ERROR` was treated as compatible with a blank or uninitialized image and was not, by itself, considered the blocking fault;
- `Flash ID: 0101 / Unknown flashrom` was treated as the operative blocker until the CFI-based path was selected.

This interpretation is retained as `inferred from observed/reported tool behavior`. It should be reproduced with complete OSCR output before being generalized.

## Cartridge execution strategy

The project selected deterministic native GB/GBC rewritable cartridges as the preferred path for intended-hardware testing. The rationale was to reduce variables introduced by SD-card loaders, menu firmware, battery-backed save storage, and compatibility layers.

Current reconstructed roles:

- **InsideGadgets MBC5 2 MiB / 32 KiB FRAM:** deterministic single-image test cartridge;
- **FunnyPlaying EverSave GB/GBC Flash Cart Pro:** secondary rewritable target with a successful reported write/redump;
- **EZ-Flash Jr:** convenience loader for original hardware, but not the preferred ground-truth cartridge path;
- **original cartridge:** preferred historical reference if acquired, but not currently recorded as present.

## DS flash-cart side work

A separate DS-family acquisition plan considered an Ace3DS+-compatible cart, EZ-Flash Parallel, and an RP2040-based DSPico cart. The intended arrangement was:

- provide a friend with a configured DS-family system from existing hardware inventory;
- use one stable cart as the friend's appliance;
- retain two carts for compatibility and implementation experiments.

This activity may inform general cartridge-development practice, but it is explicitly **out of scope as evidence for the classic Game Boy IZEK/Jaguar protocol**. DS flash-cart behavior must not be used to support claims about native GB/GBC cartridge bus timing, link-port signaling, or sewing-machine compatibility.

## Prior-art boundary

Shonumi's Singer IZEK/Jaguar work and GBE+ remain prior art. The existence of a published protocol analysis or emulator implementation does not make any protocol fact independently observed by this project.

For every imported technical statement, the notebook should record:

- source ID;
- archived and original URL where available;
- article section or repository commit/file/symbol;
- license;
- exact statement extracted;
- project reproduction status.

## Current evidence boundary

The reconstructed work supports these limited claims:

- the project has a functioning reported ROM/save acquisition workflow;
- the project has at least two reported rewritable-cartridge write/redump paths;
- the project has identified a specific OSCR CFI configuration that reportedly worked for the InsideGadgets cartridge;
- the Singer IZEK can be powered and can produce basic machine motion with a replacement controller.

It does not yet support independent claims about:

- IZEK connector pinout or voltage levels;
- clock ownership or serial direction;
- packet framing, commands, status values, or timing;
- stitch, coordinate, or pattern encoding;
- equivalence among IZEK and Jaguar machine models;
- successful formation of a threaded stitch;
- successful communication between a rewritten cartridge and the physical machine.

## Missing primary artifacts

Highest-value recovery items:

1. OSCR console logs for source reads, writes, and redumps.
2. SHA-256 hashes and byte lengths for each lawful-to-record image.
3. OSCR PCB, firmware, and host software versions.
4. Photographs of cartridge PCBs and flash markings.
5. Exact cart profiles and write-enable settings.
6. Emulator identity/version and validation notes.
7. Video or photographs of the powered Singer test.
8. A dated, repeatable basic stitch test.
9. A cartridge-to-machine execution record.
10. Passive electrical measurements and captures, after a protected breakout is documented.
