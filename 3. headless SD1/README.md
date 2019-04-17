### SAMA5D27-SOM1 BASICS: How to compile a demo and boot from SD1

Buildroot Video Step by Step Guide for SAMA5D27-SOM1-EK1 available here:

#### Check previous guide to see 5W1H: 
- Software Pre Requirements
- Linux update and version check
- Find info. on the web
- Required packets
- Git repositories

#### Configure and compile from sources a demo image:
```
BR2_EXTERNAL=../buildroot-external-microchip/ make sama5d27_som1_ek_headless_defconfig
```

#### Change some basic system settings: 
```
make menuconfig

System configuration  --->
        ...
    [sama5d27-som1] System hostname
    [SAMA5D27 Microchip Embedded Demo] System Banner
    [toor] Root password
```

#### Change the bootstrap, u-boot and environment image configs files:

```
Bootloaders  --->
        ...
    [*] AT91 Bootstrap 3  --->
            ...
            [sama5d27-som1_eksd1_uboot] Defconfig name
        ...
    [*] U-Boot  --->
            ...
            [sama5d27-som1_ek_mmc1] Board defconfig
        ...
    [*] Environment image  --->			
            ...
            ($(BR2_EXTERNAL_MCHP_PATH)/board/microchip/sama5d27_som1_ek/uboot-sd1-env.txt) Source files for environment

save
exit

time make
```

#### Check previous guide to see 5W1H: 
- Find ready image
- Burn the image to SD card

Plug the ready SD card in J14 connector.

#### Play with image:
```
sudo minicom -b 115200 -D /dev/ttyS2
```
