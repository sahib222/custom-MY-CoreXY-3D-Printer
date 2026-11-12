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

The official assembly guide confirms **four Z-drive assemblies, each housing a motor**. The source electronics BOM lists five stepper drivers. The SKR Mini E3 V3.0 has five driver interfaces: X, Y, Z-A, Z-B and E. This gives two Z driver channels, not four independently controlled Z channels. The exact original motor grouping and current requirements still need verification. The board therefore cannot yet be declared compatible.

- The two CoreXY motors need two independently controlled driver channels.
- The board has two Z driver interfaces, Z-A and Z-B.
- The extruder needs a driver channel.
- The official assembly guide shows four physical Z-drive motors.
- Four Z motors plus two CoreXY motors and one extruder represent seven physical motors.
- The selected board exposes only two Z driver channels, so four independently controlled Z motors cannot each have their own driver channel on this board.
- The original BOM lists five drivers, suggesting the source design may group motors onto fewer driver channels, but the exact grouping and electrical suitability are not confirmed by the sources checked so far. Do not assume paired motors are safe or compatible.

**Decision:** Keep the SKR Mini E3 V3.0 as a candidate only. Four Z-drive motors are confirmed, but the required driver grouping is not. Do not order until the designer's intended motor grouping, driver current requirements and firmware configuration are confirmed.

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

## 4. Planned smart features

| Feature | Planned implementation | Status / caveat |
|---|---|---|
| Camera monitoring | Compatible USB camera connected to the Klipper host for remote viewing | Not selected or tested; verify host support and mounting |
| Touchscreen | Compatible display for local printer status and controls | Not selected or tested; verify interface and software support |
| AI print monitoring | Optional software analysis of camera images to flag possible print failures | Experimental; advisory only, not a safety system and not a substitute for supervision or hardware protections |

## 5. Firmware planning

- Klipper is the planned firmware.
- BIGTREETECH publishes a Klipper guide and sample configuration for this board.
- The sample configuration is only a starting reference; it is not a ready-to-use MY-CoreXY configuration.
- The final configuration must be created for the actual CoreXY kinematics, motor directions, step distances, endstops, thermistor, heater, fans and motor arrangement.
- Do not copy printer dimensions or motion limits from the generic example.

## 6. Source-design conflicts still open

1. **Controller:** the original product page and wiring chapters refer to other controller examples. This project has selected SKR Mini E3 V3.0 as a replacement candidate; its pin mapping must be adapted and verified for this printer.
2. **Motor / driver count:** the official assembly guide confirms four Z-drive motors, while the electronics BOM lists five drivers. Confirm how the four Z motors are assigned to the two Z driver channels before selecting the controller.
3. **Power:** the source mentions a 24 V system, a 240 V heated bed, a separate 5 V supply and different 24 V supply examples. Confirm the exact bed and complete load before choosing supplies.
4. **Toolhead and sensors:** verify the exact heater, thermistor, fans and endstop types against the selected hardware.

## 7. Safety boundary

This is a student project. Mains-powered equipment, AC heated beds, grounding, fusing, isolation and electrical installation must be specified, installed and inspected by a qualified adult electrician. Do not open power-supply cases or work on live equipment. Do not operate heaters until sensor compatibility, firmware limits and independent thermal protections have been professionally checked.

This document does **not** provide a mains wiring procedure or a ready-to-use wiring diagram.

## 8. Verification checklist

- [ ] Confirm the exact MY-CoreXY revision represented by the downloaded CAD/STLs.
- [x] Confirm four physical Z-drive motor assemblies in the official assembly guide.
- [ ] Confirm the original designer's intended grouping of four Z motors across the available driver channels.
- [ ] Confirm whether the two Z driver interfaces on this board can safely support the intended motor grouping and current requirements.
- [ ] Confirm the exact SKR Mini E3 V3.0 revision and obtain its official pinout.
- [ ] Map the final CoreXY motor, endstop, heater, thermistor and fan signals to the board.
- [ ] Confirm the Klipper host computer and storage.
- [ ] Confirm the heated-bed type and rated voltage.
- [ ] Have the power architecture and protection reviewed by a qualified electrician.
- [ ] Replace planning estimates with current supplier quotes before purchasing.

## Sources

- MY-CoreXY product overview: https://my-machines.com/my-corexy-3d-printer
- MY-CoreXY Z-drive assembly guide (confirms four motorised Z-drive assemblies): https://docs.my-machines.com/3d-printers/my-corexy/assembly/02-z-drives-and-idlers/
- MY-CoreXY electronics BOM: https://docs.my-machines.com/3d-printers/my-corexy/bom/electronics/
- MY-CoreXY wiring chapters: https://docs.my-machines.com/3d-printers/my-corexy/wiring/
- BIGTREETECH SKR Mini E3 V3.0 specifications: https://github.com/bigtreetech/docs/blob/master/docs/SKR%20MINI%20E3.md
- BIGTREETECH SKR Mini E3 V3.0 Klipper guide: https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/tree/master/firmware/V3.0/Klipper
