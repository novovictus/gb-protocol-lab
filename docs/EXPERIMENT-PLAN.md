# Experiment Plan

The goal is not to jump directly to a Flipper application. The first goal is a defensible chain from known software and hardware state to a captured, reproducible exchange.

## Stage 0: Machine intake and safety

Determine whether the Singer unit is mechanically and electrically suitable for testing. Record labels, connector photographs, mechanical movement, visible damage, power-on behavior, and foot-controller connector measurements. Do not energize improvised pedal circuitry until the connector, resistance range, and circuit role are established.

## Stage 1: Software and cartridge baseline

Use one identified original Game Boy Color, the InsideGadgets MBC5 FRAM cart, one exact ROM hash, and OSCR write/redump verification. Record hardware identifiers, tool versions, source hashes, programmed-cart redump hashes, compare results, and missing-device messages. Treat the FPGA GBC only as a comparison platform.

## Stage 2: Passive electrical characterization

Measure idle voltage, continuity, endpoint power, clock activity and ownership, data direction, startup duration, and approximate bit rate. Begin with an ordinary multi-channel logic analyzer; escalate to an oscilloscope only when thresholds, ringing, contention, or rise time are ambiguous.

## Stage 3: Controlled capture matrix

| Capture ID | Machine state | Software action | Expected value |
|---|---|---|---|
| C00 | disconnected | ROM boot | Software-only control |
| C01 | connected, machine off | ROM boot | Passive cable/device effects |
| C02 | connected, machine on | ROM boot | Startup/handshake candidate |
| C03 | connected, idle | no input | Idle polling/state traffic |
| C04 | connected | one menu action | Small command delta |
| C05 | connected | select one simple stitch/pattern | Data-transfer candidate |
| C06 | connected and mechanically safe | initiate then stop | Execution-state candidate |

Every capture requires sidecar metadata.

## Stage 4: Decode without implementation

Reconstruct bytes from clocked edges, preserve direction and timing, identify repeated sequences before assigning meanings, compare repeated and one-variable captures, and label agreement with prior work as corroboration rather than new discovery.

## Stage 5: Minimum active reproduction

Attempt the smallest harmless exchange that produces an observable response: replay an idle/status transaction, emulate only the endpoint required for a software state change, validate on original Game Boy hardware, and only then test a Flipper Zero or microcontroller implementation.

## Escalation criteria

Use higher-end equipment only for a recorded threshold, edge-quality, contention, capture-depth, trigger, jitter, or timing-resolution problem. Tool prestige alone is not an escalation criterion.
