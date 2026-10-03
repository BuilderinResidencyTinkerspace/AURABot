# AURABot (Aquatic Unit for Revival & Algae-management)
# AURABot

**Aquatic Unit for Revival & Algae-management**

An open-source, autonomous pond-cleaning robot that anyone can build from locally sourced materials and simple 3D-printed parts.

**Author:** Nihaal Yoosuf

**Program:** Builder-in-Residence (BIR), sponsored by Circuit Digest

**License:** GPL-3.0 (see [`LICENSE.md`](LICENSE.md))

**Status:** Early stage. Field research is done and the design is being rethought around the core waste-collection mechanism.

---

## The problem

A local pond has gone stagnant and choked with algae. Field visits and conversations with residents turned up the following:

- **Water is trapped.** The pond's drainage outlet sits at about 8 feet, while the water is only about 5 feet deep. Water can only seep out through gaps in the surrounding stone wall, so it stagnates.
- **The algae grows from below.** It is a pond scum variety that grows from the bottom, so surface-only cleaning will not remove it.
- **There is likely waste on the bottom.** A past municipal clean-up (about five years ago, reportedly costing around 40 lakhs) was left unfinished, with sand and pebbles still in the pond.
- **The pond is alive.** Fish are still present, and people fish at its edge regularly. Earlier clean-up attempts, including a college experiment, were followed by fish deaths and an oily film on the surface, so any intervention has to protect the fish and water quality.
- **The community has stepped back.** Children used to swim here, but they stopped coming as the water got dirtier, which let it get worse still.
- **Ownership is unclear.** Locals expect the municipality's permission to be required, and some are wary of outsiders working on the pond.

## The idea

The goal is not just to drop a robot in the water and show it working. **The goal is to revive the pond as a functioning waterbody.**

- **Restore water flow.** A clean pond with no inflow and outflow will go stagnant again. Recent changes around the pond now divert surrounding water straight into a nearby drain, which was meant for the pond's overflow. Reconnecting that inflow matters as much as cleaning.
- **Build function before form.** After advice from a mentor (Kurian), the design shifted from a polished commercial-looking boat to a replicable open-source build. A large PVC pipe serves as the floating structure, with the key components mounted on top.
- **Start with the two critical systems.** The robot's main job is collecting waste, so these get designed and validated first:
  - **Conveyor mechanism:** collects and lifts waste out of the water.
  - **Waste collection bin:** receives and stores what the conveyor brings in.
- **Learn from existing designs.** The next step is to study how ClearBot's collection mechanism works, break it into components, and recreate it with accessible, locally sourced materials.

> Build the functionality first, and the product around it later.

## Open questions

- **Which algae is it?** This determines the structure and design of the robot, and the plan is to consult experts.
- **How to protect the fish and water quality** during any clean-up.
- **How to work with the local community and the municipality.**

## Hardware and tools

Not finalised yet. Current decisions:

- **Hull / floating structure:** large PVC pipe (fibreglass was considered and set aside)
- **Fabrication:** locally sourced materials plus simple 3D-printable parts
- **Core subsystems:** conveyor mechanism and waste collection bin

Boards, sensors and other electronics will be added here as they are chosen.

## Repo layout

| Folder | Contents |
| --- | --- |
| [`docs/`](docs/) | Project overview and weekly logs (built with MkDocs Material) |
| [`code/`](code/) | Firmware and scripts (to come) |
| [`cad/`](cad/) | 3D models and design files, tracked with Git LFS (run `git lfs install` once before committing) |

## Weekly logs

| Week | Highlights |
| --- | --- |
| [Overview](docs/index.md) | Project summary |
| [Week 2](docs/week-02.md) | Checked the pond's depth and spoke with a local about its history, drainage and algae |
| [Week 3](docs/week-03.md) | Field trip: measured depth, confirmed fish are alive, and raised concerns about earlier clean-up attempts |
| [Week 4](docs/week-04.md) | Reframed the objective from cleaning the pond to reviving it, including restoring water flow |
| [Week 8](docs/week-08.md) | Rethought the robot design around an open-source, PVC-based build |

Weeks 1, 5, 6, 7, 9 and 10 are not filled in yet.

## Contributing

This is an open-source project, and replicability is the point. Ideas, feedback and builds from local materials are welcome. Open an issue or a pull request.

## License

Released under the [GNU General Public License v3.0](LICENSE.md).

