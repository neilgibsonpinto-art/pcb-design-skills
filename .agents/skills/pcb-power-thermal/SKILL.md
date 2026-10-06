---
name: pcb-power-thermal
description: >-
  Power delivery and thermal design for PCBs: trace width and current, copper
  weight, decoupling, regulators (LDO, buck, boost), switching-converter layout,
  protection, and heat management. Use when a design has motors, batteries,
  regulators, high current, or components that run hot.
---

# PCB Power and Thermal

## Current Capacity (IPC-2221 rule of thumb, 10 °C rise)
| Current | External 1 oz trace | External 2 oz trace |
|---|---|---|
| 1 A | about 0.3 mm | about 0.15 mm |
| 3 A | about 1.0 mm | about 0.5 mm |
| 5 A | about 2.0 mm | about 1.0 mm |
| 10 A | about 5 mm | about 2.5 mm |

Use a calculator (Saturn PCB Toolkit) to confirm. Above 10 A, use copper pours, multiple layers stitched with vias, 2–4 oz copper, or bus bars. Internal layers carry about half as much as external.

## Regulators
- **LDO**: dissipation = (Vin − Vout) × I. If above about 0.5 W on a small package, use a buck instead.
- **Buck/boost**: follow the datasheet layout exactly.
  - Minimize the hot loop (input cap, switch, diode or synchronous FET); put the input capacitor right at the IC.
  - Keep the switch node small; no sensitive traces under it.
  - Solid ground plane directly below on layer 2.
  - Feedback divider away from the inductor, routed to the output capacitor, not the inductor.
- Add bulk plus ceramic output capacitors; check DC-bias derating of ceramics.

## Decoupling
- 100 nF per supply pin placed within 2–3 mm, via to the plane directly at the capacitor pad.
- Add 1–10 µF per rail section, and bulk near connectors.
- Ferrite bead plus capacitors for analog and RF rails.

## Protection
- Reverse polarity: P-MOSFET (preferred over a diode at high current).
- TVS diode on battery and external connectors; fuse or PTC on inputs.
- Inrush limiting or soft start for large capacitance.
- Current sense: Kelvin-connect to shunt pads.

## Thermal
- Thermal pad: multiple vias (0.3 mm, 1 mm pitch) to inner and bottom copper.
- Larger copper area under and around hot parts; keep heat-sensitive parts (sensors, crystals) away.
- Compute: Tj = Ta + P × RθJA; keep Tj below 85 percent of the max rating.
- Beyond about 2 W on-board dissipation, consider a heat sink, airflow, or metal-core board.

## Checks Before Release
- [ ] Every rail has current margin of at least 30 percent.
- [ ] Hot loops are minimal and have unbroken ground below.
- [ ] Protection on all external power inputs.
- [ ] Thermal estimate done for every part above 0.5 W.
