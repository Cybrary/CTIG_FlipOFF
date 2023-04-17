There isn't alot of data on how to use the BLE function of the FLipper Zero. The Flipper Zero runs on a ARM Coretex 4 processor
with a Cortex 0+ wireless coprocessor. To understand more about the Flipper Zero we took the patch of emore deeply exaiming the 
STM32wb board. STM32 code is even presnet in the FLipper Zero source tree.

The Coretx 0+ wireless processor can run Bluetooth LE, Zigbee, and other such protocols. Loading a encrypted and signed blob provided
by ST gives the coprocessor its wireless abilities. In Flipper Code a specific BLE stack and configuration is loaded 
at build time:

COPRO_CUBE_DIR = "lib/STM32CubeWB"

# Default radio stack
COPRO_STACK_BIN = "stm32wb5x_BLE_Stack_light_fw.bin"
# Firmware also supports "ble_full", but it might not fit into debug builds
COPRO_STACK_TYPE = "ble_light"

The above snippinet is from the Flipper Built Tool (fbt) configuration. By defaullt the BLE stack that gets loaded is
a lightweight version that doesn't have full BLE functionilty. To avoid accidental bricking the Flipper we used
these boards from ST. They are the STM32wb55: https://www.st.com/en/microcontrollers-microprocessors/stm32wb55rg.html
A set of examples of diffrent firmware for the C0+ processor are avaialbe here: https://github.com/STMicroelectronics/STM32CubeWB
FOr our need wil will load stm32wb5x_BLE_Stack_full_extended_fw.bin.

A list of all the availble firmware and information about them can be found in this directory: https://github.com/STMicroelectronics/STM32CubeWB/tree/master/Projects/STM32WB_Copro_Wireless_Binaries/STM32WB5x
The file Release notes details the use and changes to the firmware as well as provide a loading address required. Luckily the ST developers also provided a Zigbee
sniffer example that can be used as a base for a BLE sniffer.  