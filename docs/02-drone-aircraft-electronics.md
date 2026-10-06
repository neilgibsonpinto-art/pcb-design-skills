# Drone and Aircraft Electronics

## Core Systems
- **Flight controller**: MCU (STM32), IMU, barometer, and magnetometer.
- **ESC**: MOSFET and gate driver design, high-current traces, and BLDC control.
- **Power distribution board**: Heavy copper, BECs, and regulators.
- **Communication**: RC receivers (ELRS, CRSF), telemetry radios, GNSS, and VTX.
- **Sensors and payload**: Cameras, LiDAR, optical flow, and airspeed sensors.
- **Companion computers**: Raspberry Pi or Jetson over UART, SPI, and CAN.

## Key Skills
1. **High-current and power design**: Wide traces, 2–4 oz copper, thermal vias, low-inductance power loops, TVS, reverse-polarity protection, and inrush limiting.
2. **Noise and signal integrity**: Isolating the IMU from motor noise, clean analog grounding, and differential pairs for USB and CAN.
3. **RF and antenna layout**: GPS, 2.4 GHz, 5.8 GHz, and 915 MHz keep-outs, and matched RF traces.
4. **Size, weight, and mechanics**: Thin boards, standard mounting patterns (30.5×30.5 mm, 20×20 mm), and vibration resistance.
5. **Reliability and safety**: Redundancy, conformal coating, temperature and altitude range, and watchdog circuits.

## Aviation Standards
| Standard | Scope |
|----------|-------|
| DO-254 | Airborne electronic hardware assurance |
| DO-178C | Airborne software assurance |
| DO-160 | Environmental testing (vibration, EMI, temperature, lightning) |
| MIL-STD-810 / 461 | Military environmental and EMI |
| IPC Class 3 | High-reliability PCB manufacturing |
| ARP4754A / ARP4761 | System development and safety assessment |

## Protocols
UART, SPI, I2C, CAN/DroneCAN, PWM/DShot, SBUS/CRSF, MAVLink, ARINC 429, and MIL-STD-1553.
