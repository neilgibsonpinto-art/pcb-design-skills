---
name: pcb-highspeed-rf-emc
description: >-
  Signal integrity, controlled impedance, differential pairs (USB, CAN, Ethernet),
  RF and antenna layout, grounding, and EMI/EMC practice for PCBs. Use when a
  design has USB, SPI above 20 MHz, DDR, Ethernet, GPS, Wi-Fi, LoRa, or any radio,
  or when noise or EMC problems appear.
---

# High-Speed, RF, and EMC Layout

## Grounding
- Prefer a solid, unbroken ground plane directly under signal layers (4-layer: Sig / GND / PWR / Sig).
- Do not route signals across plane splits or slots; if a layer change is needed, add a ground via next to the signal via.
- Analog and digital share one ground plane; separate by placement and routing, not by splitting, unless the datasheet requires it.
- Keep high-current return paths away from sensitive analog sections.

## Controlled Impedance
- Single-ended 50 Ω, differential 90 Ω (USB), 100 Ω (Ethernet, LVDS), 120 Ω (CAN).
- Get stack-up from the fab (JLCPCB offers a 4-layer impedance calculator); compute trace width with Saturn PCB Toolkit or KiCad's calculator.

## Differential Pairs
- Route together, equal length (USB 2.0: within about 0.15 mm; check each standard), constant spacing, no stubs.
- Place series resistors, ESD (low-capacitance TVS), and common-mode chokes close to the connector.
- Keep 3× trace-width spacing from other signals.

## Clocks and Fast Edges
- Keep short; guard with ground; no vias if possible; series termination (22–33 Ω) at the source.
- Crystal: load capacitors per datasheet, ground pour below on that layer, no signals underneath.

## RF and Antenna
- Place antenna at a board edge with the manufacturer's keep-out (no copper, traces, or battery nearby on any layer).
- RF trace: shortest path, 50 Ω, ground vias along both sides every λ/20 or less, no sharp corners.
- Add a pi matching network footprint (series L, shunt C) for tuning.
- Keep GPS and receivers away from switching regulators, VTX, and motor wires; shield cans where needed.

## EMI Reduction
- Minimize loop areas (signal and its return, power and its decoupling).
- Filter every external connector (ferrite, RC, TVS).
- Spread-spectrum or slower edge rates where available.
- Add footprints for optional shield can, ferrite beads, and series resistors for tuning during EMC testing.

## Checks
- [ ] Impedance and stack-up confirmed with fab.
- [ ] All fast signals have continuous reference plane.
- [ ] Differential pairs matched and symmetrical.
- [ ] Antenna keep-out respected on all layers.
- [ ] Connectors filtered and ESD protected.
