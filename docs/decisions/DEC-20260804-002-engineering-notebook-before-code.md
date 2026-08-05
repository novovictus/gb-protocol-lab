# DEC-20260804-002: Establish the evidence notebook before implementing protocol code

## Status

Accepted.

## Context

Substantial Singer IZEK/Jaguar prior art already exists, including Shonumi's article and GBE+. Beginning with an implementation would risk importing undocumented assumptions, obscuring provenance, and overstating independent discovery.

## Decision

Before protocol implementation, the repository will:

1. inventory physical hardware and software versions;
2. preserve bench observations with stable experiment and evidence identifiers;
3. map prior-art claims to exact sources and licenses;
4. distinguish direct observations, reconstructed reports, inference, code-derived behavior, and prior art;
5. document unresolved questions and the measurement needed to answer each one;
6. collect a project-generated passive capture before claiming independent protocol reproduction.

## Implementation threshold

Code should be added when it answers a defined measured question, processes a preserved artifact, or reproduces a documented behavior. Code should not be added merely to create the appearance of progress.

## Consequences

The repository remains an engineering notebook rather than a finished product. Empty or lightly populated `tools/` and `firmware/` directories are acceptable until evidence creates a concrete implementation requirement.
