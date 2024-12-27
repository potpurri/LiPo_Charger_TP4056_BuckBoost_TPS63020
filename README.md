# Lithium Battery Charger and Boost Converter PCB

This PCB is designed to safely charge a lithium-ion cell and provide a selectable 3.3V or 5V output. It's equipped with components that ensure safe charging and protection for the battery and supports flexible output and charging options. 

## Features

- **Charging IC**: TP4056 with adjustable charge currents.
- **Protection Circuitry**: DW01A and F8205A provide overcharge, over-discharge, and overcurrent protection.
- **Buck-Boost Converter**: TPS63020 for stable 3.3V or 5V output, selectable via solder jumper.
- **Compact Design**: Ideal for portable applications, with both top and bottom images of the board for easy identification.
- **Fuse Protection**: Added fuse for enhanced safety of the battery connection.
- **Battery disconnection during charging**: When the USB-C port is connected for charging, the battery is disconnected from the Buck-Boost converter via two p-channel MOSFETs in series, with the gates tied to VBUS of the USB-C input. Power is instead provided to the Buck-Boost converter using a Schottky diode during charging. This circuit can be bypassed using the solder jumper on the bottom side of the PCB.

## Charging Current Settings

The charging current of the TP4056 can be adjusted using solder jumpers on the PCB to meet various requirements. Refer to the table below:

| Solder Jumper Setting | Charging Current |
|-----------------------|------------------|
| J1                    | 130 mA           |
| J2                    | 280 mA           |
| J3                    | 400 mA           |
| J4                    | 580 mA           |
| J5                    | 780 mA           |
| J6                    | 1000 mA          |

## Images

### Schematic
![Schematic](imgs/schematic-v1.3.pdf)

### 3D Renderings
- Front View: ![3D Front](imgs/3d-front.png)
- Front View Without Components: ![3D Front](imgs/3d-front-no-components.png)
- Back View: ![3D Back](imgs/3d-back.png)

### PCB
**4-Layer Stackup**: Signal Layer, GND Layer, Power Layer, Signal Layer
- All layers: ![PCB - All Layers](imgs/pcb.png)
- Front traces: ![PCB - Front](imgs/pcb-front.png)
- GND plane: ![PCB - GND](imgs/pcb-gnd.png)
- PWR plane: ![PCB - PWR](imgs/pcb-pwr.png)
- Back traces: ![PCB - Back](imgs/pcb-back.png)

## Usage

1. **Output Voltage Selection**: Set the desired output voltage (3.3V or 5V) by configuring the solder jumper on the PCB.
2. **Charging Current Selection**: Set the charging current by adjusting the appropriate solder jumper(s) according to the table above.
3. **Connect Battery**: Connect the lithium-ion cell to the battery terminals.
4. **Power Input**: Provide power via the charging input, and the circuit will manage safe charging for the battery and maintain output stability.
5. **Fuse Protection**: Ensure the fuse is correctly in place for additional battery safety.
6. **Battery disconnection during charging**: When the USB-C port is connected, the battery is safely disconnected from the Buck-Boost converter, and power is instead supplied to it from VBUS through a Schottky diode.

---

This board is ideal for applications needing a stable 3.3V or 5V from a lithium-ion cell with enhanced safety and flexibility. With the added features, it provides even more robust protection and usability for various portable electronic projects.
