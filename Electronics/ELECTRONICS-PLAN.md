# Electronics Plan — MY-CoreXY

> **Status: research-based draft, not a purchase-ready design.** I compared the MY-CoreXY product page, its electronics BOM and wiring chapters. Those sources contain conflicting board and power details, so the unresolved items below are deliberately marked for verification. Do not buy parts or wire the printer from this draft alone.

## 1. What the MY-CoreXY sources currently say

| Subsystem | Source information | Confidence / action |
|---|---|---|
| Main controller | The MY-CoreXY product page names **Makerbase MKS Monster8** and says the printer uses Klipper (Marlin is also mentioned). | Listed by the product page, but confirm exact board revision and MCU before purchase. |
| Stepper drivers | The MY-CoreXY electronics BOM lists **5 drivers**, with **TMC2209 or similar** as an example. The controller-setup chapter also describes TMC2209 in UART mode. | Source-listed example; confirm driver count, exact driver version and board compatibility. |
| Host computer | The component-mounting chapter shows a **Raspberry Pi** mounted as the Klipper host. | Source-listed; exact Pi model and storage are not specified in the BOM. |
| DC power | The mounting chapter gives **Mean Well RS-25-5 (or similar)** for 5 V and **Mean Well LRS-200-24 (or similar)** for 24 V. | Source-listed examples, but the product page and accessories BOM describe different power arrangements. Do not order until the complete load and heater configuration are confirmed. |
| Mains / bed power | The product page says **24 V system with a 240 V heated bed**. The wiring chapter describes an SSR for an AC heated bed. | Important unresolved design detail. Mains-side selection, installation and inspection require a qualified adult electrician. |
| Hotend heater / sensor | The electronics BOM lists a **24 V, 40 W heater cartridge** and a **100 kΩ NTC hotend thermistor**. | Generic BOM specification; verify against the exact hotend and sensor model. |
| Fans | The electronics BOM lists two cooling fans, examples **4010 or 5015**. | Quantity/type need checking against the actual EVA toolhead and enclosure. |
| Endstops | The electronics BOM lists **3 endstop switches**. The mounting chapter describes X, Y and Z endstops. | Source-listed; confirm switch type and final homing design. |
| Printed electronics parts | Controller box (1), controller-box lid (1), fan holder (2). | Listed in the electronics BOM. |

## 2. Conflicts that must be resolved before buying

1. **Controller-board mismatch:** the product page names MKS Monster8; the electronics BOM gives SKR Pro / Duet 3 as examples; the mounting chapter gives BigTreeTech Octopus as an example. These are not interchangeable without checking the actual wiring, pin map, firmware and mounting.
2. **Power-system mismatch:** the product page describes a 24 V system and 240 V bed; the accessories BOM lists a 24 V 350 W supply; the wiring chapter describes an LRS-200-24 plus an AC-bed SSR and a separate 5 V supply. Confirm which revision of the machine and bed is represented by the CAD you are building.
3. **Driver / motor count mismatch:** the electronics BOM lists five drivers, while the DC-wiring chapter describes four Z-motor connections as well as A/B and extruder motors. The Z-motion BOM lists one Z motor. The actual motor count must be checked against the exact model and assembly revision.
4. **Board naming detail:** the product page's controller section names MKS Monster8 but a nearby feature heading refers to MKS DLC32. Confirm the actual product and board revision from the designer's current build files.

## 3. Working electronics checklist

| Item | Preliminary quantity / specification | Status |
|---|---|---|
| Mainboard | MKS Monster8 is the product-page reference | Verify revision, pinout and firmware target |
| Stepper drivers | 5 listed; TMC2209 example | Verify count and exact model |
| Raspberry Pi / Klipper host | 1 host shown in mounting guide | Confirm model and storage |
| 5 V supply | RS-25-5 example | Verify load and approved supply |
| 24 V supply | LRS-200-24 example | Verify total DC load; conflicting 350 W listing exists |
| Hotend heater | 24 V, 40 W listed | Verify against chosen hotend |
| Hotend thermistor | 100 kΩ NTC listed | Verify exact sensor curve/type |
| Fans | 2 listed; 4010 / 5015 examples | Verify voltage, current, airflow and mounting |
| Endstops | 3 listed | Verify type and axis arrangement |
| Bed heater / SSR | AC bed and SSR mentioned in wiring guide | Do not select or install until bed design is confirmed by the designer and qualified electrician |
| Wiring / connectors | By actual circuit requirements | Must be specified from datasheets and reviewed |
| Protective devices / isolation | By qualified electrical design | Not yet selected |
| Controller enclosure / lid / fan holders | 1 / 1 / 2 | Printed parts listed by source |

## 4. Firmware and compatibility

- Klipper is the primary firmware direction described by the product page; Marlin is also mentioned as supported.
- The controller's exact MCU, bootloader, communication method and pin map must be confirmed before creating a firmware configuration.
- Driver mode and jumper positions depend on the exact board revision. Do not copy jumper positions from another board.
- The final configuration must match the real motor count, endstop locations, thermistor model, heater outputs and fan voltage.

## 5. Safety boundary

This repository is a student project. Mains-powered supplies, AC heated beds, grounding, fusing and isolation must be specified, installed and inspected by a qualified adult electrician. Do not open power-supply cases or work on live equipment. Keep all hazardous connections enclosed. Do not operate heaters until sensor compatibility, firmware limits and independent thermal protections have been professionally checked.

This document intentionally does **not** provide a mains wiring procedure or a ready-to-use wiring diagram.

## 6. Verification checklist before a purchase list can be finalized

- [ ] Confirm the exact MY-CoreXY revision represented by the downloaded CAD/STLs.
- [ ] Ask the designer which controller board is the intended one: MKS Monster8, Octopus, SKR Pro, or another.
- [ ] Confirm the exact Z motor count from the original assembly and wiring diagram.
- [ ] Confirm the heated-bed type and rated voltage from the actual bed label / official parts list.
- [ ] Confirm the hotend model, heater cartridge and thermistor part numbers.
- [ ] Confirm every fan's voltage, current, size and quantity.
- [ ] Confirm the host computer and firmware version.
- [ ] Have the power architecture and protection reviewed by a qualified electrician.
- [ ] Add supplier links, India pricing, shipping and taxes only after the above checks.

## Sources

- MY-CoreXY product overview and controller reference: https://my-machines.com/my-corexy-3d-printer
- MY-CoreXY electronics BOM: https://docs.my-machines.com/3d-printers/my-corexy/bom/electronics/
- Component mounting (Pi, power-supply and controller examples): https://docs.my-machines.com/3d-printers/my-corexy/wiring/01-component-mounting/
- Controller-board setup and TMC2209 example: https://docs.my-machines.com/3d-printers/my-corexy/wiring/02-controller-setup/
- Mains and PSU wiring chapter (reference only; not a DIY wiring instruction): https://docs.my-machines.com/3d-printers/my-corexy/wiring/03-mains-wiring/
- Low-voltage and signal wiring chapter: https://docs.my-machines.com/3d-printers/my-corexy/wiring/04-dc-wiring/
