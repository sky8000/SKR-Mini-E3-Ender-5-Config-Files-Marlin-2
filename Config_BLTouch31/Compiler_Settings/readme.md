# Configuration guide for SKR Mini E3 v1.0

This guide documents all settings changed in file **plaformio.ini** from Marlin bugfix 2.0.x.  These settings are compatible with **Creality Ender-5**, **Ender-3** and **Ender-3 Pro** printers.

**Updated on 2019-10-11.**



## 1. File platformio.ini

This section shows all changes made to configuration in **Project Configuration File** (**platformio.ini**).

### 1.1. Configure environment

To configure the development environment change `default_envs = megaatmega2560` to `default_envs = STM32F103RC_bigtree`.


