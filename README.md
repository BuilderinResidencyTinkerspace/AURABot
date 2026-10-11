# AURABot

**Aquatic Unit for Revival and Algae-Management**

An open-source pond-cleaning robot built from PVC pipe and locally available parts. Work in progress.

**Author:** Nihaal Yoosuf

**Program:** Builder in Residence (BIR) at Tinkerspace, Kochi, sponsored by Circuit Digest

**License:** GPL-3.0 (see [`LICENSE.md`](LICENSE.md))

**Status:** Prototype only. The two hulls and the conveyor frame are built. Propulsion, electronics and the collection bin are not.
![photo](https://github.com/BuilderinResidencyTinkerspace/AURABot/blob/main/docs/photos/prototype-assembled-02oct.jpg)

There is a pond close to the Tinkerspace facility in Kochi that nobody uses any more. The water is stagnant, a green mat covers part of the surface, and litter has collected in it. Children used to swim here until the water got dirty. About five years ago the municipality started a clean-up that reportedly cost 40 to 50 lakh rupees, and it was left unfinished.

I started this project to build a robot that could clean that pond. My first plan was to skim the surface and also pick up waste from the bottom. After talking to residents and a few experts, I understood the project has turned much complex than when I started. Fish still live in the pond, and an earlier clean-up experiment by a group of college students was followed by a fish die-off. So AURABot became a technology to revive the pond rather than a surface skimming robot. This project needed an intensive research and would go well beyond the cohort's 10 week timeline. As I am new to such a project, I underestimated the timeline and committed to solve the whole problem within 10 weeks. But it took about 6 or 7 weeks for me to realize the depth of the situation. So, for the last 2 or 3 weeks, I decided to build a surface collector only to present for the demo day: a conveyor belt between two PVC pipe hulls that lifts floating litter and weed out of the water and into a bin.

At the demo on 20 September 2026 I had the two hulls and a conveyor with its belt. There was no propulsion, no electronics and no collection bin, and the robot had never touched water. This page records what was built, what went wrong and what is still to do, so the next person can start further along than I did.

## Table of contents

- [The pond](#the-pond)
- [Why the robot only works at the surface](#why-the-robot-only-works-at-the-surface)
- [What is built and what is not](#what-is-built-and-what-is-not)
- [Components](#components)
- [How it is meant to work](#how-it-is-meant-to-work)
- [How the frame was built](#how-the-frame-was-built)
- [Challenges faced](#challenges-faced)
- [Open questions](#open-questions)
- [Future improvements](#future-improvements)
- [Repo layout](#repo-layout)
- [Weekly logs](#weekly-logs)
- [Contributing](#contributing)
- [Acknowledgements](#acknowledgements)
- [License](#license)

## The pond
![photo](https://github.com/BuilderinResidencyTinkerspace/AURABot/blob/main/docs/photos/pond%20pic.jpg)
Most of these numbers come from my own visits, using a stone tied to a fishing line and measurements on a map.

- The pond is about 25 m by 25 m, which is roughly 625 m².
- The water is about 5 feet (157 cm) deep at the places I could reach. The middle may be deeper.
- The drainage outlet sits at about 8 feet, so the water never reaches it. The only way water leaves is by seeping through gaps in the stone wall around the pond.
- Fish are still alive. People fish from the bank, and residents say the fish grow to 30 to 35 cm.
- The municipality's clean-up five years ago was stopped by a flash flood, which left some equipment in the pond. Sand and pebbles from that job are still there.
- Water from around the pond is now routed straight into a nearby drain instead of through the pond. Cleaning alone will not keep the pond clean while nothing flows through it. Fixing that is a separate job from this robot, but it matters just as much.
- Locals expect the municipality to be involved, so permission has to be sorted out before any water test.

## Why the robot only works at the surface

Residents told me that a group of college students once experimented on this pond. About two days later many fish died, and an oily film was seen on the water. I do not know what they did or what killed the fish. One explanation I considered is that disturbing the bottom released hydrogen sulphide that had built up in the mud of a pond that never drains. I have not tested for it, and the oily film points to other possible causes, so this is a guess and not a finding. The design rule that came out of it is simple: stay at the surface and do not touch the bottom.

I have also not identified the algae. The green mat I pulled from the edge floats and feels like grass. A local told me it grows from the bottom, but I could not check, because the water is too far below the bank to reach the weeds and do a pull test. A research scholar from the Marine Biology department at CUSAT suggested starting with the floating weeds and the microalgae and leaving the rooted plants for later. I still want to ask her whether even that is safe for the fish.

## What is built and what is not

| Part | Status |
| --- | --- |
| Two PVC hulls with end caps, joined by PVC cross pipes | Built |
| Conveyor frame (two aluminium side rails at 30 degrees) | Built |
| Two PVC rollers on four ball bearings | Built |
| Mesh belt with timing-belt grip | Fitted, but it moves stiffly |
| Paddle propulsion | Not built |
| Collection bin | Not built |
| Electronics and firmware | Draft only, never run on the robot |
| Test in water | Not done |

## Components

This is the parts list as it stands. The last column says what has actually been fitted.

| S.no | Component | Used for | Qty | Status |
| --- | --- | --- | --- | --- |
| 1 | 110 mm PVC pipe with end caps | Hulls | 2 | Built |
| 2 | PVC pipe | Cross pipes between the hulls | as needed | Built |
| 3 | Aluminium channel (base of a flex banner stand) | Conveyor side rails | 2 | Built |
| 4 | PVC pipe, about 40 cm wide, with end caps | Conveyor rollers | 2 | Built |
| 5 | Ball bearings | Roller supports | 4 | Fitted |
| 6 | Plastic mesh net | Belt | 1 | Fitted |
| 7 | Timing belt, cut to length | Grip between the roller and the mesh | 1 | Fitted |
| 8 | Orange 12 V 100 RPM geared motor | Conveyor roller and the two paddles | 3 to 4 | Not fitted |
| 9 | Paddles with long blades | Propulsion | 2 | Not built |
| 10 | Plastic or mesh bin | Collecting waste | 1 | Not built |
| 11 | ESP32 DevKit V1 | Controller | 1 | Not fitted |
| 12 | Motor drivers (BTS7960 or L298N) | Driving the motors | 2 to 3 | Not fitted |
| 13 | 12 V battery (LiPo or sealed lead-acid) | Power | 1 | Not decided |
| 14 | Buck converter, fuse, power switch, emergency stop button | Power and safety | 1 each | Not fitted |

The Orange motors were already available at Tinkerspace. Sellers list them at roughly 10 to 12 kg-cm of rated torque.

## How it is meant to work

**Hull.** Two 110 mm PVC pipes with caps on both ends float the robot, and PVC cross pipes join them. A mentor advised me to stop trying to build a finished-looking boat and use plain plumbing pipe, so that anyone can copy the build with parts from a local shop.

![photo](https://github.com/BuilderinResidencyTinkerspace/AURABot/blob/main/docs/photos/week-09-frame-parts-11sep.jpg)

**Conveyor.** A mesh belt runs over two PVC rollers, about 40 cm wide, held between two aluminium side rails at 30 degrees. The lower end is meant to sit just under the water surface. As the belt turns, floating litter and weed ride up it and fall into a bin at the top. Only the top roller is driven, and the bottom roller just turns freely. A strip of timing belt is stuck under the mesh and around one roller so that the roller can drive the mesh without slipping.

**Propulsion.** Two paddles, one on each side, each driven by an Orange motor. I first wanted propellers, but the motors cannot go under water. Keeping the motor on the boat and the blades under water at an angle needs universal joints, which I could not find locally and which were too much work for the deadline.

**Control (planned).** The ESP32 creates its own WiFi hotspot, so no router is needed at the pond. You join it with a phone and drive from a web page with a joystick. The firmware draft stops all motors if no command arrives for 1.5 seconds, and it has an input for a physical emergency stop button. It was written for an earlier layout of the robot, with a surface brush, a comb roller and a depth actuator, so it needs changing for one conveyor motor and two paddle motors. It has not been run on hardware. Part of the sizing work and this draft were done with an AI assistant, and none of it has been checked on the real robot.

## How the frame was built

1. I first cut two horizontal bars from 1-inch hollow steel pipe with a hand-held cut-off saw, and drilled holes in them so U-clamps could hold the PVC hulls on both sides.
2. For the conveyor's side rails I used the bottom part of a flex banner stand. It was light and the right shape, but aluminium cannot be welded to steel pipe, so I stacked 1-inch steel pipes into a frame about 7 cm thick instead. A Tinkerspace staff member who is trusted with the power tools helped me with this.
3. I marked the 30 degree angle with a protractor and cut the angled piece by hand. As a beginner this took far longer than I expected.
4. I bought four ball bearings and found that their rubber seals would melt if I welded them. So welding the bearings to the pipes was out.
5. The steel frame also turned out too heavy. Carrying it would have meant bigger hulls. I went back to the aluminium rails for the demo and replaced the steel cross pipes with PVC.
6. I cut the aluminium rails to the size of the bearings so each bearing sits partly inside, and fixed them with hot glue.
7. Each roller is a PVC pipe about 40 cm wide. Its end caps are drilled so smaller, shorter pipes pass through them and into the bearings.
8. I fitted the mesh net as the belt, and stuck the timing belt under it and around one roller. Then I tied the whole conveyor to the PVC cross pipes.
![photo](https://github.com/BuilderinResidencyTinkerspace/AURABot/blob/main/docs/photos/week-10-roller-with-bearings-19sep.jpg)
## Challenges faced

- **Weight.** The steel pipe frame was too heavy for PVC hulls of a sensible size. Weight was the main reason the steel was replaced.
- **Joining different materials.** Aluminium will not weld to steel, and welding heat would destroy the bearing seals. In the end I used glue, which is not a good long-term fix.
- **Cutting the angle.** Cutting a 30 degree piece by hand with a power saw was slow, and I had to learn how to do it without damaging the tool or hurting myself.
- **Belt friction.** The belt moves with difficulty. My guess is that the adhesive I used to stick the timing belt to the mesh made the mesh stiff, and that I attached it to the roller unevenly. I have not confirmed this.
- **Time.** I underestimated how long the frame would take, and I managed my time badly. This is why nothing else was fitted at the demo.
- **Reaching the water.** The water is too far below the bank to reach the weeds, so I could not do a pull test or take a good sample.
- **Identifying the algae.** The design depends on what the algae and weed actually are, and I still do not know.

## Open questions

- Which algae or plant is it, and is it rooted or floating?
- Is removing floating weed safe for the fish, and how should oxygen be monitored while doing it?
- Was a disturbed bottom layer behind the earlier fish deaths, or something else, like the oil?
- How to get the municipality's permission, and how to bring water flow back to the pond.

## Future improvements

- Fix the belt friction, probably by attaching the timing belt evenly with a thinner or more flexible adhesive.
- Add raised rubber strips across the belt. Round objects like bottles roll back down a smooth slope, so the belt needs something to hold them.
- Build and fit the paddles, the motors and the collection bin.
- Fit the electronics and adapt the firmware to the real layout.
- Test in a tub first, then at the pond edge, before any real run.
- Try a small trial patch with a dissolved oxygen test kit, watching the fish the whole time.
- Get the algae identified by an expert.
- Later, add obstacle sensing and automatic coverage of a zone. This is not part of the current work.


## Repo layout

| Folder | Contents |
| --- | --- |
| [`docs/`](docs) | Project overview and weekly logs (built with MkDocs Material) |
| [`code/`](code) | Draft ESP32 firmware, untested |
| [`cad/`](cad) | 3D models and design files, tracked with Git LFS (run `git lfs install` once before committing) |

## Weekly logs

| Week | Highlights |
| --- | --- |
| [Overview](docs/index.md) | Project summary |
| [Week 1](docs/week-01.md) | Cohort kickoff, facility tour and the first idea |
| [Week 2](docs/week-02.md) | Checked the pond's depth and spoke to a local about its history, drainage and algae |
| [Week 3](docs/week-03.md) | Field trip: measured depth, confirmed fish are alive, heard about the earlier experiment |
| [Week 4](docs/week-04.md) | Changed the goal from cleaning the pond to reviving it, including water flow |
| [Week 7](docs/week-07.md) | Found Clearbot as a reference, visited CUSAT, looked for parts, first PVC prototype |
| [Week 8](docs/week-08.md) | Rethought the design around an open-source PVC build |
| [Week 9](docs/week-09.md) | Built the steel pipe conveyor frame |
| [Week 10](docs/week-10.md) | Switched to aluminium and PVC, built rollers and belt, demo on 20 September |

## Contributing

This is an open-source project and replicability is the point. Ideas, feedback and builds from local materials are welcome. Open an issue or a pull request.

## Acknowledgements

Thanks to Circuit Digest and TinkerHub for sponsoring the cohort and giving me room to try something this hard, and to Shan, who runs the cohort. Thanks to Kurian for the advice on the hull, to the research scholar at CUSAT's Marine Biology department for her time, to the Tinkerspace staff who helped with the power tools, and to the people who live beside the pond for telling me its history.

## License

Released under the [GNU General Public License v3.0](LICENSE.md).
