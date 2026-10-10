# 🔋 TP4056 Li-Ion Battery Charging Module — PCB Design

## 📌 Project Overview

A compact **TP4056-based single-cell lithium-ion battery charging module** designed using EasyEDA. The module is intended for charging rechargeable 3.7 V nominal lithium-ion or lithium-polymer batteries from a suitable 5 V DC input.

The PCB integrates the charging circuit and its supporting components into a compact layout suitable for embedded electronics, robotics, IoT devices, portable projects, and battery-powered prototypes.

The design focuses on reliable electrical connections, practical component placement, clear silkscreen labeling, and convenient PCB integration.

## ⚙️ Key Features

- 🔋 **Single-Cell Li-Ion Charging** — Designed for one rechargeable lithium-ion or lithium-polymer cell.
- 🧠 **TP4056 Charging IC** — Constant-current/constant-voltage (CC/CV) charging controller.
- 🔌 **5 V DC Input** — Input interface for a compatible USB supply or regulated 5 V source.
- ⚡ **Programmable Charging Current** — Charging current set by the PROG resistor, subject to IC and PCB thermal limits.
- 💡 **Charging Status Indication** — Supports charge-status LEDs when connected according to the circuit design.
- 📐 **Compact PCB Layout** — Components arranged for practical assembly and integration.
- 🛠️ **EasyEDA Design** — Schematic and PCB layout created in EasyEDA.
- 🔧 **Embedded Project Compatibility** — Suitable for prototyping battery-powered electronics, including robotics and IoT systems.

> ⚠️ **Protection note:** A TP4056 charging IC alone does not provide complete battery protection against over-discharge, overcurrent, or short circuits. Do not describe the module as protection-equipped unless a protection circuit, such as a suitable DW01A and dual MOSFET arrangement, is actually included and verified.

## 🔌 How It Works

The TP4056 uses a constant-current/constant-voltage charging method to charge a single-cell lithium-ion battery.

1. 🔌 **Power Input:** A suitable regulated 5 V supply is connected to the input terminals.
2. ⚡ **Constant-Current Phase:** The IC charges the battery at a current determined primarily by the PROG resistor.
3. 🔋 **Constant-Voltage Phase:** As the battery voltage approaches the regulation voltage, the charging current gradually decreases.
4. ✅ **Charge Completion:** The IC terminates charging when the current falls below its termination threshold, under the specified operating conditions.
5. 💡 **Status Indication:** The status outputs can drive charging and completion indicators, depending on the implemented circuit.

## 🧩 Main Components

| Component | Function |
|---|---|
| TP4056 | Single-cell lithium-ion battery charging controller. |
| PROG resistor | Sets the programmed charging current. |
| Input capacitor | Helps stabilize the input supply. |
| BAT capacitor | Provides local filtering on the battery connection, if included. |
| Status LEDs | Indicate charging state or charge completion, if implemented. |
| LED resistors | Limit current through the status indicators. |
| Input connector | Connects the 5 V supply. |
| Battery connector | Connects the rechargeable battery. |
| Supporting components | Implement filtering, control, and other functions shown in the schematic. |

*The actual component list depends on the schematic and BOM of your EasyEDA design.*

## 📊 Electrical Specifications

| Parameter | Description |
|---|---|
| Charging IC | TP4056 |
| Battery chemistry | Compatible single-cell lithium-ion / lithium-polymer |
| Nominal battery voltage | 3.7 V |
| Typical full-charge voltage | 4.2 V, subject to the exact IC variant and battery specification |
| Input supply | Regulated 5 V DC, within the IC's specified limits |
| Charging method | Constant current / constant voltage (CC/CV) |
| Charging current | Determined by the PROG resistor and thermal conditions |
| PCB design software | EasyEDA |
| Battery configuration | 1S (one cell) |

**Note:** Actual charging current, thermal performance, and supported input range must be confirmed against the selected IC datasheet and your schematic. The TP4056 is a linear charger, so its power dissipation can become significant at high charging currents.

## 📐 PCB Design Highlights

### 🧱 Component Placement
- Arrange the TP4056 and its supporting components to keep important connections short.
- Place input and battery connectors where they are easy to access.
- Keep status LEDs visible after the PCB is installed in its enclosure.
- Position decoupling capacitors close to the corresponding IC pins.

### ⚡ Power Routing
- Use suitable trace widths for input and charging-current paths.
- Minimize unnecessary resistance in the battery and power connections.
- Maintain proper clearances between copper features and exposed pads.
- Verify connector polarity and silkscreen labels before fabrication.

### 🌡️ Thermal Management
- Account for the TP4056's power dissipation during charging.
- Use copper area and thermal vias where appropriate for the package and PCB stack-up.
- Check the IC's junction-temperature limits under realistic operating conditions.
- Reduce the programmed charging current if the thermal design cannot safely dissipate the heat.

### 🏷️ Silkscreen & Usability
- Clearly identify the input terminals, such as `IN+` and `IN−`.
- Clearly identify the battery terminals, such as `B+` and `B−`.
- Mark LED functions and other important connection points.
- Include polarity markings that remain visible after assembly.

## 📂 Project Files

The repository may contain the following files, depending on your exported deliverables:

| File | Description |
|---|---|
| `README.md` | Project overview and technical documentation. |
| `TP4056_Module.json` | EasyEDA design data, if exported in JSON format. |
| `TP4056_Module.pdf` | Schematic and/or PCB documentation. |
| `TP4056_Module_Gerber.zip` | Gerber and drill files for PCB fabrication. |
| `TP4056_Module_BOM.csv` | Bill of materials, if exported. |
| `images/schematic.png` | Schematic preview. |
| `images/top.png` | PCB top-layer preview. |
| `images/bottom.png` | PCB bottom-layer preview. |
| `images/3d.png` | 3D PCB model preview. |

*Only include files that actually exist in your repository, and update the filenames to match your exports.*

## 🖼️ Design Preview

Add your exported EasyEDA screenshots to the `images/` directory.

| 🔌 Schematic | 🔝 Top Layer |
|---|---|
| ![Schematic](images/schematic.png) | ![Top Layer](images/top.png) |

| 🔽 Bottom Layer | 🧊 3D PCB View |
|---|---|
| ![Bottom Layer](images/bottom.png) | ![3D PCB View](images/3d.png) |

## 🛠️ Design Workflow

1. 📋 Define the battery, input-supply, and charging-current requirements.
2. 🔍 Select the TP4056 IC and supporting components.
3. 🔌 Create and verify the schematic in EasyEDA.
4. 📐 Assign the correct footprints and arrange the components.
5. 🛤️ Route the PCB and verify power paths and thermal considerations.
6. ✅ Run the Electrical Rule Check (ERC) and Design Rule Check (DRC), as applicable.
7. 📦 Export the required design documentation and manufacturing files.
8. 🔬 Inspect the fabricated PCB and test it with a suitable current-limited power supply and compatible battery.

## ✅ Verification Checklist

- [ ] Confirm the exact TP4056 IC variant and package footprint.
- [ ] Verify all IC pin assignments against the datasheet.
- [ ] Check the PROG resistor value and expected charging current.
- [ ] Verify input and battery connector polarity.
- [ ] Confirm capacitor values, voltage ratings, and placement.
- [ ] Verify LED polarity and current-limiting resistors.
- [ ] Check whether battery over-discharge and overcurrent protection are included.
- [ ] Review charging-current traces and thermal dissipation.
- [ ] Run ERC and DRC and resolve relevant errors.
- [ ] Inspect Gerber and drill outputs before manufacturing.
- [ ] Test the assembled board for correct charging behavior and safe temperature.

## ⚠️ Safety Considerations

- Use only a compatible single-cell rechargeable lithium-ion or lithium-polymer battery.
- Never connect a battery with reversed polarity.
- Do not exceed the battery manufacturer's recommended charging current or voltage.
- Use a suitable, regulated input supply.
- Monitor temperature during initial testing.
- Do not leave an unverified prototype charging unattended.
- If the project requires over-discharge, overcurrent, or short-circuit protection, implement and verify a suitable protection circuit separately.

## 🚀 Applications

- 🤖 Robotics and small embedded systems.
- 📡 ESP32 and ESP8266 battery-powered projects.
- 🌐 IoT sensor nodes.
- 🔦 Portable electronics and DIY devices.
- 🔋 Rechargeable battery-powered prototypes.
- 🧪 Electronics learning and PCB design practice.

## 👨‍💻 Author

**M. Shoyab Sadik**  
B.Sc. in Electrical and Electronic Engineering (EEE), IUBAT

- 🌐 Website: [shoyabsadik.github.io](https://shoyabsadik.github.io/)
- 💼 LinkedIn: [shoyabsadik](https://www.linkedin.com/in/shoyabsadik/)

**🚀 From Code to Creation — Learn • Build • Innovate.**
