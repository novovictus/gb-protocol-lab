# DEC-20260804-001: Separate deterministic GB test cartridges from DS flash-cart experiments

## Status

Accepted in project history; recorded 2026-08-04.

## Context

The project needs a repeatable cartridge path for original GB/GBC hardware and the Singer IZEK. Separate DS-family flash carts were also considered for general experimentation and for preparing a system for a friend.

Combining these activities under one compatibility claim would create a false equivalence between DS flash-cart behavior and native GB/GBC cartridge or link behavior.

## Decision

For IZEK/Jaguar work:

- prefer deterministic native GB/GBC rewritable cartridges;
- use original Game Boy hardware as the behavioral baseline;
- record each cartridge revision, writer profile, firmware version, source hash, redump hash, and target result;
- treat menu-based or SD-backed carts as convenience devices unless separately validated for the specific machine path.

For DS-family work:

- retain Ace3DS+-compatible, EZ-Flash Parallel, and DSPico-class carts as a separate experimentation set if acquired;
- do not cite DS results as evidence for IZEK electrical or protocol claims;
- document any useful cross-platform tooling lessons as engineering practice, not protocol reproduction.

## Consequences

- The InsideGadgets and FunnyPlaying carts remain the principal reported native write/redump targets.
- EZ-Flash Jr remains useful for convenience comparison but is not automatically a reference implementation.
- DS flash-cart acquisition and compatibility work stays outside the IZEK evidence matrix unless a clearly scoped methodological claim is being made.
