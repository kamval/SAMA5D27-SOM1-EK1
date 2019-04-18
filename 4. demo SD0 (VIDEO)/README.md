### SAMA5D27-SOM1 BASICS: How to compile a demo, add video support and boot from SD0

Buildroot Video Step by Step Guide for SAMA5D27-SOM1-EK1 available on [youtube](https://www.youtube.com/)

#### Check previous guide to see 5W1H:
- Software Pre Requirements
- Linux update and version check
- Find info. on the web
- Required packets
- Git repositories

#### Pre Requirements:

We will need a LCD panel in order to have a video output some of the compatible solutions are listed below:

- Use some of [capacitive multitouch solutions](http://www.pdaatl.com/products.htm) manufacture by [PDA inc](http://www.pdaatl.com/)
- Use custom LCD adapter board

For this guide we will use a custom developed board, enabling us to connect every LCD with 24-bit RGB parallel interface (check following folder in this repository: [LCD adapter board r1.0](https://github.com/kamval/SAMA5D27-SOM1-EK1/tree/master/4.%20demo%20SD0%20(VIDEO)/LCD%20adapter%20board%20r1.0)). 
The exact PN of the display used for the guide is [KWH043ST12](https://store.comet.bg/Catalogue/Product/45269/) manufactured by [FORMIKE](https://www.wandisplay.com/). 

#### Configure and compile from sources a demo image:
```
BR2_EXTERNAL=../buildroot-external-microchip/ make sama5d27_som1_ek_demo_defconfig
```

#### Change some basic system settings: 
```
make menuconfig

System configuration  --->
        ...
    [sama5d27-som1] System hostname
    [SAMA5D27 Microchip Embedded Demo] System Banner
    [toor] Root password

save
exit

time make
```

#### Check previous guide to see 5W1H:
- Find ready image
- Burn the image to SD card

Plug the ready SD card in J12 connector.

#### Manually select (or enforce) video at boot time:

The compiled demo supports the following display sizes:

- 4.3" TFT LCD, 480x272 - sama5d27_som1_ek_pda4.dtbo, tested with [KWH043ST12](https://store.comet.bg/Catalogue/Product/45269/) 
- 5.0" TFT LCD, 800x480 - sama5d27_som1_ek_pda5.dtbo, tested with [KWH050ST19](https://store.comet.bg/Catalogue/Product/45270/) 
- 7.0" TFT LCD, 800x600 - sama5d27_som1_ek_pda7.dtbo / sama5d27_som1_ek_pda7b.dtbo

By default the video output is not enabled. You need to enable the environment manualy. To do that press any key during U-Boot, the following text should appear:  

```
Hit any key to stop autoboot:  0

```

Enforce video by entering the following command in u-boot menu: 

```
setenv bootcmd 'fatload mmc 0:1 0x24000000 sama5d27_som1_ek.itb; bootm 0x24000000#kernel_dtb#pda4'
saveenv
```

Restart the board. Now the video output should be enabled. 

#### Play with image:
```
sudo minicom -b 115200 -D /dev/ttyS2
```
<p align="center">
  <img width="659" height="449" src="https://github.com/kamval/SAMA5D27-SOM1-EK1/blob/master/Documents/a5d27_som1_video_demo_bot.jpg">
</p>