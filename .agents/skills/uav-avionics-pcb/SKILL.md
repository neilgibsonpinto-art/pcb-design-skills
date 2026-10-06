---
name: uav-avionics-pcb
description: >-
  PCB design for drones, UAVs, and aircraft electronics: flight controllers, ESCs,
  power distribution boards, IMU and GNSS layout, radio links, vibration and
  reliability, and aviation standards (DO-254, DO-160). Use when designing or
  reviewing any drone, FPV, fixed-wing, or avionics hardware.
---

# UAV and Avionics PCB

## Architecture Checklist
- Flight controller: MCU (STM32 F4/F7/H7), IMU(s), barometer, magnetometer (keep away from current), SD or flash, USB, UART/CAN/I2C/SPI ports, PWM or DShot outputs.
- Reference designs to study first: Pixhawk standards, ArduPilot and PX4 supported boards, Betaflight targets, VESC for ESCs.

## Layout Priorities
1. **IMU**: near board center, on a quiet, low-noise rail (LDO), isolated from ESC and motors. Add foam or soft mounting; separate IMU ground area on the plane by placement, not splits. Use a heater or thermal mass if the application needs temperature stability.
2. **Magnetometer**: far from power traces, motors, and magnets; ideally on a GNSS mast.
3. **GNSS**: antenna at top edge, clear sky view, away from VTX, regulators, and USB 3 noise; add LNA/SAW only per module datasheet.
4. **ESC power stage**: 2–4 oz copper, wide pours, minimal hot loop, bulk plus ceramic capacitors close to MOSFETs, gate drive loop short, Kelvin shunt sensing, TVS for regen spikes.
5. **PDB**: wide copper, solder pads sized for wire gauge (for example 12–14 AWG at 30–60 A), BEC with enough margin, voltage and current sense (divider and shunt) to ADC.
6. **Radios**: 2.4 GHz (ELRS), 915 MHz, and 5.8 GHz VTX kept apart; each with its own ground via fence and correct antenna keep-out.

## Mechanical
- Standard mounting: 30.5 × 30.5 mm (M3), 20 × 20 mm (M2), 25.5 × 25.5 mm. Keep tall parts away from the stack.
- Thickness 1.0–1.6 mm for FCs (rigid), 0.8 mm for weight-critical boards.
- Strain relief on connectors; use locking connectors (JST-GH, Molex) and JST-SH for small payloads.
- Conformal coat for moisture and vibration, leaving connectors, sensors (baro with a cover), and antennas uncoated.

## Reliability
- Redundancy where required: dual IMU, dual power path (diode-OR or ideal-diode controller), separate rails for critical sensors.
- Watchdog, brown-out detect, and failsafe defaults on motor outputs.
- Wide input range with surge protection (up to 6S or 12S LiPo: check for ringing and spikes).
- Operating temperature of at least −20 to +85 °C; consider altitude (reduced cooling).
- Test points on all rails and critical signals.

## Standards (for certified or commercial aircraft)
- DO-254 (hardware assurance), DO-160 (environmental), DO-178C (software), ARP4754A and ARP4761 (system and safety).
- IPC Class 3 fabrication and assembly; MIL-STD-810 and MIL-STD-461 for military.
- For hobby and research drones, apply the intent: documentation, traceability, and testing.

## Protocols
UART, SPI, I2C, CAN and DroneCAN, PWM, DShot, SBUS and CRSF, MAVLink; ARINC 429 and MIL-STD-1553 for aircraft.

## Before Release
- [ ] IMU and magnetometer isolation reviewed.
- [ ] Power path tested for stall, regen, and brown-out.
- [ ] RF keep-outs verified for every radio.
- [ ] Vibration and thermal test plan written.
- [ ] Bench bring-up checklist prepared: rails, clocks, programming, sensors, outputs.
