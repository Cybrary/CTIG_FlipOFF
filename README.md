# CTIG_FlipOFF

What?
https://www.cybrary.it/blog/ctig-iot-research/

Why?
https://www.cybrary.it/blog/cybrary-counter-stalking-initiative/

Overview
This repo is a collection of findings and tools from other researchers as well as internat research done by Cybrary's CTIG group.
The goal of this researchw as to understand low power trackers like Air Tags, Tie, and Samsung Smarttile and provide
a collection of tools to research and find malicopus use. 

3rd Parties
examples/gap-overwrite - https://github.com/culturally/flipper-zero-airtag
example/openhaystack - https://github.com/AlexStrNik/flipperzero-firmware
example/postive - https://github.com/positive-security/find-you
example/scripts - https://github.com/haxorthematrix/AirTag-tools
example/stm32wb - https://github.com/STMicroelectronics/STM32CubeWB

Detection
There are two methods we use for detection:
1. Scanning all BLE channels and look for behavior consistent with an Air Tag. 
2. Pretend to be a device that an Air Tag weould proxcy data through and wait for connections. 

Scanning channels can work and catch tracker use but there is an element of timing and luck. More ddetails are in 
analysis/scanning. 
