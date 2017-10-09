# ESP32-WROOM32-Eagle-Breakout

A breadboard compatible Eagle breakout board for Espressif's ESP32 module ESP-WROOM-32. 

## Credits
I started with the schematic and layout from 
https://github.com/StudioSophisti/ESP-WROOM-32-Eagle-Breakout
and heavily modified it for my purposes. 

## Features
Instead of ordering the board pinout gpios by index, the pinout on the board corresponds to the WROOM-32 module pinout. This ensures
shortest path connections with minimum vias.

Ensured adequate power planes and heatsinking for the WROOM-32 module.  
Added multiple decoupling capacitors, including optional large low ESR tantalum (e.g. 330uF 6.3V). This will prevent brownout resets
when running off power supplies with limited current capacity.

Added two voltage regulator options : SOT-89 LDO regulator (e.g. HT7833 if running off USB, HT7333 if running off Lipoly battery),
or SMPS regulator (TPS82140) for applications where efficiency is important and the source voltage can be up to 17V.

LED on GPIO15. Pull-down resistor on IO2. Pull-up resistor on IO0.

No USB-UART chip on-board, to minimize deep sleep power consumption.

For testing/programming, if your USB-UART dongle 3.3V pin can provide enough power, short R3 and do not populate the regulator ICs. Otherwise, use one of the regulator options, provide power via VIN and leave R3 unpopulated.

The buttons, programming interface and regulator input pins have been placed on the edge to facilitate using the board in a case.

Board dimensions : 35.5mm x 45.5mm

## Assembly notes

This layout is meant for manual assembly. I have placed vias in pads for shortest path to the power planes.  The TPS82140 will have 
to be reflowed with whatever homebrew technique you prefer - e.g. electric skillet. There's no need to risk reflowing the WROOM-32, put 
thermal paste on the ground pad before hand-soldering the module pins.
