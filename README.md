# MY-CoreXY 3D Printer

A student hardware project to build and document a CoreXY 3D printer based on the original **MY-CoreXY** design by EdgarMata.

> **Project status:** Design and planning. The current reconstructed reference assembly is for visual planning only; it is not yet a mechanically validated, manufacturing-ready CAD assembly. Exact part compatibility, dimensions, quantities and supplier prices must be checked before purchasing.

## About

MY-CoreXY is a CoreXY-style 3D printer project based on the design by EdgarMata. The machine uses a rigid aluminium-extrusion frame, belt-driven CoreXY movement for the X/Y axes, a fixed build platform and a gantry that moves along the Z axis. This repository documents the process of understanding the original design, checking its parts and electronics, preparing a bill of materials, and working towards a safe, tested build.

This is an independent student build and learning project, not the official MY-Machines product. The current project is still in the design and planning stage; final dimensions, component choices and assembly details must be verified before construction.

## Project goals

- Build a working CoreXY 3D printer while learning mechanical design, CAD, electronics and fabrication.
- Preserve the original MY-CoreXY architecture: CoreXY XY motion, a fixed build plate and a Z-moving gantry.
- Document the mechanical design, electronics, bill of materials (BOM), assembly and testing.
- Explore a future **CoreXY Guardian** add-on for monitoring vibration and machine condition.

## Design reference and credit

This project is based on the original MY-CoreXY 3D Printer design by **EdgarMata**.

- Original project: https://www.printables.com/model/132032-my-core-xy-3d-printer
- Assembly documentation: https://docs.my-machines.com/3d-printers/my-corexy/assembly/

The original designer and source project are credited. This repository is for documenting my own build planning, learning, testing and clearly identified modifications. Please check the original project's licence and terms before redistributing or manufacturing its files.

## Repository contents

| Path | Contents |
|---|---|
| `BOM.csv` | Preliminary category-level budget estimate |
| `CAD/` | CAD models and exports |
| `Images/` | Planned location for design screenshots and build photos |
| `Electronics/` | Planned location for wiring diagrams and controller documentation |
| `Documentation/` | Planned location for design notes, build log and test results |

Some folders may be added as the project progresses. Only files that have actually been uploaded are available in this repository.

## Images

### Overall MY-CoreXY design reference

![MY-CoreXY printer design reference](Images/ME_-_Core_XY_03.webp)

*CAD-style design reference supplied for this project. It shows the intended printer layout; it is not a photograph of a completed build.*

Additional full-model CAD screenshots, electronics layout, schematic and wiring-diagram images will be added when those files are ready. See [Images/](Images/) for image assets and [JOURNAL.md](JOURNAL.md) for dated progress notes.

## Main subsystems

1. **Frame:** aluminium extrusion structure and fasteners.
2. **XY motion:** CoreXY belts, pulleys, idlers, rails and gantry.
3. **Z motion:** Z guides and drive components that move the gantry.
4. **Build platform:** fixed build plate and its support structure.
5. **Toolhead:** compatible extruder and hotend assembly.
6. **Electronics:** controller, motor drivers, power supply, wiring and safety components.

Exact specifications and quantities will be recorded in the BOM after checking the source design and selected components.

## Planned development

- [ ] Verify the CAD assembly against the original design and assembly documentation.
- [ ] Confirm every purchased component's dimensions and compatibility.
- [ ] Complete an item-by-item BOM with supplier quotations and shipping costs.
- [ ] Finalise electronics architecture and wiring documentation.
- [ ] Print and inspect the required plastic parts.
- [ ] Assemble the frame and motion systems.
- [ ] Complete electrical checks and firmware configuration.
- [ ] Run initial motion, calibration and print tests.
- [ ] Document results, problems and improvements.
- [ ] Evaluate the optional CoreXY Guardian monitoring add-on.
- [ ] Integrate a compatible camera for remote print monitoring.
- [ ] Add a compatible touchscreen for local control.
- [ ] Evaluate AI-assisted print-failure detection; treat it as an advisory feature, not a safety system.

## Smart monitoring and user interface — planned features

The planned upgrade set includes a compatible camera for remote viewing, a touchscreen for local status and control, and optional AI-assisted analysis of camera images to flag possible print failures. These features are not yet implemented or validated. AI alerts are advisory only and must never replace supervision, thermal protections or other hardware safety systems.

## CoreXY Guardian — future extension

A possible future feature is a small monitoring system using a microcontroller and vibration sensor to record machine vibration and help identify changes that may indicate maintenance is needed. This is a planned experiment, not a completed or validated safety system.


## Bill of materials (USD planning estimate)

The itemised master BOM is [BOM.csv](BOM.csv) in the repository root. It includes estimated prices in USD, supplier search links, small hardware (screws, nuts, T-nuts, washers, inserts and cable-management items), a separate shipping allowance, and a total including shipping. **These are budget estimates, not live quotations or confirmed compatible selections.** Several source-design details remain unresolved (especially Z-motor driver grouping, controller revision, power-supply sizing and heated-bed arrangement). Check specifications, current seller prices, GST and delivery before ordering. Mains-powered parts and wiring must be reviewed by a qualified adult electrician.

## Funding and budget

The current preliminary total is approximately **$781.06 USD**, including the planned camera and touchscreen additions. The BOM uses a reference conversion of **1 USD = 93.68 INR (12 November 2026)**. This is a planning estimate, not a supplier quote. Prices, exchange rates, quantities, compatibility, shipping, customs and taxes must be verified before submitting a final funding request or placing orders.

Funding would be used only for project materials that are not already available to me. No purchases should be made on the assumption that funding is approved until the programme confirms approval.

## Safety

Mains-powered equipment, heaters and moving machinery can cause injury or fire if assembled incorrectly. Electrical design, fusing, grounding, enclosure and testing must be reviewed carefully, and the printer must not be operated unattended during early testing.

## Build log

Progress updates, CAD revisions, supplier quotations, assembly photographs and test results will be added here as the project develops.


## Electronics planning

- [Preliminary electronics plan](Electronics/ELECTRONICS-PLAN.md)
- [Electronics BOM (unselected parts and quote tracker)](Electronics/ELECTRONICS-BOM.csv)

The planned controller is the **BIGTREETECH SKR Mini E3 V3.0**. It has five onboard TMC2209 driver interfaces and documented Klipper support. This is a replacement candidate, not the original board specified by the MY-CoreXY source. The official assembly guide confirms four Z-drive motors. The board has only two Z driver channels, so the original motor grouping and current requirements must be confirmed before compatibility can be claimed. See [Electronics/ELECTRONICS-PLAN.md](Electronics/ELECTRONICS-PLAN.md).
