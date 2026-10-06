---
name: pcb-design-workflow
description: >-
  End-to-end workflow for designing a PCB (schematic, component selection,
  stack-up, placement, routing, DRC, outputs). Use when the user starts, plans,
  or reviews any PCB or schematic design, or asks which EDA tool, layer count,
  or fab settings to use.
---

# PCB Design Workflow

Follow these phases in order. Ask the user for missing inputs in Phase 0 before designing.

## Phase 0: Requirements (ask if unknown)
- Function, supply voltage(s), max current per rail, interfaces and speeds.
- Board size, mounting holes, connectors, weight limit, environment (temp, vibration, moisture).
- Quantity, budget, fab (default JLCPCB or PCBWay), assembly (hand or SMT service).
- EDA tool (default KiCad).

## Phase 1: Schematic
- Hierarchical sheets per function (power, MCU, sensors, comms, connectors).
- Consistent net names; label every power rail and test point.
- Every IC: decoupling per datasheet, pull-ups and straps, reset, boot pins, ESD on external connectors.
- Run ERC to zero errors; justify every warning.

## Phase 2: Components and Footprints
- Read the datasheet's absolute maximum and recommended operating conditions; derate 20–50 percent.
- Check stock, lifecycle, and an alternate for every critical part (LCSC, Digi-Key, Octopart).
- Use IPC-7351 footprints; verify pin 1, pad size, and courtyard against the datasheet drawing.
- Prefer 0402 or larger for hand assembly; 0603 or 0805 for power and prototypes.

## Phase 3: Stack-up and Rules
| Board type | Layers | Notes |
|---|---|---|
| Simple digital or analog | 2 | Ground pour on bottom |
| MCU with USB or high-speed, mixed-signal | 4 | Sig / GND / PWR / Sig |
| Dense, DDR, RF | 6+ | Dedicated planes per signal layer |

- Default rules (standard fab): trace 0.15 mm min (0.2 mm preferred), clearance 0.15 mm, via 0.3/0.6 mm, annular ring 0.13 mm min. Check the fab's current capability page.
- Set net classes for power, signal, and differential pairs before routing.

## Phase 4: Placement
1. Fix connectors, mounting holes, and board outline first.
2. Place the main IC, then its decoupling capacitors closest to the power pins.
3. Group by function; keep analog away from switching and digital sections.
4. Put crystals close to the MCU with short traces and a ground guard.
5. Leave room for test points, programming header, and rework.

## Phase 5: Routing
- Route critical first: RF, differential pairs, clocks, then power, then general signals.
- Keep return paths unbroken; do not route across plane splits.
- 45-degree or curved bends; avoid acute angles and stubs.
- Stitch ground vias near layer changes and board edges.

## Phase 6: Verify and Output
- DRC clean; 3D view check for mechanical fit; print 1:1 to check footprints.
- Silkscreen: reference designators, polarity, pin 1, version, and date.
- Outputs: Gerbers, drill files, BOM, pick-and-place (CPL), schematic PDF, assembly drawing.
- Check the Gerbers in a viewer before ordering.

For deeper checks, use the `pcb-design-review`, `pcb-power-thermal`, `pcb-highspeed-rf-emc`, and `uav-avionics-pcb` skills.
