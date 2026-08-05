# Evidence and Claim Matrix

This matrix prevents conversation history, prior art, and direct bench results from collapsing into a single narrative.

| Claim or asset | Label | Current support | Repository evidence still needed |
|---|---|---|---|
| Shonumi published Singer/Jaguar reverse engineering | prior art | Original article and archived snapshot identified | Archive metadata or local citation record |
| GBE+ emulates IZEK 1500, JN-100, and JN-2000 behavior | prior art | Public GBE+ repository and article | Pin exact commit and relevant source paths |
| OSCR hardware is assembled and can dump GB ROM/save data | observed/reported | Retained project record | Build photographs, firmware version, sample command log, hashes |
| OSCR can write the selected InsideGadgets cart | observed/reported | Successful flash/redump retained in project history | Flash log and byte-for-byte comparison manifest |
| InsideGadgets cart is MBC5, 2 MiB ROM, 32 KiB FRAM, ultra-low-power | observed/reported | Purchased product selection and successful use | PCB photograph and product-page snapshot or invoice metadata |
| FunnyPlaying EverSave can hold and redump the Singer operation image | observed/reported | Successful test retained in project history | Hashes and procedure |
| EZ-Flash Jr works on original Game Boy hardware | observed/reported | Target ROM set booted after firmware update | Firmware version and test matrix |
| EZ-Flash Jr fails on FPGA GBC | observed/reported | Repeated incompatibility retained in project history | Error photograph/video and FPGA firmware version |
| Original hardware is the current execution baseline | decision | Based on observed cart/platform behavior | Keep decision until FPGA equivalence is demonstrated |
| Singer operation ROM uses MBC5 + RAM + battery, 1 MiB ROM, 8 KiB RAM | reported | Prior header analysis | Commit generated header report and hashes, not ROM |
| `Raku x Raku - Mishin` is a base machine-control title | reported | Prior ROM-set analysis | Reproduce classification from UI behavior and/or code inspection |
| Kirby/Mario/Cut Shuu/Moji require embroidery-unit path | reported | Prior test/classification record | Record boot behavior and required-device prompts |
| Game Boy link traffic can be captured with modest digital instrumentation | inferred | Link is low-rate synchronous serial; public tooling exists | Measure actual machine traffic and voltage levels |
| Flipper Zero can implement the IZEK endpoint | unverified | Public GB link-port apps show related capability | Timing test, protocol capture, minimum handshake implementation |
| Expensive Keysight-class instrumentation is required | not supported | No evidence of an analog or high-speed blocker | Escalate only after ordinary logic capture fails for a measured reason |
| The sewing-machine protocol is fully understood by this project | false/currently unsupported | No independent capture or implementation yet | Complete capture, decode, replay, and independent verification |

## Updating this matrix

Change a label only when the supporting artifact is committed or linked. A successful result remembered from a bench session remains `observed/reported` until the procedure and output are attached. Prior-art agreement does not convert an unmeasured project claim into an observation.
