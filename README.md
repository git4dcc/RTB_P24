# RTB_P24
[![Real-time Bus (RTB)](https://img.shields.io/badge/RTB_Project-FF6699)](https://www.rtb4dcc.de)
[![Kicad_Libs](https://img.shields.io/badge/Kicad_Libs-29C7FF)](https://github.com/git4dcc/RTB_SamacSys)
[![Apache License 2.0](https://img.shields.io/badge/license-Apache%20License%202.0-lightgray)](https://www.apache.org/licenses/LICENSE-2.0)

This simple module is a decoder test board with two [Next18](https://normen.railcommunity.de/RCN-118.pdf) sockets and is part of my growing collection of tools for my DCC based digital model trains. It has two independent Next18 sockets and the DCC signal is fed in and out at both ends to enable easy daisy chaining of multiple PCBs. For each, a motor or resistor can be connected externally to enable service mode programming with DCC.

<details>
<summary>See also</summary>

- [RTB_D21](https://github.com/git4dcc/RTB_D21) (DCC Decoder)
- [RTB_P21](https://github.com/git4dcc/RTB_P21)
- [RTB_P27](https://github.com/git4dcc/RTB_P27)

</details>

<details>
<summary>User Guides</summary>

- User Guide - DE (to be done)
- User Guide - EN (to be done)

</details>

<img src=supplemental/images/P24_main.jpg>

# Hardware
My PCB layout uses SMD footprints with mainly 0603 parts. Reflow soldering is my recommendation, but with some experience handsoldering is also possible.

<img src=supplemental/images/P24_top_connect.jpg>

## PCB
- 2-layer PCB, FR4, 1.6mm
- Dimensions: 80mm x 22mm
- Socket: 2x [Next18](https://normen.railcommunity.de/RCN-118.pdf)

## Kicad
[Schematic](doc/P24_schematic.pdf) | [Layout](doc/P24_layout.pdf) | [Gerber](gerber)

<details>
<summary>Dependency</summary>
<br>

:yellow_circle: Requires my Kicad project library [RTB_SamacSys](https://github.com/git4dcc/RTB_SamacSys) in the same directory tree.

</details>

# Images
<img src=supplemental/images/P24_usecase.jpg width=260>

This project is intended for hobby use only and is distributed in accordance with the Apache License 2.0 agreement.
