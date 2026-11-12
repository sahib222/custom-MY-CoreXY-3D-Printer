# MY-CoreXY Build Plan

## 1. Purpose

Build and document a functional MY-CoreXY CoreXY 3D printer as a student hardware project. The build will follow the original design architecture and use verified compatible components.

## 2. Current status

- Original design identified: MY-CoreXY by EdgarMata.
- 3D reference assembly and source part files have been collected.
- Preliminary material categories and budget estimate have been added to the repository.
- Exact component specifications, supplier quotes and mechanical fit still need verification.
- A full repository/source audit is recorded in [AUDIT-REPORT.md](AUDIT-REPORT.md); key design conflicts block purchasing.
- No claim is made that the printer is already assembled or operational.

## 3. Work packages

### A. CAD verification
- Compare the assembly against the original assembly guide.
- Check frame dimensions, rail lengths, belt path, Z-drive arrangement and toolhead interfaces.
- Mark any reconstructed or approximate geometry.
- Do not manufacture parts from unverified geometry.

### B. Bill of materials
For every item, record:
- Component name and exact specification
- Quantity
- Supplier and product URL
- Unit price and shipping
- Compatibility notes
- Whether it is already owned, available locally or needs funding

### C. Printed parts
- Identify the exact printable parts from the source files.
- Confirm material requirements and print orientation/settings from reliable design documentation.
- Track printed, inspected and rejected parts.

### D. Mechanical assembly
- Assemble and square the frame.
- Install rails, gantry, belts, pulleys and Z-motion components according to the design.
- Check smooth movement and alignment before powering motors.

### E. Electronics and commissioning
- Keep the BIGTREETECH SKR Mini E3 V3.0 as an unverified candidate only. The official sources conflict on Z-motor count/grouping and controller choice. Resolve the exact revision and motor-driver mapping before selecting a board.
- Verify electrical ratings, grounding, fusing and enclosure before connecting power.
- Configure firmware and test motion in a controlled, supervised manner.
- Calibrate and perform documented test prints.

### F. Optional CoreXY Guardian
After the printer works reliably, investigate vibration sensing and a dashboard for maintenance observations. This feature is experimental and will not replace normal inspection or safety protections.

## 4. Budget approach

The current master BOM arithmetic total is unverified and may contain overlapping category allowances. The Electronics BOM is a subsystem breakdown and must not be added to it. Replace estimates with itemised, dated supplier quotations after the design revision is confirmed. See [AUDIT-REPORT.md](AUDIT-REPORT.md). Confirm shipping, taxes and customs separately.

## 5. Evidence to collect

- CAD screenshots and revision history
- Original design references and attribution
- Itemised BOM and supplier quotations
- Printed-part photographs
- Assembly progress photographs
- Wiring diagram and component datasheets
- Firmware/configuration notes
- Calibration and test-print results
- Problems encountered and changes made

## 6. Completion criteria

The project is complete when the printer has a verified mechanical assembly, reviewed electrical system, safe supervised commissioning, documented calibration and repeatable successful test prints. The optional Guardian feature is a separate stretch goal.
