# PCB Design Skills (with Drone and Aircraft Electronics)

A curated skills map and reading list for PCB design, with a focus on drones, UAVs, and avionics.

## Contents
| File | Description |
|------|-------------|
| [docs/01-pcb-design-skills.md](docs/01-pcb-design-skills.md) | Core, advanced, manufacturing, tool, and soft skills |
| [docs/02-drone-aircraft-electronics.md](docs/02-drone-aircraft-electronics.md) | Skills specific to drones, UAVs, and aircraft |
| [docs/03-resources.md](docs/03-resources.md) | Books, courses, tools, standards, and communities |
| [docs/04-learning-path.md](docs/04-learning-path.md) | Step-by-step roadmap and project ideas |
| [docs/05-study-material.md](docs/05-study-material.md) | Topic-by-topic study material: books, courses, app notes, and projects |

## Antigravity Skills (ready to use)
Optimised, on-demand skills live in [.agents/skills/](.agents/skills/):

| Skill | Use it for |
|-------|-----------|
| `pcb-design-workflow` | Whole design flow from requirements to outputs |
| `pcb-power-thermal` | Trace width, regulators, decoupling, protection, heat |
| `pcb-highspeed-rf-emc` | Impedance, USB/CAN pairs, RF and antenna, EMC |
| `uav-avionics-pcb` | Flight controllers, ESCs, PDBs, IMU/GNSS, DO-254/160 |
| `pcb-design-review` | Pre-fab checklist, DFM, bring-up plan |

**Use in a project:** copy the `.agents` folder into your project root.
**Use everywhere:** copy the five skill folders into `~/.gemini/config/skills/` (on Windows, `C:\Users\<you>\.gemini\config\skills\`).

Then ask, for example: "Design a flight controller PCB using the pcb skills."

## Quick Start

1. Learn basic electronics.
2. Install [KiCad](https://www.kicad.org/) and design a simple board.
3. Study open-source flight controllers (Pixhawk, ArduPilot hardware).
4. Order a prototype from JLCPCB or PCBWay, then test and debug it.

## License
Content is released under the MIT License. Linked resources belong to their respective owners.
