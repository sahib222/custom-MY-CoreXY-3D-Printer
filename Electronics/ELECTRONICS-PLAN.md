# Electronics Plan — MY-CoreXY

> **Status: selected controller candidate; full system not yet verified or purchase-ready.** The project now uses the **BIGTREETECH SKR Mini E3 V3.0** as its planned controller. The original MY-CoreXY documentation refers to other controller boards and contains conflicting motor and power details. Do not buy or wire parts until the exact machine revision and motor arrangement are confirmed.

## 1. Selected controller

**Planned board:** BIGTREETECH SKR Mini E3 V3.0

- 32-bit STM32G0B1-based controller.
- Five onboard TMC2209 motor-driver interfaces: X, Y, Z-A, Z-B and E.
- 12 V / 24 V DC input.
- Klipper firmware support is documented by BIGTREETECH.
- No separate plug-in TMC2209 modules are included in this BOM because the drivers are onboard.

Official references:
- Board specifications: https://github.com/bigtreetech/docs/blob/master/docs/SKR%20MINI%20E3.md
- BIGTREETECH Klipper guide: https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/tree/master/firmware/V3.0/Klipper
- Klipper generic board configuration: https://github.com/Klipper3d/klipper/blob/master/config/generic-bigtreetech-skr-mini-e3-v3.0.cfg

## 2. Important compatibility check

The board provides five driver interfaces, but that does **not** prove it can drive every motor in the MY-CoreXY design as currently downloaded.

- The two CoreXY motors need two independently controlled driver channels.
- The board has two Z driver interfaces, Z-A and Z-B.
- The extruder needs a driver channel.
- The original MY-CoreXY wiring information appears to describe four Z-motor connections in one section, while other source material lists a different Z-motor count.
- If the actual printer needs four independently controlled Z motors in addition to the two CoreXY motors and extruder, five driver channels will not be enough.
- If the final design uses fewer independently controlled motors, the pin mapping and motor arrangement still need to be checked against the exact assembly revision.

**Decision:** Keep the SKR Mini E3 V3.0 as the selected budget candidate, but mark motor compatibility as **not yet verified**. Do not order until the designer's motor count and wiring arrangement are confirmed.

## 3. Other electronics

| Subsystem | Preliminary item | Status |
|---|---|---|
| Host | Raspberry Pi or another supported Klipper host | Exact model/storage not selected |
| 5 V supply | Separate regulated supply if required by final design | Verify load and mounting |
| 24 V supply | 24 V DC supply | Verify total DC load and rating |
| Hotend heater | 24 V, 40 W example | Verify against selected hotend |
| Hotend thermistor | 100 kΩ NTC example | Verify exact sensor curve/type |
| Fans | Two cooling fans in preliminary BOM | Verify voltage, current, size and quantity |
| Endstops | Three switches in preliminary BOM | Verify type and final homing arrangement |
| Heated bed / SSR | Source mentions an AC heated bed and SSR | Unresolved; qualified adult electrician must review the mains-side design |
| Wiring / connectors | To be specified from final component datasheets | Not finalised |
| Enclosure / lid / fan holders | Printed parts listed in source BOM | Check dimensions and fit |

## 4. Firmware planning

- Klipper is the planned firmware.
- BIGTREETECH publishes a Klipper guide and sample configuration for this board.
- The sample configuration is only a starting reference; it is not a ready-to-use MY-CoreXY configuration.
- The final configuration must be created for the actual CoreXY kinematics, motor directions, step distances, endstops, thermistor, heater, fans and motor arrangement.
- Do not copy printer dimensions or motion limits from the generic example.

## 5. Source-design conflicts still open

1. **Controller:** the original product page and wiring chapters refer to other controller examples. This project has selected SKR Mini E3 V3.0 as a replacement candidate; its pin mapping must be adapted and verified for this printer.
2. **Motor count:** source sections conflict about one versus four Z motors and five versus more driver channels. Confirm the exact CAD revision and wiring.
3. **Power:** the source mentions a 24 V system, a 240 V heated bed, a separate 5 V supply and different 24 V supply examples. Confirm the exact bed and complete load before choosing supplies.
4. **Toolhead and sensors:** verify the exact heater, thermistor, fans and endstop types against the selected hardware.

## 6. Safety boundary

This is a student project. Mains-powered equipment, AC heated beds, grounding, fusing, isolation and electrical installation must be specified, installed and inspected by a qualified adult electrician. Do not open power-supply cases or work on live equipment. Do not operate heaters until sensor compatibility, firmware limits and independent thermal protections have been professionally checked.

This document does **not** provide a mains wiring procedure or a ready-to-use wiring diagram.

## 7. Verification checklist

- [ ] Confirm the exact MY-CoreXY revision represented by the downloaded CAD/STLs.
- [ ] Confirm the number of independently controlled XY, Z and extruder motors.
- [ ] Confirm whether the two Z driver interfaces on this board suit the actual Z arrangement.
- [ ] Confirm the exact SKR Mini E3 V3.0 revision and obtain its official pinout.
- [ ] Map the final CoreXY motor, endstop, heater, thermistor and fan signals to the board.
- [ ] Confirm the Klipper host computer and storage.
- [ ] Confirm the heated-bed type and rated voltage.
- [ ] Have the power architecture and protection reviewed by a qualified electrician.
- [ ] Replace planning estimates with current supplier quotes before purchasing.

## Sources

- MY-CoreXY product overview: https://my-machines.com/my-corexy-3d-printer
- MY-CoreXY electronics BOM: https://docs.my-machines.com/3d-printers/my-corexy/bom/electronics/
- MY-CoreXY wiring chapters: https://docs.my-machines.com/3d-printers/my-corexy/wiring/
- BIGTREETECH SKR Mini E3 V3.0 specifications: https://github.com/bigtreetech/docs/blob/master/docs/SKR%20MINI%20E3.md
- BIGTREETECH SKR Mini E3 V3.0 Klipper guide: https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/tree/master/firmware/V3.0/Klipper
