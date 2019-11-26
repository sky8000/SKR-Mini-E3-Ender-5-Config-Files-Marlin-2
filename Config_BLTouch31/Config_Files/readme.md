# Configuration guide for SKR Mini E3 v1.0

This guide documents all settings changed in files **Configuration.h** and **Configuration_adv.h** from Marlin bugfix 2.0.x config examples for **Creality Ender-5**. These settings are also compatible with **Ender-3** and **Ender-3 Pro**, just be sure to use the correct config examples for your printer.

**Updated on 2019-10-26.**



## 1. File Configuration.h

This section details all configurations made to Marlin main configuration file (**Configuration.h**).



### 1.1. Configure motherboard

To configure the motherboard change `#define MOTHERBOARD BOARD_MELZI_CREALITY` to `#define MOTHERBOARD BOARD_BIGTREE_SKR_MINI_E3`.



### 1.2. Configure serial port

Follow the next steps to configure serial communication needed to print using USB:

1. Change `#define SERIAL_PORT 0`  to `#define SERIAL_PORT 2`. 
2. Uncomment `#define SERIAL_PORT_2 -1`.



### 1.3. Configure stepper drivers

Follow the next steps to configure stepper drivers:

1. Uncomment and change `#define X_DRIVER_TYPE  A4988`  to `#define X_DRIVER_TYPE TMC2209`.

2. Uncomment and change `#define Y_DRIVER_TYPE  A4988`  to `#define Y_DRIVER_TYPE TMC2209`.

3. Uncomment and change `#define Z_DRIVER_TYPE  A4988`  to `#define Z_DRIVER_TYPE TMC2209`.

4. Uncomment and change `#define E0_DRIVER_TYPE  A4988`  to `#define E0_DRIVER_TYPE TMC2209`.



### 1.4. Enable end stop interrupts

Enable end stop interrupts to reduce CPU load by uncommenting `#define ENDSTOP_INTERRUPTS_FEATURE`.



### 1.5. Enable and configure BLTouch

Follow the next steps to enable and configure BL Touch:

1. Uncomment `//#define BLTOUCH`.
2. Uncomment `//#define Z_MIN_PROBE_USES_Z_MIN_ENDSTOP_PIN`.
3. Change `#define XY_PROBE_SPEED 8000` to `#define XY_PROBE_SPEED 10000`.
4. Change `#define\ AUTO_BED_LEVELING_BILINEAR` to `#define AUTO_BED_LEVELING_BILINEAR`.
5. Uncomment `//#define Z_SAFE_HOMING`.

If you're using BL Touch mount from original Creality kit on Ender-5 change `#define NOZZLE_TO_PROBE_OFFSET { 10, 10, 0 }` to `#define NOZZLE_TO_PROBE_OFFSET { -43, -6, 0 }`.

Otherwise you'll have to measure the offsets and set the values accordingly. 



### 1.6. Disable speaker

Disable speaker by commenting `#define SPEAKER`. The firmware will freeze on SKR Mini E3 if this feature is enabled.



## 2. File Configuration_adv.h

This section details all changes made to Marlin advanced configuration file (**Configuration_adv.h**).



### 2.1. Configure TMC2209 serial communication

Follow next steps to configure communication with the stepper drivers (TMC2209):

1. Change `#define  Y_SLAVE_ADDRESS 0`  to `#define  Y_SLAVE_ADDRESS 2`.
2. Change `#define  Z_SLAVE_ADDRESS 0` to `#define  Z_SLAVE_ADDRESS 1`.
3. Change `#define E0_SLAVE_ADDRESS 0` to `#define E0_SLAVE_ADDRESS 3`.



### 2.2. Configure BL Touch v3.x

Follow the next steps to configure BL Touch for easier Z offset tuning:

1. Change `#define BABYSTEP_MULTIPLICATOR  1` to `#define BABYSTEP_MULTIPLICATOR  10`.
2. Uncomment `//#define BABYSTEP_ZPROBE_OFFSET` .

Users with **BL Touch v3.0** have to uncomment  `//#define BLTOUCH_FORCE_MODE_SET`  to force logic into 5v mode. **This applies to BL Touch v3.0 only, do not enable this option in BL Touch v3.1 as it will force the probe to save settings in the internal flash each time the printer boots reducing the probe's life span.**

