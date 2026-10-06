---
name: pcb-design-review
description: >-
  Pre-fabrication review checklist for PCBs covering schematic, footprints,
  layout, DFM/DFA/DFT, bring-up planning, and common failure modes. Use when
  the user asks to review, check, or debug a PCB design, or before ordering boards.
---

# PCB Design Review

Run through each section and report findings as **Blocker**, **Should fix**, or **Note**.

## Schematic
- [ ] Power pins, grounds, and reset/boot pins connected per datasheet.
- [ ] Voltage levels compatible between all interfaces (level shifting where needed).
- [ ] I2C pull-ups present once per bus, with correct values (2.2–4.7 kΩ at 3.3 V).
- [ ] USB: CC resistors (5.1 kΩ), ESD, shield handling, D+/D− not swapped.
- [ ] Unused pins handled; enable pins not floating.
- [ ] Test points and a programming/debug header (SWD, UART) present.
- [ ] Power sequencing checked.

## Footprints and BOM
- [ ] Every footprint checked against the datasheet drawing (print 1:1 and place parts on it).
- [ ] Pin 1 and polarity marked on silkscreen and in 3D.
- [ ] All parts in stock, with alternates; MPN and LCSC/Digi-Key numbers in BOM.
- [ ] Connector pinouts and mating side verified (the most common error).

## Layout
- [ ] DRC at zero; no unconnected nets.
- [ ] Decoupling close to pins; crystals short.
- [ ] Reference planes continuous under fast signals.
- [ ] Current paths sized (see `pcb-power-thermal`).
- [ ] Clearances for high voltage and creepage where relevant.
- [ ] Mounting holes, connector access, and cable clearances checked in 3D.

## DFM / DFA / DFT
- [ ] Meets fab minimums (trace, space, drill, annular ring, silk-to-pad clearance).
- [ ] Acid traps and slivers avoided; copper balanced across layers.
- [ ] Fiducials (3 global) for assembly; parts on one side where possible.
- [ ] Panelization and tab routing decided; board edge clearance of at least 0.3 mm for copper.
- [ ] Test points accessible; component spacing for rework.
- [ ] Tented or covered vias under fine-pitch parts.

## Outputs
- [ ] Gerbers, drill, BOM, CPL, and PDF generated from the latest design.
- [ ] CPL rotation checked against the assembler's preview (rotation errors are common with JLCPCB).
- [ ] Gerbers opened in a separate viewer and compared to the layout.

## Bring-up Plan
1. Visual inspection and short check between each power rail and ground (multimeter).
2. Power with a current-limited bench supply; check each rail voltage.
3. Check clocks, then programming and debug access.
4. Bring up peripherals one at a time; log results.
5. Record fixes for the next revision (rev B list).

## Common Failure Modes
Wrong connector mirror, reversed footprints, missing pull-ups, floating enable pins, regulator instability from capacitor choice, ground bounce on IMU or ADC, antenna detuned by nearby copper, and thermal runaway in LDOs.
