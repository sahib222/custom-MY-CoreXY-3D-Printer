# Repository audit — 12 November 2026

## Scope
Reviewed the repository tree, the master and electronics BOMs, the separate materials and small-hardware sheets, README, project plan, electronics plan, journal, image index, and the original MY-CoreXY documentation pages linked below. This is a documentation/consistency audit; it is not a physical inspection or CAD fit validation.

## Overall result
**Not purchase-ready and not build-ready yet.** The repository is organised and the project status is honestly described as planning, but the source documentation itself contains conflicting machine revisions and the cost sheets overlap. Do not order components based on the current quantities or total.

## Critical design conflicts

1. **Frame profile:** the Frame BOM says 2020 extrusions with 300/350/400 mm cut lengths and 12 corner brackets. The product overview describes a 30×30 mm extrusion frame. Confirm which design revision matches the downloaded CAD/STL files.
2. **Linear rails:** the Gantry BOM lists two MGN9 300 mm rails and two MGN9H carriages; the assembly guide describes four vertical MGN9 rails; the product overview describes MGN12 rails on all axes. The total rail count/type cannot be finalised until the exact revision is identified.
3. **Z axis:** the assembly chapter describes four motorised Z-drive assemblies and four Z-idlers. The separate Z-Motion BOM lists one NEMA17 motor, one lead screw, two 8 mm rods and four LM8UU bearings. This is a direct documentation conflict. The master BOM records the four assemblies and marks the motor quantity unresolved rather than treating either source as definitive.
4. **Controller and drivers:** the electronics BOM lists one controller and five stepper drivers. The product overview names an MKS Monster 8; this project proposes an SKR Mini E3 V3.0 replacement. The proposed board has only two Z driver channels, so it cannot independently drive four Z motors. Do not assume motors can be paired; obtain the designer's intended motor grouping and electrical requirements first.
5. **Heated bed and power:** the Heat Bed BOM lists a 220×220 mm 24 V PCB bed, while the product overview mentions a 240 V heated bed. The Accessories BOM lists a 24 V 350 W supply and a 5 V buck converter. The current master sheet had different provisional power allowances. These must be resolved from the exact revision and professionally reviewed before selection or installation.
6. **Motion details:** the Z-drive assembly guide specifies four Z-drive subassemblies, each with a GT2 80T pulley, three 625 bearings, a 5×60 mm shaft, a closed-loop GT2 188 mm belt and a motor pulley. Four Z-idler assemblies are also described. These are now represented as unpriced checklist lines, with fastener counts marked as planning assumptions where the guide does not give a consolidated BOM quantity.

## Quantity checks entered in the master BOM

- Frame BOM: 4 × 300 mm, 4 × 350 mm and 4 × 400 mm extrusions; 12 corner brackets; 4 printed feet.
- Gantry BOM: 2 MGN9 300 mm rails, 2 MGN9H carriages, 5 m GT2 belt, 2 × 20T pulleys, 2 idlers and 2 A/B motors.
- Z-drive assembly chapter: 4 Z-drive assemblies, 4 Z-idler assemblies, 4 vertical rails, 4 assumed rail carriages, 4 × 80T pulleys, 12 × 625 bearings, 4 × 5×60 mm shafts, 4 × 188 mm closed-loop belts and 4 motor pulleys. The four rail-carriage and several fastener quantities are assumptions pending CAD confirmation.
- Z-Motion BOM: 1 lead screw, 1 anti-backlash nut, 1 coupler, 2 × 8 mm rods and 4 LM8UU bearings; the single-motor entry conflicts with the four motorised Z-drive assembly chapter.
- Extruder BOM: 1 pancake motor, 1 hotend, 1 dual-drive gear kit, 1 PTFE tube and 2 pneumatic fittings.
- Heat Bed BOM: 1 bed, 1 build surface, 4 springs, 4 thumbwheels and 1 printed bed support.
- Enclosure BOM: 4 panels, 2 hinges, 1 handle, 2 magnetic catches, 16 panel holders, 2 hinge mounts and 1 handle mount.
- Electronics BOM: 1 controller, 5 driver channels/modules in the original design, 3 endstops, 1 hotend thermistor, 1 heater cartridge, 2 fans and 1 wiring kit.
- Accessories BOM: 1 mains cord, 1 C14 inlet, 1 switch, 1 24 V 350 W supply, 1 5 V buck converter, 1 LED strip, 1 optional webcam and three nozzle sizes.
- Fasteners BOM: 100 M3×8, 50 M3×12, 20 M3×20, 100 M3 nuts, 50 M3 T-nuts, 50 M5×10, 50 M5 nuts and 50 M5 T-nuts. The extrusion-profile mismatch means T-nut compatibility is not yet confirmed.

## Budget audit

- The current master BOM's priced rows arithmetically add to **$785.85** (approximately **₹73,618** at the sheet's stated 1 USD = ₹93.68 reference rate). This includes a **$24.01 unitemized reconciliation allowance** added to match the user-provided parts total; it is not an independently verified component price.
- This is **not a verified project total**: broad category allowances coexist with some separately priced components, so some costs may overlap. Unpriced checklist lines are excluded.
- The Electronics BOM's $406.81 is a subsystem view of items already represented in the master BOM. **Do not add it to the master total.**
- The separate `BOM/Materials-and-Cost.csv` still has an old $500 / ₹44,000 estimate and an old illustrative ₹88 exchange rate. It is superseded and must not be used for funding totals.
- The small-hardware sheet contains TBD quantities. The master fastener rows reflect the published fastener BOM but may not cover every assembly-specific screw, insert, spacer and clip.
- Camera, touchscreen and AI monitoring are optional project additions, not base-machine requirements. AI monitoring is experimental and not a safety feature.

## Repository / evidence audit

- Present: root BOM, Electronics BOM and plan, project plan, journal, README, one overall design-reference WebP, and two CAD ZIP archives.
- CAD directory contains `MY-CoreXY.zip` and `MY-CoreXY-Full-Assembly.zip`. There is **no STEP file** in the current repository tree. The previous generated faceted STEP was not validated as a correctly positioned assembly and failed Onshape translation; do not describe it as a verified assembly.
- Images directory currently contains only `ME_-_Core_XY_03.webp` and an image README. The three separate screenshots previously discussed are not in this repository.
- JOURNAL.md repeats the same overall design reference image for multiple entries. It is clearly labelled as a reference, not build evidence, but it does not yet satisfy a genuine per-entry progress-photo requirement.
- The journal currently covers 30 October, 3 November, 6 November and 7 November 2026. Add later entries only for work actually completed, and attach real dated evidence.
- No verified PCB schematic/layout/Gerbers, complete wiring diagram, tested Klipper configuration, assembled STEP CAD, physical build photographs or test-print evidence are present in the current tree.

## Required next actions before purchasing

1. Identify the exact revision represented by the downloaded CAD archive; compare its frame profile, rail sizes, Z drive and bed to the current official docs.
2. Ask the designer to resolve the 2020/3030, MGN9/MGN12, one/four Z motor and 24 V/240 V bed conflicts.
3. Select the controller only after the motor/driver mapping is confirmed.
4. Rebuild the BOM from the chosen revision, with each part appearing once, exact supplier SKUs, dated quotes, shipping, taxes and a non-overlapping total.
5. Have the mains power, heated-bed arrangement, grounding, fusing and enclosure reviewed and installed by a qualified adult electrician.
6. Validate the CAD assembly in a real CAD system and record the exact source file/revision. Do not use the current STEP export as a manufacturing drawing.
7. Add authentic CAD screenshots, separate progress images, wiring documentation, firmware/configuration and test results as they are completed.

## Primary sources checked

- Product overview: https://my-machines.com/my-corexy-3d-printer
- Frame BOM: https://docs.my-machines.com/3d-printers/my-corexy/bom/frame/
- Gantry BOM: https://docs.my-machines.com/3d-printers/my-corexy/bom/gantry/
- Z-Motion BOM: https://docs.my-machines.com/3d-printers/my-corexy/bom/z_motion/
- Z-drive assembly: https://docs.my-machines.com/3d-printers/my-corexy/assembly/02-z-drives-and-idlers/
- Extruder BOM: https://docs.my-machines.com/3d-printers/my-corexy/bom/extruder/
- Heat Bed BOM: https://docs.my-machines.com/3d-printers/my-corexy/bom/heat_bed/
- Enclosure BOM: https://docs.my-machines.com/3d-printers/my-corexy/bom/enclosure/
- Electronics BOM: https://docs.my-machines.com/3d-printers/my-corexy/bom/electronics/
- Accessories BOM: https://docs.my-machines.com/3d-printers/my-corexy/bom/accessories/
- Fasteners BOM: https://docs.my-machines.com/3d-printers/my-corexy/bom/fasteners/
- Hardware reference: https://docs.my-machines.com/3d-printers/my-corexy/operation/introduction/hardware-reference/
