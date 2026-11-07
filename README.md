# MY-CoreXY 3D Printer

A student hardware project to build and document a CoreXY 3D printer based on the original **MY-CoreXY** design by EdgarMata.

> **Project status:** Design and planning. The current reconstructed reference assembly is for visual planning only; it is not yet a mechanically validated, manufacturing-ready CAD assembly. Exact part compatibility, dimensions, quantities and supplier prices must be checked before purchasing.

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
| `BOM/Materials-and-Cost.csv` | Preliminary category-level budget estimate |
| `CAD/` | Planned location for CAD exports model |
| `Images/` | Planned location for design screenshots and build photos |
| `Electronics/` | Planned location for wiring diagrams and controller documentation |
| `Documentation/` | Planned location for design notes, build log and test results |

Some folders may be added as the project progresses. Only files that have actually been uploaded are available in this repository.

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

## CoreXY Guardian — future extension

A possible future feature is a small monitoring system using a microcontroller and vibration sensor to record machine vibration and help identify changes that may indicate maintenance is needed. This is a planned experiment, not a completed or validated safety system.

## Funding and budget

The preliminary estimate is recorded in `BOM/Materials-and-Cost.csv`. It is a planning estimate, not a supplier quote. The listed costs, exchange rate, quantities, compatibility, shipping, customs and taxes must be verified before submitting a final funding request or placing orders.

Funding would be used only for project materials that are not already available to me. No purchases should be made on the assumption that funding is approved until the programme confirms approval.

## Safety

Mains-powered equipment, heaters and moving machinery can cause injury or fire if assembled incorrectly. Electrical design, fusing, grounding, enclosure and testing must be reviewed carefully, and the printer must not be operated unattended during early testing.

## Build log

Progress updates, CAD revisions, supplier quotations, assembly photographs and test results will be added here as the project develops.


## Electronics planning

- [Preliminary electronics plan](Electronics/ELECTRONICS-PLAN.md)
- [Electronics BOM (unselected parts and quote tracker)](Electronics/ELECTRONICS-BOM.csv)

The electronics documents are planning drafts. Exact board, drivers, motors, heaters, sensors, fans, power supply and protection must be confirmed against the final build before purchase or wiring.
