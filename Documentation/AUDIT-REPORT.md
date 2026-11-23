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

**Unit-price update (23 November 2026):** 67 previously blank non-filament component rows in the master BOM now have indicative USD unit-price estimates and supplier reference links. Eight additional rows were priced in the latest pass. These are a mix of supplier-listed reference prices and provisional allowances, not confirmed quotes. Their line totals are intentionally left blank because many parts are already covered by broad category allowances; adding them again would double-count the budget. Filament and printed-part material remain unpriced, as requested. Rows with unknown dimensions, unresolved design revision or TBD quantities still need confirmation.

- The current priced rows in `BOM.csv` total **$755.43 USD** (approximately **₹70,013** at the repository's stated reference conversion of 1 USD = ₹92.68).
- The filament row is now **unpriced**: material is listed, but quantity and cost are blank/TBD. No printing cost has been added to the master BOM subtotal.
- The subtotal retains a **$24.01 unitemized reconciliation allowance** from the earlier user-provided target. It is not a verified component price.
- Some broad category allowances may overlap with individual priced rows. Unpriced checklist lines are excluded. The subtotal is provisional and not purchase-ready.
- The separate `BOM/Printing-Cost.csv` worksheet is not included in the master subtotal. Do not add its calculations until actual slicer data is available and any overlap is reconciled.
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
