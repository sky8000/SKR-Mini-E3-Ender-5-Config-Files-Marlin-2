# Ender-5/SKR Mini E3 Config Files

This repository contains Marlin custom config files for Creality Ender-5 printers with a BIGTREETECH SKR Mini E3 motherboard. 

## Installation guide for Printers with BL Touch 3.1

1. Get the latest Marlin bugfix-2.0.x from the official site here: http://marlinfw.org/meta/download/.
2. Copy files from folder **\Config_BLTouch31\Config_Files** in this repository to the folder **\Marlin** in your firmware root folder.
3. **Optional:** Copy files from folder **\Config_BLTouch31\Board_Pins** in this repository to the folder **\Marlin\src\pins\stm32** in your firmware root folder if you want to use BL Touch dedicated port (PC14) instead of the default Z end stop pin (PC2).
4. Copy files from folder **\Config_BLTouch31\Compiler_Settings** in this repository to the your firmware root folder.
5. Copy files from folder **\CR10_Display_Fix** in this repository to the folder **\Marlin\src\lcd\dogm** in your firmware root folder (fixes [BUG] #15113 on latest Marlin bugfix-2.0.x, please view links section for more details).
6. Compile the software and flash the board.
7. **Optional:** Do a "Restore failsafe" from the printer's menu or delete file EEPROM.DAT from the SD Card before powering on to make sure that the printer is running with the default values and avoid malfunction.

Please note that there are still some compatibility issues with BL Touch v3.x that randomly causes homing or bed leveling to fail, for more details please check the following links: https://www.reddit.com/r/ender5/comments/cvrokv/bigtreetech_skr_mini_e3_on_ender_5/.



## Installation guide for Printers without BL Touch

1. Get the latest Marlin bugfix-2.0.x from the official site here: http://marlinfw.org/meta/download/.
2. Copy files from folder **\Config_BLTouch31\Config_Files** in this repository to the folder **\Marlin** in your firmware root folder.
3. Copy files from folder **\Config_BLTouch31\Compiler_Settings** in this repository to the your firmware root folder.
4. Copy files from folder **\CR10_Display_Fix** in this repository to the folder **\Marlin\src\lcd\dogm** in your firmware root folder (fixes [BUG] #15113 on latest Marlin bugfix-2.0.x, please view links section for more details).
5. Compile the software and flash the board.
6. **Optional:** Do a "Restore failsafe" from the printer's menu or delete file EEPROM.DAT from the SD Card before powering on to make sure that the printer is running with the default values and avoid malfunction.

## Connecting BL Touch to dedicated on-board port (PC14)

Below is a picture showing where to connect you BL Touch if you wish to use the dedicated on-board port. This not required but it leaves Z end stop port available if you want to repurpose it.



![](https://i.imgur.com/AO4crIO.jpg)



## Links

SKR Mini E3 Github page: https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3-

Marlin bugfix-2.0.x: http://marlinfw.org/meta/download/

[BUG] #15113 breaks CR10_STOCKDISPLAY support on SKR Mini E3: https://github.com/MarlinFirmware/Marlin/issues/15141

BIGTREETECH SKR MINI E3&E3 DIP User Group on FB: https://www.facebook.com/groups/322956191976815/

Bigtreetech after-sales support e-mail:  [support@bigtree-tech.com](mailto:support@bigtree-tech.com)



## Technical information

| Item                 | Detail/description                                           |
| -------------------- | ------------------------------------------------------------ |
| Printer              | Creality Ender-5                                             |
| Board                | BIGTREETECH SKR Mini E3                                      |
| Display              | Stock Ender-5 display (LCD 12864)                            |
| ABL                  | BL Touch 3.1, tested with dedicated BL Touch port (PC14) and Z end stop port (PC2) |
| Original file source | Ender-5 example config files bundled with Marlin bugfix-2.0.x tree, commit c5c63b147c, 2019-09-05 |
