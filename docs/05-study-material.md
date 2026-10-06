# Study Material

A topic-by-topic syllabus. Each topic lists what to study and where. Items without a link are best found by searching the exact title. Verify links and editions before use.

## 1. Electronics Fundamentals
**Study:** voltage, current, resistance, Ohm's and Kirchhoff's laws, capacitors, inductors, diodes, BJTs, MOSFETs, op-amps, and filters.
- *The Art of Electronics*, Horowitz and Hill
- *Make: Electronics*, Charles Platt
- *Practical Electronics for Inventors*, Scherz and Monk
- [All About Circuits](https://www.allaboutcircuits.com/) (free textbook and tutorials)
- [Khan Academy: Electrical Engineering](https://www.khanacademy.org/science/electrical-engineering)
- [MIT OpenCourseWare 6.002 Circuits and Electronics](https://ocw.mit.edu/)
- [EEVblog](https://www.youtube.com/@EEVblog) and [GreatScott!](https://www.youtube.com/@greatscottlab) on YouTube

## 2. Digital Electronics and Microcontrollers
**Study:** logic, timing, UART, SPI, I2C, CAN, ADC/DAC, clocks, and bootloaders.
- *Making Embedded Systems*, Elecia White
- *Mastering STM32*, Carmine Noviello
- [STM32 hardware development guide, AN4488](https://www.st.com/) (search the number on st.com)
- [Arduino documentation](https://docs.arduino.cc/)
- [Phil's Lab](https://www.youtube.com/@PhilsLab): STM32 and KiCad design

## 3. Schematic Capture and Component Selection
**Study:** reading datasheets, reference designs, derating, lifecycle, and alternates.
- Manufacturer reference designs and evaluation board schematics (TI, ST, Microchip, Analog Devices)
- [SparkFun Learn](https://learn.sparkfun.com/) and [Adafruit Learn](https://learn.adafruit.com/): how to read a datasheet and schematic
- [Octopart](https://octopart.com/) and [Digi-Key](https://www.digikey.com/): parametric search

## 4. PCB Layout Fundamentals
**Study:** placement, routing, stack-up, vias, clearance, copper weight, and the DRC.
- [KiCad documentation](https://docs.kicad.org/)
- *Printed Circuit Board Designer's Reference: Basics*, Christopher Robertson
- *The Printed Circuit Designer's Guide to... Flex and Rigid-Flex Fundamentals* (free eBooks from [I-Connect007](https://iconnect007.com/))
- [Contextual Electronics](https://contextualelectronics.com/)
- [Robert Feranec](https://www.youtube.com/@RobertFeranec) and [Altium Academy](https://www.youtube.com/@AltiumAcademy) on YouTube

## 5. Power Electronics and Power Integrity
**Study:** linear and switching regulators, buck, boost, and LDO design, decoupling, PDN, current capacity, and thermal limits.
- *Fundamentals of Power Electronics*, Erickson and Maksimovic
- *Switching Power Supplies A to Z*, Sanjaya Maniktala
- *Power Integrity: Measuring, Optimizing, and Troubleshooting Power Related Parameters in Electronics Systems*, Steve Sandler
- TI Power Management Guide and Application Notes (search "TI AN-1149 layout guidelines for switching power supplies")
- [Würth Elektronik Trilogy of Magnetics](https://www.we-online.com/)
- [LTspice](https://www.analog.com/en/resources/design-tools-and-calculators/ltspice-simulator.html)

## 6. Signal Integrity and High-Speed Design
**Study:** transmission lines, impedance, reflections, crosstalk, differential pairs, length matching, and return paths.
- *Right the First Time*, Lee Ritchey
- *High-Speed Digital Design: A Handbook of Black Magic*, Johnson and Graham
- *Signal and Power Integrity – Simplified*, Eric Bogatin
- [Bogatin's Rules of Thumb](https://www.bethesignal.com/) (search "Bogatin Rules of Thumb")
- [Saturn PCB Toolkit](https://saturnpcb.com/saturn-pcb-design-toolkit/)
- [Hyperlynx / Ansys SIwave](https://www.ansys.com/) for simulation

## 7. EMI/EMC
**Study:** noise sources, grounding, shielding, filtering, loop area, and pre-compliance testing.
- *EMC and the Printed Circuit Board*, Mark Montrose
- *Electromagnetic Compatibility Engineering*, Henry Ott
- *Grounding and Shielding: Circuits and Interference*, Ralph Morrison
- [EMC Fastpass](https://www.emcfastpass.com/) and [EMCStandards](https://www.emcstandards.co.uk/) guides

## 8. RF and Antenna Layout
**Study:** microstrip and CPWG, matching networks, Smith chart, antenna keep-outs, and filters.
- *RF Circuit Design*, Chris Bowick
- *Microwave Engineering*, David Pozar
- *RF Design Guide: Systems, Circuits, and Equations*, Peter Vizmuller
- [Analog Devices RF resources](https://www.analog.com/)
- [Texas Instruments antenna design notes](https://www.ti.com/) (search "TI antenna selection quick guide")
- [Nordic Semiconductor antenna and layout guidelines](https://docs.nordicsemi.com/)

## 9. Thermal Management
**Study:** thermal resistance, copper spreading, thermal vias, and heat sinks.
- TI SPRA953 "IC Package Thermal Metrics"
- *Thermal Design: Heat Sinks, Thermoelectrics, Heat Pipes, Compact Heat Exchangers, and Solar Cells*, Ralph Remsburg
- [Celsius EC / Ansys Icepak](https://www.ansys.com/) for simulation

## 10. Manufacturing: DFM, DFA, and DFT
**Study:** fab capabilities, panelization, solder mask, assembly, and test points.
- IPC-2221, IPC-7351, IPC-A-600, IPC-A-610, IPC-6012, and IPC-J-STD-001 from [ipc.org](https://www.ipc.org/)
- [JLCPCB capabilities](https://jlcpcb.com/capabilities/pcb-capabilities) and [PCBWay capabilities](https://www.pcbway.com/capabilities.html)
- [PCB Fabrication Design Guides, Altium resources](https://resources.altium.com/)
- *The Printed Circuit Designer's Guide to Design for Manufacturing*, I-Connect007

## 11. Drone and UAV Electronics
**Study:** flight controllers, ESCs, power distribution, GNSS, radio links, and companion computers.
- [ArduPilot developer docs](https://ardupilot.org/dev/)
- [PX4 developer guide](https://docs.px4.io/)
- [Pixhawk Standards](https://github.com/pixhawk/Pixhawk-Standards)
- [Betaflight](https://github.com/betaflight/betaflight)
- [DroneCAN](https://dronecan.github.io/) and [MAVLink](https://mavlink.io/)
- [Oscar Liang](https://oscarliang.com/)
- [ExpressLRS](https://www.expresslrs.org/)
- [VESC Project](https://vesc-project.com/): open-source motor controller
- *Small Unmanned Aircraft: Theory and Practice*, Beard and McLain
- *Quadrotor Control* and the Coursera "Aerial Robotics" course (University of Pennsylvania)

## 12. Motor Control (BLDC and ESC)
**Study:** BLDC and PMSM theory, six-step commutation, FOC, gate drivers, and current sensing.
- *Brushless Permanent Magnet and Reluctance Motor Drives*, T.J.E. Miller
- *Advanced Electric Drives*, Ned Mohan
- [SimpleFOC](https://simplefoc.com/)
- TI and ST motor control application notes (search "FOC BLDC application note")
- [Texas Instruments Motor Drive resources](https://www.ti.com/motor-drivers)

## 13. Aerospace and Avionics Standards
**Study:** design assurance, environmental testing, safety assessment, and certification.
- RTCA DO-254, DO-160, and DO-178C from [rtca.org](https://www.rtca.org/)
- SAE ARP4754A and ARP4761 from [sae.org](https://www.sae.org/)
- MIL-STD-810 and MIL-STD-461 (US DoD)
- *Airborne Electronic Hardware Design Assurance: A Practitioner's Guide to RTCA/DO-254*, Randall Fulton and Roy Vandermolen
- FAA guidance on [airborne electronic hardware](https://www.faa.gov/)

## 14. Testing and Debugging
**Study:** oscilloscope use, probing, logic analyzers, bring-up, and troubleshooting.
- *Troubleshooting Analog Circuits*, Bob Pease
- *Debugging: The 9 Indispensable Rules*, David Agans
- Keysight and Tektronix oscilloscope primers (free application notes)
- [Sigrok / PulseView](https://sigrok.org/): open-source logic analyzer software

## 15. Professional Skills
- Git and GitHub for hardware: [KiCad with Git guide](https://docs.kicad.org/)
- Documentation: design notes, revision control, and handoff packages
- [Hackaday.io](https://hackaday.io/) and [Open Source Hardware Association](https://www.oshwa.org/): share and certify projects

## Free Video Courses (Quick List)
- Phil's Lab: KiCad and STM32 PCB series
- Robert Feranec: FEDEVEL Academy (free videos, paid courses)
- Contextual Electronics: KiCad
- Altium Academy
- Rohde & Schwarz and Keysight YouTube channels for EMC and oscilloscopes
- Coursera: "Introduction to Electronics" (Georgia Tech) and "Aerial Robotics" (UPenn)
- edX / MIT OCW: Circuits and Electronics

## Practice Projects
Pair each topic with a build:
1. LED and 555 timer board → fundamentals
2. 3.3 V buck converter → power
3. STM32 minimal board → microcontrollers and layout
4. USB-C device with differential pair → signal integrity
5. IMU breakout → noise and SPI
6. GPS and radio board → RF layout
7. Mini flight controller → integration
8. 4-in-1 ESC → motor control and high current
