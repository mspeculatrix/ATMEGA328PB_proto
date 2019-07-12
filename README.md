# ATMEGA328PB_proto

**This is a work in progress. It is incomplete and untested.**

This is a breakout/prototyping board for the ATMEGA328PB microcontroller which comes in the TQFP-32 format. It allows programming of the chip and breaks out all the pins to standard DuPont headers for project prototyping. My plan is to mount this PCB on a baseboard alongside a breadboard.

The microcontroller chip is placed in a TQFP-32 adapter, such as [this one](https://www.ebay.com/itm/1Pcs-TQFP32-QFP32-TO-DIP32-28-IC-Programmer-Adapter-Chip-Test-Socket-Pitch-Black/173689092477?ssPageName=STRK%3AMEBIDX%3AIT&_trksid=p2057872.m2749.l2649). These come with carrier boards to make the adapter fit standard DIP footprints. But my board doesn't use this - it just uses the main adapter itself which I intend to solder into my PCB.

The pins for the four ports, B, C, D and E are gathered together logically (whereas they are somewhat scattered around on the microcontroller chip itself).

### Features
* The AVCC pin is connected to VCC using a low-pass filter - ie, via a 10µH inductor with a 0.1µF capacitor to GND. This is Atmel's recommended setup which you want to use the analogue features of the microcontroller but don't want to go to the trouble of providing a separate analogue supply.
* There's a standard 6-pin header to connect an ISP programmer auch as the ATMEL-ICE.
* The ~RESET pin (PC6) has a pullup resistor and a tactile button to reset the microcontroller.
* The standard I2C pins (PC4, PC5) both have two additional pins for easy use of more than one I2C device. The additional pins are accompanied by +5V and GND pins. Onboard 10kΩ pullup resistors can be selected or deselected using jumpers.
* Female headers allow the use of an external crystal. This can be selected or deselected using jumpers. Onboard 22pF capacitors are connected between each leg of the crystal and GND.
* The standard UART pins – RX (PD0) and TX (PD1) have additional pins. These are in a row of six pins, including a GND connection, designed to match the normal order of connections on an FTDI USB-serial cable. Two of the other pins - RTS and CTS - are connected to two more pins. You can then use short female-female jumper cables to connect RTS and DTS to the GPIO pins of your choice.
* Finally, there are three lots of 4-pin connectors all tied to GND. Marked as 'test points', these are for the easy attachment of the GND clip for oscilloscope probes.

### Notes
* The power connector is a simple two-pin header. NO REVERSE POLARITY PROTECTION IS PROVIDED. Nor is there any over-voltage protection.
* The board is intended to be powered by 5V, although it might work on 3.3V (I haven't thought that through).

***
### Resources
* [Background to the project](https://mansfield-devine.com/speculatrix/2019/07/atmega328pb-breakout-and-prototyping-board/)


