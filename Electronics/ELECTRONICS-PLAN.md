# Electronics Plan — MY-CoreXY

> Status: preliminary planning only. This is not a verified wiring diagram or purchase-ready BOM. Confirm every item against the exact motor, hotend, fan, sensor and mechanical configuration before buying.

## 1. Proposed control architecture

The printer electronics will use a 24 V DC system, subject to confirmation against the selected components.

- **Main controller:** 32-bit 3D-printer control board with enough stepper-driver channels for the final axis and extruder arrangement.
- **Motion drivers:** compatible stepper drivers selected for the motors and controller-board voltage/current limits.
- **Motors:** X, Y, Z-axis motor arrangement and extruder motor to be confirmed from the final assembly/CAD and build guide.
- **Heater control:** controller-compatible hotend heater output and temperature sensor input; heated-bed output only if the final design includes a heated bed.
- **Endstops / homing:** compatible endstop or sensor inputs for the final motion design.
- **Cooling:** separately controlled hotend heatsink, part-cooling and electronics-enclosure fans as required.
- **Power:** certified, enclosed, appropriately rated DC power supply; fuse and protection requirements to be determined from the final load calculation.
- **Firmware:** choose Marlin or Klipper after selecting the controller board and host-computer arrangement.

## 2. Preliminary electronics checklist

| Item | Planning requirement | Status |
|---|---|---|
| Main controller board | 32-bit board; sufficient stepper, heater, fan and sensor connections | Not selected |
| Stepper drivers | Compatible with controller and selected motors | Not selected |
| X/Y/Z/extruder motors | Count, model and current rating to be verified from the build | Verify |
| Hotend heater | Match the chosen hotend and controller output rating | Not selected |
| Temperature sensors | Match hotend (and bed, if fitted) and firmware configuration | Not selected |
| Endstop / homing sensors | Match the final mechanical layout | Not selected |
| Fans | Correct voltage, size and current for each cooling position | Verify |
| DC power supply | Certified enclosed supply; voltage and wattage based on a documented load calculation | Not selected |
| Protection | Correctly rated fusing and suitable connectors/enclosure | To engineer |
| Wiring and connectors | Wire gauge, insulation and connector ratings matched to measured loads | Not selected |
| Host / display | Optional host for Klipper or compatible display for selected firmware | Not selected |
| Emergency stop / power isolation | Appropriate accessible isolation and protective design | To review |

## 3. Compatibility checks before ordering

1. Confirm the exact motor count, motor model, rated current and connector type.
2. Confirm whether the selected hotend and build configuration use 12 V or 24 V parts; do not mix voltages.
3. Check the controller board's input-voltage range, driver compatibility, per-channel current limits, heater MOSFET ratings, fan outputs and thermistor support.
4. Calculate the maximum DC load from the actual heater, motors, fans and controller specifications; select a certified supply with suitable headroom.
5. Confirm the firmware supports the selected board and the intended CoreXY / Z-motion arrangement.
6. Verify pin assignments and sensor types from the board manufacturer's documentation before any commissioning.

## 4. Electrical safety

- Use a certified, enclosed power supply and keep hazardous mains connections enclosed.
- Mains-side installation and inspection must be done by a qualified adult/electrician. Do not work on live circuits.
- Do not rely on firmware alone for thermal safety. Use appropriate hardware protection, correctly rated components, secure terminals and strain relief.
- Keep wiring away from moving parts and hot surfaces; protect cables against abrasion.
- Do not power heaters until the sensor type, firmware configuration, wiring and independent thermal protections have been checked.
- This document is a planning checklist, not a substitute for the controller, power-supply and component manufacturers' instructions.

## 5. Information still needed

The exact electronics BOM and wiring diagram cannot be finalized until the following are known:

- Final stepper motor count and model numbers
- Selected hotend and heater voltage / wattage
- Whether a heated bed is included
- Fan voltage, size and current
- Preferred controller board and firmware
- Country-specific supplier quotations, shipping and taxes

**Next revision:** replace every "Not selected / Verify" entry with a confirmed part number, quantity, datasheet link, supplier quote and compatibility note.
