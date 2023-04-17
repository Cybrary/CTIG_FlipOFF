# CTIG_FlipOFF

* What? https://www.cybrary.it/blog/ctig-iot-research/
* Why? https://www.cybrary.it/blog/cybrary-counter-stalking-initiative/

# Overview
This repo is a collection of findings and tools from other researchers and internet research done by the Cybrary Threat Intelligence Group (CTIG.) This research aimed to understand low-power trackers like Air Tags, Tile, and Samsung SmartTag and provide a collection of tools to research and find malicious use.
3rd Parties 
* examples/gap-overwrite - https://github.com/culturally/flipper-zero-airtag 
* example/openhaystack - https://github.com/AlexStrNik/flipperzero-firmware 
* example/postive - https://github.com/positive-security/find-you 
* example/scripts - https://github.com/haxorthematrix/AirTag-tools 
* example/stm32wb - https://github.com/STMicroelectronics/STM32CubeWB

# Detection
There are two methods we use for detection:
Scanning all BLE channels and looking for behavior consistent with an Air Tag.
Pretend to be a device that an Air Tag would proxy data through and wait for connections.
Scanning channels can catch tracker use, but there is an element of timing and luck. Additional details are in the analysis/scanning.
