# Project Status

Last updated: 2026-08-05

## Phase

Engineering-notebook consolidation before code. Current work is end-to-end intended-hardware baseline documentation, deterministic cartridge workflow verification, mechanical restoration, compatibility-matrix reconstruction, source attribution, and passive-measurement planning.

Protocol implementation remains deferred.

## Current state

Repository facts from the current default branch:

- Canonical documentation exists under `README.md`, `docs/NOTEBOOK.md`, `docs/STATUS.md`, `docs/REFERENCES.md`, and `hardware/INVENTORY.md`.
- `artifacts/izek_test_matrix.xlsx` is committed with SHA-256 `fdb941a3a6936b61b20042d2fc8c103e78ca737df4389bdbfad5c45dccebd9e0`.
- A dated photo-backed evidence index is committed under `artifacts/2026-05-03-compatibility-evidence/`.
- The committed contact-sheet derivative has SHA-256 `631f990bdf22d4e80851b35b48505fd7c77c2358dbf695ec26bb4fced5e023ea`.
- The evidence manifest records SHA-256 hashes for all sixteen original source photos and identifies an alternate workbook revision with SHA-256 `a1bb3aa68c7cec801a31c387377345be2a513a7677a2c83d6f8c18c97cc86d9d`.
- The alternate workbook differs from the previously committed root workbook. Both identities are preserved; neither silently supersedes the other.
- No commercial ROM, proprietary firmware, physical-bus capture, or protocol implementation is committed.

Artifact-backed compatibility observations:

- Original GBA and original GBC visibly reached software prompt, machine-check, or embroidery-unit requirement screens for the tested titles.
- Game Boy Pocket visibly displayed the Game Boy Color-only rejection screen for the tested CGB-only titles.
- Original GBC and FP-GBC visibly reached different STOP/error states in the retained comparison images.
- These images establish screen states only. They do not establish completed upload, machine motion, stitch formation, electrical equivalence, timing equivalence, or the exact meaning of every screen.

Results retained as `observed/reported` unless later backed by committed evidence:

- OSCR was assembled; Game Boy ROM and save reads worked; at least one output was usable in an emulator.
- A replacement controller powered the Singer IZEK and produced machine motion.
- The feed-dog lift failure was traced to a broken notch on the mechanical slider that engages the cam. Manually positioning the slider restored engagement of the downstream mechanism.
- The installed needle used during initial bring-up was physically broken and unsuitable for a valid sewing test.
- The lower plastic drop-in bobbin case reportedly arrived with substantial prior needle-strike marks.
- Multiple reseating attempts reportedly did not prevent the bobbin case from shifting during automatic operation.
- Continued tests reportedly caused thread jams, bent or broken needles, and additional marring of the bobbin case.
- Under automatic operation, the bobbin case reportedly rotated approximately 10 degrees or more into the needle path and was struck by the needle.
- The immediate mechanical fault is therefore consistent with inadequate bobbin-case retention or seating. This does not establish whether the root cause is the case itself, the stopper or position bracket, retainer/race hardware, or timing/alignment.
- During the unresolved bring-up state, pressing sew reportedly caused the machine to accelerate, stop, and blink red at the switch or indicator.
- The Game Boy software displayed an error graphic pointing toward the upper area of the machine during the same general troubleshooting period.
- These mechanical and UI observations do not establish a direct thread-presence sensor, tension sensor, motor-overload code, position-sensor fault, or any specific protocol status.
- Correct bobbins, 100% polyester all-purpose thread, a needle assortment, denim needles, and Singer oil were obtained locally after returning the Amazon starter supplies. Exact package identities and authoritative compatibility remain unverified.
- The machine reportedly lacked spool caps and other loose accessories. Correct horizontal-spool retention is therefore an unresolved prerequisite; a standalone thread stand remains a possible workaround if the onboard spool path cannot feed cleanly.
- The generic replacement foot controller remains uncharacterized by model, rating, connector wiring, and electrical equivalence. It must not be assumed unrelated to ramp-stop or red-indicator behavior.
- An updated EZ-Flash Jr reportedly booted the tested software set on a stock Game Boy Color.
- Stock GBC plus EZ-Flash Jr plus Singer/IZEK software reportedly produced visible lateral needle motion and later halted with a thread-related error.
- A Singer/IZEK image was reportedly written to and redumped from a FunnyPlaying EverSave cart.
- `Jaguar Mishin Sashi Senyou Soft - Kirby Family (Japan) (Proto)` was reportedly written to and redumped from an InsideGadgets MBC5 2 MiB / 32 KiB FRAM cart using OSCR `CFI Repro`, `WE=WR`, and M29F160F-compatible behavior.
- EZ-Flash Jr reportedly failed to boot on FP-GBC.
- DS-family side work revived an R4 SDHC with period firmware and made GameYob/GBARunner2 operational. That path is separate from native GB/GBC IZEK protocol evidence.

## Model and accessory boundary

Current project documentation must preserve these distinctions until project-owned manuals, catalogs, hardware, or captures verify them:

- Singer IZEK 1500 is the project-owned Western base sewing-machine target. Current project evidence does not establish EM-2000 attachment support.
- Jaguar JN-100 / nu-yell is treated as the analogous Japanese base-machine path.
- Jaguar JN-2000 / nuotto is the embroidery-capable path associated in prior art with the EM-2000 embroidery unit.
- Jaguar EM-2000 is an embroidery arm/accessory, not interchangeable with the base IZEK/JN-100 sewing path.

An embroidery-software screen requesting or depicting the embroidery unit is compatible with missing JN-2000/EM-2000 capability. It does not prove that the project-owned IZEK accepts that unit, that the cartridge is defective, or that any exact protocol status byte has been identified.

## Bobbin-case fault boundary

The bobbin case should have limited clearance, not unrestricted rotation. The reported 10-degree-plus movement into the needle path is unsafe for powered operation and is sufficient to explain needle impact and thread jams without invoking a Game Boy or cartridge fault.

Potential fault classes remain separate:

1. damaged or incorrect bobbin case geometry;
2. stopper or position-bracket seating, adjustment, screw, or clearance;
3. retainer, retainer spring, shuttle race, or race-base fault;
4. needle-bar alignment, hook timing, needle plate, or hook/race deformation after retention is verified.

Source leads retained for later verification include bobbin-case families `76212`, `076212`, `141000810`, and `51045`; stopper or position references `76118` and possible retail cross-reference `51058`; and deeper hook-area references `76156`, `76157`, `76213`, `76027`, `76103`, and `85164`. These are search leads only, not verified interchangeability claims.

## Layered result model

Every compatibility run must record these separately:

1. cartridge write completed;
2. redump matched source;
3. host recognized cartridge;
4. software booted;
5. operational UI reached;
6. machine link initialized;
7. upload started;
8. upload completed;
9. machine moved;
10. valid stitch formed.

A pass at one layer does not imply a pass at the next. `Booted` is not shorthand for machine compatibility.

## Superseded boundary

The earlier statement that no flash-cart communication with the physical IZEK had been observed is superseded. One stock-GBC/EZ-Flash Jr/Singer path reportedly produced deterministic machine motion. That does not establish generalized flash-cart compatibility, packet semantics, detailed coordinate transfer, or a valid stitch.

## Current claim boundary

Not established:

- a valid threaded stitch or embroidery result;
- completed upload for the photo-backed 2026-05-03 compatibility runs;
- correct feed height, feed timing, stitch length, or durable feed-dog repair;
- correct bobbin-case retention under handwheel, bobbin-only, threaded, or powered conditions;
- whether the damaged bobbin case alone is sufficient cause;
- stopper, retainer, shuttle-race, needle-bar, or hook-timing correctness;
- correct spool support, spool-cap fit, or stable upper-thread feed;
- electrical equivalence of the generic replacement foot controller;
- the specific cause of the ramp-stop-red indication;
- whether the upper-machine graphic represents threading, spool routing, take-up, tension, or another machine condition;
- direct sensing of missing thread or thread tension;
- EM-2000 compatibility with the Singer IZEK 1500;
- electrical equivalence among original, EZ-Flash Jr, FunnyPlaying, and InsideGadgets cartridges;
- equivalence among stock GBC, Pocket, GBA CGB mode, SGB2, FP-GBC, MiSTer, Analogue Pocket, or Chromatic;
- connector pinout, voltage levels, idle states, signaling direction, or clock ownership;
- packet format, commands, timing, status values, integrity fields, or stitch encoding;
- exact cause of the host-specific upload failures or thread-related halt;
- independent reproduction of Shonumi's protocol findings.

## Blocking evidence gaps

1. The original sixteen photos are hash-identified, but only the contact-sheet derivative is committed through the current repository connector.
2. No row-level mapping from every source photo and workbook row to exact experiment and evidence IDs.
3. No exact chronology resolving differing Pocket, GBA, GBC, and FP-GBC observations across Singer and Kirby runs.
4. No exact ROM hashes, cartridge revisions, programmed-image verification, host board revisions, firmware/core versions, cable identities, machine state, error text, timestamps, repetition counts, or artifact hashes for the retained compatibility runs.
5. No photographs or dimensions of the broken feed-dog slider notch, engaged/disengaged positions, or durable repair.
6. No photograph or authoritative identification of the broken needle or validated replacement needle system/orientation.
7. No high-resolution photos of the bobbin case, locating tab, stopper or position bracket, retainer/race stack, needle plate, or strike marks.
8. No controlled handwheel record separating no-thread, bobbin-only, threaded, and powered behavior.
9. No authoritative cross-reference confirming any candidate bobbin case, stopper, retainer, or race part for the exact IZEK machine revision.
10. No photos or authoritative manual confirmation for bobbin class, bobbin-winder seating, spool-cap requirements, spool-pin setup, thread path, or oiling points.
11. No model, rating, connector pinout, wiring, or safety comparison for the generic foot controller.
12. No synchronized record of machine motion, red-indicator cadence, Game Boy screen, mechanical state, threading state, and exact sequence for the fault run.
13. No documented ordinary threaded straight-stitch baseline.
14. No complete OSCR logs and source/redump hash pairs.
15. No protected passive breakout, voltage survey, or project-generated raw capture.
16. No pinned GBE+ commit, files, symbols, and license extraction for each code-derived claim.
17. No pinned prior-art section or project-owned source establishing the JN-2000/EM-2000 model relationship.

## Immediate actions

1. Stop powered sewing tests until the bobbin case remains constrained and the needle clears through manual rotation.
2. Photograph the original bobbin case installed and removed, including locating geometry, strike marks, stopper contact, retainer/race hardware, and needle-plate damage.
3. Install a new, straight, correctly oriented needle and perform at least 20 slow handwheel cycles with no upper thread and no bobbin.
4. Confirm a firm clockwise/counterclockwise mechanical stop without case lift, rocking, or needle contact.
5. Repeat only after passing each stage: bobbin installed without upper thread, then threaded handwheel test, then the slowest powered test.
6. Reject replacement cases that differ in height, locating geometry, needle-clearance window, bottom profile, or stopper contact point.
7. If a confirmed replacement case still rotates with no thread, inspect stopper position and screw, retainer and retainer spring, shuttle race, race base, cover, and prior-crash burrs.
8. If the case is firmly retained but the needle still strikes, stop and treat the fault as timing, needle-bar, needle-plate, or hook/race alignment.
9. Map each original compatibility photo hash and workbook row to a separate experiment/evidence record.
10. Preserve both workbook revisions and document their chronology and content differences.
11. Retest one exact image/cart/host combination at a time, recording machine power state, attachments, thread state, selected operation, exact screen text, and repetition count.
12. Keep boot, UI, link initialization, upload start, upload completion, physical motion, and stitch formation as separate fields.
13. Photograph the broken feed-dog slider/notch, measure it, record engaged and disengaged positions, and document a reversible retention or durable repair.
14. Document ordinary sewing setup: exact bobbin type, bobbin-winder behavior, upper thread route, spool support, presser-foot state, feed-dog state, fabric, stabilizer, and tension settings.
15. Identify the generic foot controller by model, rating, connector, wiring, and safety characteristics before attributing powered faults solely to the machine.
16. Produce and document one ordinary valid straight stitch before interpreting protocol-driven motion as sewing success.
17. Reproduce OSCR reads and both write/redump paths with complete logs and SHA-256 comparisons.
18. Validate a protected passive fixture and voltage compatibility before active hardware is connected.
19. Pin GBE+ commit and source locations before using implementation details.
20. Pin the Shonumi/manual/catalog evidence for JN-100, JN-2000, and EM-2000 model roles.

## EM-2000 deferral decision

EM-2000 spoofing and embroidery-design dumping are deferred. The required sequence is:

1. restore ordinary Singer IZEK sewing operation;
2. validate the normal Game Boy/software/machine path on real hardware;
3. build and validate a passive capture fixture;
4. capture the base sewing-machine handshake, one normal path, and one controlled fault or blocked path;
5. only then define the minimum JN-2000/EM-2000 presence or capability response needed for design-extraction research.

The initial future goal, when the gate is satisfied, is presence/capability/status emulation sufficient to observe or extract design data. It is not motor control, hoop motion, or physical embroidery.

## Protocol implementation gate

No active drive, replay, endpoint emulator, EM-2000 spoofing, or firmware implementation until all of the following are documented:

- ordinary machine operation and at least one valid stitch;
- corrected bobbin-case retention and safe needle clearance;
- exact software, cartridge, host, cable, machine, and firmware identities;
- deterministic write/redump verification with hashes;
- protected passive measurement fixture;
- idle-state voltage survey;
- immutable raw capture;
- one captured normal base-machine path and one controlled fault or blocked path;
- a narrowly stated measured question;
- hazard/failback plan;
- prior-art provenance and license boundaries.
