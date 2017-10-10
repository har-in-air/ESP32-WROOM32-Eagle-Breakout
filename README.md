# ESP32-WROOM32-Eagle-Breakout

A breadboard compatible Eagle breakout board for Espressif's ESP32 module ESP-WROOM-32. 

## Credits
I started with the schematic and layout from 
https://github.com/StudioSophisti/ESP-WROOM-32-Eagle-Breakout
and heavily modified it for my purposes. 

## Features
Pinout on the board corresponds to the WROOM-32 module pinout. This ensures shortest path connections with minimum vias.

Adequate power planes and heatsinking for the WROOM-32 module.  

Multiple decoupling capacitors, including optional large low ESR tantalum (e.g. 330uF 6.3V). This will prevent brownout resets
when running off power supplies with limited current capacity.

Added two voltage regulator options : 
1. SOT-89 LDO regulator (e.g. HT7833 if running off USB, HT7333 if running off Lipoly battery), OR
2. SMPS regulator (TPS82140) when efficiency is important and the source voltage can be up to 17V

LED on IO15. Pull-down resistor on IO2. Pull-up resistor on IO0.

No USB-UART chip on-board, to minimize deep sleep power consumption.

For testing/programming, if your USB-UART dongle 3.3V pin can provide enough power, short R3 and do not populate the regulator ICs. Otherwise, use one of the regulator options, provide power via VIN and leave R3 unpopulated.

The buttons, programming interface and regulator input pins have been placed on the edge to facilitate using the board in a case.

Pinout silkscreen on top AND bottom.

Board dimensions : ~ 36mm x 46mm

Resistors are 0603 package. Capacitors are 0603 except for C6 (tantalum, Vishay-C). You can find suitable capacitors (0603 X5R, X7R) on Aliexpress and Ebay e.g. https://mcigicm.aliexpress.com/store/506373?spm=2114.10010108.0.0.15e3fdeesSP1Dd

The most inexpensive pcb prototyping service I've found is pcbway.com : 10 PCBs  (2-layer, < 100mm x 100mm ) for US$5 + shipping. Great quality, but in my experience, it takes about 4-5 weeks from order to delivery with the cheapest shipping option.

## Assembly notes

This layout is meant for manual assembly. I have placed vias in pads for shortest path to the power planes.  The TPS82140 will have 
to be reflowed with the home-brew method of your choice - e.g. electric skillet. There's no need to risk reflowing the WROOM-32, just put thermal paste on the ground pad before hand-soldering the module pins.
