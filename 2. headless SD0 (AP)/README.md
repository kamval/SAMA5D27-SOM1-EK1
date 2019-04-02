### SAMA5D27-SOM1 BASICS: How to add new packages and boot from SD0

Buildroot Video Step by Step Guide for SAMA5D27-SOM1-EK1 available here:

#### Check previous guide to see how and where:
- Pre Requirements
- Linux version
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
    [*] System hostname
	[*] System Banner
	[*] Root password
```
#### Add lighttpd support: 
```
Target packages  --->
        ...
    [*] Networking applications  --->
            ...
            [*] lighttpd
            [ ]   openssl support
            [ ]   zlib support
            [ ]   bzip2 support
            [ ]   pcre support
            [ ]   webdav support
			
time make
```
Check previous guide to see how and where:
- Find ready image
- Burn the image to SD card

Plug the ready SD card in J12 connector.

Play with image:
```
sudo minicom -b 115200 -D /dev/ttyS2
```
