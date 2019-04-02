### SAMA5D27-SOM1-EK1

A step by step guide to build from source Bulidroot for SAMA5D27-SOM1-EK1. 

This entry level guide would be usefull for everyboady who are starting their first steps with Embedded Linux, [Buildroot](https://buildroot.org/) and [Microchip MPUs](https://www.microchip.com/design-centers/32-bit-mpus ).

#### About Buildroot:

[Buildroot](https://buildroot.org/downloads/manual/manual.html) is a tool that simplifies and automates the process of building a complete Linux system for an embedded system, using cross-compilation.
In order to achieve this, Buildroot is able to generate a cross-compilation toolchain, a root filesystem, a Linux kernel image and a bootloader for your target. Buildroot can be used for any combination of these options, independently (you can for example use an existing cross-compilation toolchain, and build only your root filesystem with Buildroot).
Buildroot is useful mainly for people working with embedded systems. Embedded systems often use processors that are not the regular x86 processors everyone is used to having in his PC. They can be PowerPC processors, MIPS processors, ARM processors, etc.
Buildroot supports numerous processors and their variants; it also comes with default configurations for several boards available off-the-shelf. Besides this, a number of third-party projects are based on, or develop their BSP or SDK on top of Buildroot.

#### About SAMA5D27-SOM1-EK1:

[ATSAMA5D27-SOM1-EK1](https://www.microchip.com/developmenttools/ProductDetails/atsama5d27-som1-ek1) is a fast prototyping and evaluation platform for the SAMA5D2 based System in Packages (SiPs) and the SAMA5D27-SOM1 (SAMA5D27 System On Module). The kit comprises a baseboard with a soldered ATSAMA5D27-SOM1 module. The module features an ATSAMA5D27C-D1G-CU SIP embedding a 1-Gbit (128 MB) DDR2 DRAM. The SOM integrates a Power Management IC (PMIC), a QSPI memory, a 10/100 Mbps Ethernet PHY and a serial EEPROM with a MAC address. 128 GPIO pins are provided by the SOM for general use in the system. The board features a wide range of peripherals, as well as a user interface and expansion options, including two mikroBUS™ click interface headers to support MikroElektronika click boards™ and one PMOD™ interface. Linux distribution and software package allows you to easily get started with your development.

<img src="https://github.com/kamval/SAMA5D27-SOM1-EK1/blob/master/Documents/a5d27_som1_ek_board_presentation.png">