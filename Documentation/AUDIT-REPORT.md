# Repository audit — updated 23 November 2026

## Scope
Reviewed the repository tree, master and electronics BOMs, separate materials and small-hardware sheets, README, project plan, electronics plan, journal, image index, and original MY-CoreXY documentation. This is a documentation/consistency audit, not a physical inspection or CAD fit validation.

## Overall result
**Not purchase-ready or build-ready.** The source documentation contains conflicting machine revisions and cost sheets may overlap. Do not order components from the current estimates.

## Critical design conflicts
1. **Frame profile:** Frame BOM lists 2020 extrusions; product overview describes a 30×30 mm frame. Confirm the CAD revision.
2. **Linear rails:** Gantry BOM lists two MGN9 300 mm rails and two MGN9H carriages; assembly guide describes four vertical MGN9 rails; product overview describes MGN12 rails on all axes.
3. **Z axis:** Assembly chapter describes four motorised Z-drive assemblies and four Z-idlers. Separate Z-Motion BOM lists one NEMA17 motor, one lead screw, two 8 mm rods and four LM8UU bearings. This remains unresolved.
4. **Controller:** The proposed SKR Mini E3 V3.0 has only two Z driver channels and cannot independently drive four Z motors. Confirm intended motor grouping before claiming compatibility.
5. **Heated bed and power:** Heat Bed BOM lists a 220×220 mm 24 V PCB bed; product overview mentions a 240 V bed. Accessories BOM lists a 24 V 350 W supply. Resolve and professionally review the electrical architecture before selection.
6. **A/B drive hardware:** Bearing, shim and fastener counts remain TBD pending exact CAD/exploded-view verification.

## Quantity checklist
The master BOM records the published quantities for frame extrusions, gantry rails/belts/pulleys, Z-drive assemblies, extruder, bed, enclosure, electronics, accessories and fasteners. Rows with blank quantities/prices are checklist items, not priced purchases. Some counts remain assumptions and require the exact CAD revision.

## Budget audit

**Unit-price update (23 November 2026):** Indicative unit-price references are recorded for many non-filament components. Optional camera, touchscreen, runout sensor, LED strip, extra nozzles and unitemized reconciliation allowance have been removed from the active BOM. Zero-quantity separate driver and 5 V PSU rows have also been removed because the proposed controller has onboard driver interfaces and the accessory BOM specifies a DC-DC buck converter. These are a mix of supplier-listed reference prices and provisional allowances, not confirmed quotes. Their line totals are intentionally left blank because many parts are already covered by broad category allowances; adding them again would double-count the budget. All 3D-printed parts, filament and printing costs are excluded from the active BOM and budget. Rows with unknown dimensions, unresolved design revision or TBD quantities still need confirmation.

- After removing overlapping category-level allowance prices, the remaining priced purchase rows in `BOM.csv` total **$665.62 USD** (approximately **₹61,675** at the repository's stated reference conversion of 1 USD = ₹92.68).
- All printed-part rows, filament, and print electricity have been removed from the active BOM. The budget covers purchased components only; no 3D-printing cost is included.
- The unitemized $24.01 reconciliation allowance has been removed because it did not represent a verified component or supplier quote.
- Category-level allowance rows for frame, motion, drive, toolhead, build platform and fasteners are retained as unpriced headings because their detailed component rows are separately listed. The subtotal is provisional and not purchase-ready.
- The separate print-cost worksheet has been removed because the project budget intentionally excludes printed parts, filament and printing electricity.
- The Electronics BOM is a subsystem view of items already represented in the master BOM; do not add its subtotal again.
- The old `BOM/Materials-and-Cost.csv` estimate is superseded and must not be used as the current budget.

## Evidence and CAD
- The repository contains two CAD ZIP archives but no verified STEP assembly.
- The existing design image is a reference, not a photo of a completed printer.
- No verified PCB schematic/Gerbers, complete wiring diagram, tested Klipper configuration, validated assembled STEP, physical build photos or test-print evidence are present.
- Add journal entries only for work actually completed, with genuine evidence where available.

## Required next actions
1. Identify the exact CAD revision and resolve frame, rail, Z-drive and bed conflicts.
2. Confirm controller motor/driver mapping.
3. Replace category allowances with dated supplier quotations and avoid double counting.
4. Determine filament material and grams from the final printed-part list and slicer; only then add a filament price if requested.
5. Have mains power, heated-bed arrangement, grounding, fusing and enclosure reviewed by a qualified adult electrician.
6. Validate the assembly in a CAD system and record the exact source revision.
7. Add authentic CAD screenshots, build photos, wiring documentation, firmware configuration and test results as completed.

## Primary sources
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


## Optional-item cleanup — 23 November 2026

Removed the optional USB monitoring camera and its webcam holder, touchscreen and its mounting hardware, AI monitoring software placeholder, filament runout sensor, LED strip, 0.6 mm and 0.8 mm optional nozzles, zero-quantity separate stepper-driver modules, zero-quantity separate 5 V PSU, and the unitemized reconciliation allowance. The standard 0.4 mm nozzle, essential controller/electronics, frame, motion, bed, enclosure and safety-related line items remain. The touchscreen/camera features can be added later if the selected controller/host and budget justify them.

The cleaned master BOM subtotal is a planning estimate for purchased components only, not a verified purchase quote. The Hack Club form's 34 flagged rows cannot be individually corrected from the supplied screenshot alone: it shows the count and one visible missing-price row, not the other 33 line items. The repo cleanup does not submit or alter the Hack Club form.


## 3D-printed parts and print-cost exclusion — 23 November 2026

At the user's request, removed every 3D-printed part line from the active master BOM, including frame, gantry, Z-motion, extruder, bed, enclosure, electronics, accessory and Z-drive/Z-idler printed assemblies. Removed the filament-for-printed-components and printing-electricity lines, removed the printed-components entry from the materials sheet, and deleted `BOM/Printing-Cost.csv`. The BOM now represents purchased components only. The priced-row subtotal was subsequently recalculated to $665.62 after clearing overlapping category-level allowance prices; it must not be interpreted as including printed parts or filament.
