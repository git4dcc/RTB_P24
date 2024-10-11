# RTB_E15
[![Real-time Bus (RTB)](https://img.shields.io/badge/RTB_Project-FF6699)](https://www.rtb4dcc.de)
[![Kicad_Libs](https://img.shields.io/badge/Kicad_Libs-29C7FF)](https://github.com/git4dcc/RTB_SamacSys)
[![Apache License 2.0](https://img.shields.io/badge/license-Apache%20License%202.0-lightgray)](https://www.apache.org/licenses/LICENSE-2.0)

This E15 module implements a 12 channel WS2811 emulator with compatible bus timing to drive multiplex (charlieplexing) LEDs. The E15 may be cascaded with regular WS28xx chips. The number of LEDs attached is automatically detected (0-12). The LED voltage is fixed to 5V.  The intended use is to drive Multiplex Signals on Model Railway layouts via the WS28xx bus.

_Note: The E15 is nearly identical to the [RTB_E13](https://github.com/git4dcc/RTB_E13), but only allows fixed LED voltage._

<details>
<summary>See also</summary>

- [RTB_E10](https://github.com/git4dcc/RTB_E10)
- [RTB_E13](https://github.com/git4dcc/RTB_E13)

</details>

<details>
<summary>User Guides</summary>

- [User Guide - DE](https://rtb4dcc.de/ws2811_guide_de/)
- User Guide - EN

</details>

<img src="https://rtb4dcc.de/wp-content/uploads/2024/04/E15_1.png">

The decoder has the following features,
- **Protocol**
  - WS2811 compatible timing
- **LED ports**
  - 0..12 LEDs (auto detecting)
  - Charlieplexing (Multiplexing) output
  - 256 step PWM (300Hz)
  - LED voltage fixed to 5V (see also [RTB_E13](https://github.com/git4dcc/RTB_E13))
  - gamma correction (optional)
- firmware update via V24 debug interface

# Hardware
My current PCB layout uses SMD footprints with 0.5mm pitch and 0603 parts. Reflow soldering is my recommendation, but with some experience handsoldering is also possible.

<img src=https://rtb4dcc.de/wp-content/uploads/2024/07/un_E15_5.png>

## PCB
- 2-layer PCB, FR4, 1.6mm
- CPU: AVR64DA32
- BUS: WS28xx
- LED: Charlieplexing

## Kicad
[Schematic](doc/E15_schematic.pdf) | [Layout](doc/E15_layout.pdf) | [Gerber](gerber)

<details>
<summary>Dependency</summary>
<br>

:yellow_circle: Requires my Kicad project library [RTB_SamacSys](https://github.com/git4dcc/RTB_SamacSys) in the same directory tree.

</details>

## Firmware
Filename structure: { **pcb** }{ **code** }{ **version** }.hex

Example: **E15F0001**.hex

|   | Description |
| --- | --- |
| **pcb** | Name of matching hardware (**E15**) |
| **code** | Type of code contained (**R**=rom, **B**=bootloader, **F**=flash, **U**=bld update, **P**=UPDI factory code) |
| **version** | Release version (**####**) |

## UPDI
The fuse settings as well as the P-code (E15Pxxxx.hex) has to be installed by using UPDI.<br>

<details>
<summary>Details</summary>

<img src=https://rtb4dcc.de/wp-content/uploads/2024/07/un_E13_4.jpg>

| Fuse Setting | P-code Install |
| --- | --- |
|<img src="https://rtb4dcc.de/wp-content/uploads/2024/07/un_E15_Fuses.png" width=500>|<img src="https://rtb4dcc.de/wp-content/uploads/2024/07/un_E15_Mem.png" width=500>|

</details>

## Debug Interface
Subsequent code updates can be done via the built-in serial debug interface.<br>

<details>
<summary>Details</summary>

- connect the serial cable **(1Mb, 8N1, RTS/CTS)**
- press 'break' within the VT100 terminal to bump the module to console prompt
- upload the firmware file (E15Fxxxx.hex)
- for more details, refer to the 'User Guide'

  <img src="https://rtb4dcc.de/wp-content/uploads/2024/07/un_E15_Rom.png">

</details>

# Software
The LED intensity values for the individual LEDs need to be transmitted over the bus, with N being the number of configured LEDs.

```
Byte order:     {led_0} ... {led_N}
```

# Images
<img src=https://rtb4dcc.de/wp-content/uploads/2024/02/E13_3.jpg width=260> <img src=https://rtb4dcc.de/wp-content/uploads/2024/01/un_E13_example1.png width=260>

This project is intended for hobby use only and is distributed in accordance with the Apache License 2.0 agreement.
