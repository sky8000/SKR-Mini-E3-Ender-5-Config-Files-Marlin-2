# Ender-5/SKR Mini E3 v1.0 Config Files

This repository contains Marlin custom config files for **Creality Ender-5** printers with a BIGTREETECH SKR Mini E3 v1.0 motherboard.  Settings used are also compatible with **Ender-3** and **Ender-3 Pro**, just be sure to use the correct config examples for your printer. For more information about which settings to change please browse to the config folder in this repository and read the readme.md files.

Please note that this configuration is **not compatible with SKR Mini E3 v1.2**.

**Updated on 2019-11-06.**



## Installation guide for Printers with BL Touch 3.1

1. Get the latest Marlin bugfix-2.0.x from the official site here: http://marlinfw.org/meta/download/.
2. Copy files from folder **\Config_BLTouch31\Config_Files** in this repository to the folder **\Marlin** in your firmware root folder.
3. **Optional:** Copy files from folder **\Config_BLTouch31\Board_Pins** in this repository to the folder **\Marlin\src\pins\stm32** in your firmware root folder if you want to use BL Touch dedicated port (PC14) instead of the default Z end stop pin (PC2).
4. Copy files from folder **\Config_BLTouch31\Compiler_Settings** in this repository to the your firmware root folder.
6. Compile the software and flash the board.
6. **Optional:** Do a "Restore failsafe" from the printer's menu or delete file EEPROM.DAT from the SD Card before powering on to make sure that the printer is running with the default values and avoid malfunction.

   

## Installation guide for Printers without BL Touch

1. Get the latest Marlin bugfix-2.0.x from the official site here: http://marlinfw.org/meta/download/.
2. Copy files from folder **\Config_BLTouch31\Config_Files** in this repository to the folder **\Marlin** in your firmware root folder.
3. Copy files from folder **\Config_BLTouch31\Compiler_Settings** in this repository to the your firmware root folder.
5. Compile the software and flash the board.
6. **Optional:** Do a "Restore failsafe" from the printer's menu or delete file EEPROM.DAT from the SD Card before powering on to make sure that the printer is running with the default values and avoid malfunction.

## Connecting BL Touch to dedicated on-board port (PC14)

Below is a picture showing where to connect your BL Touch if you wish to use the dedicated on-board port. This not required but it leaves Z end stop port available if you want to repurpose it. In this case you need to **follow** **step 3** from the **Installation guide for Printers with BL Touch 3.1**.



![](https://i.imgur.com/AO4crIO.jpg)



## Connecting BL Touch to Z end stop (PC2)

Below is a picture showing where to connect your BL Touch if you wish to use the Z end stop pin.  In this case you have to **skip** **step 3** from the **Installation guide for Printers with BL Touch 3.1**.



![](https://i.imgur.com/3TEBdS4.jpg)



## Using a buck converter to power BL Touch

Below are two pictures that show how to connect BL Touch to a stable, low noise power source in order to fix the probing issues caused by SKR Mini E3 5v rail problem. 

![](https://i.imgur.com/8eEEUF9.jpg)



![](https://i.imgur.com/lZjAzvL.jpg)



**To do:**

* Create and test a common ground between buck converter and SKR Mini E3 board.

  

**Buck converter specs:**

- Type/name: LM2596HVS DC-DC step-down module
- Input Voltage: 4.5V ~ 53V
- Output Voltage: 3V ~ 40V
- Output Current: 3A (max)
- Conversion efficiency: 92%(the highest)
- Output Ripple: <30mV
- Switching frequency: 150KHz
- Operating Temperature: -45 ° ~ +85 °
- Size: 43mm * 21mm * 14mm (L * W* H)



## Links

SKR Mini E3 Github page: https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3-

Marlin bugfix-2.0.x: http://marlinfw.org/meta/download/

Marlin Github repository: https://github.com/MarlinFirmware/Marlin

BIGTREETECH SKR MINI E3&E3 DIP User Group on FB: https://www.facebook.com/groups/322956191976815/



## Technical information

| Item                 | Detail/description                                           |
| -------------------- | ------------------------------------------------------------ |
| Printer              | Creality Ender-5 (settings also compatible with Ender-3 and Ender-3 Pro using the correct config file examples from Marlin 2.0.x) |
| Board                | BIGTREETECH SKR Mini E3 v1.0                                 |
| Display              | Stock Ender-5 display (LCD 12864)                            |
| ABL                  | BL Touch 3.1, tested with Z end stop port (PC2) and powered by a low noise buck converter |
| Original file source | Ender-5 example config files bundled with Marlin bugfix-2.0.x tree, commit 882609c5bd, 2019-11-06 |

