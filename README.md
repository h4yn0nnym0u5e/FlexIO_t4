Overview and Warning: 
=====

This library was originally created to experiment with the FlexIO capabilities of the new Teensy 4 board and
also support the Teensy 4.1 and the Sparkfun Teensy Micromod.


This program is free software: you can redistribute it and/or modify it 

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. 


Details on FlexIO
====================

See chapter 49 of the IMXRT1060RM manual which you can download from the PJRC website:
https://www.pjrc.com/teensy/datasheets.html

There are more discussions about FlexIO up on the PJRC forum, including:
https://forum.pjrc.com/threads/58228-T4-FlexIO-Looking-back-at-my-T4-beta-testing-library-FlexIO_t4


FlexIO pins on T4 and T4.1 and Teensy Micromod
==========================

Note: I have these tables in Teensy pin number order,  It may also be interesting to also have
a version with FlexIO pin order, as at some point I will experiment with parallel pin IO..

Teensy 4.0 
-------------
(ARDUINO_TEENSY40) has the following FlexIO pins defined:

### FlexIO 1 ###
Edited: removed the MUX setting from pin table as all FlexIO1 and FlexIO2 are 0x14 and all FlexIO3 are 0x19


Teensy pin | 2 | 3 |    4 |    5 |  33 
--- | --- | ---  | --- | --- | ---: 
FlexIO pin |    4 |       5 |    6 |    8 |  7 
    
Ranges: 4-8; MUX setting 0x14

### FlexIO 2 ###

Teensy pin | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 32 | 
---       | --- | --- | --- | --- | ---: | ---: | ---: | ---: | ---: 
FlexIO pin | 10 | 17 | 16 | 11 | 0 | 2 | 1 | 3 | 12 | 

Ranges: 0-3, 10-12, 16-17; MUX setting 0x19

### FlexIO 3 ###
__Note Flex IO 3 does not have DMA support__

Teensy pin |    7 | 8 | 14 | 15 | 16 | 17 | 18 | 19 | 20 | 21 | 22 | 23 | 26 | 27 | 
---        | --- | --- | --- | --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: 
FlexIO pin |     17 | 16 | 2 | 3 | 7 | 6 | 1 | 0 | 10 | 11 | 8 | 9 | 14 | 15 | 
Ranges: 0-3,6-11,14-17; MUX setting 0x19

Teensy 4.1
-------------
(ARDUINO_TEENSY41) has additional IO pins.  

### FlexIO 1 ###

Teensy pin |    2 | 3 | 4 | 5 | 33 | 49 | 50 | 52 | 54
---        | --- | --- | --- | --- | ---:  | ---: | ---: | ---: | ---:
FlexIO pin |     4 | 5 | 6 | 8 | 7 | 13 | 14 | 12 | 15

Ranges: 4-8,12-15; MUX setting 0x14

### FlexIO 2 ### 

Teensy pin |    6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 32 | 34 | 35 | 36 | 37
---        | --- | --- | --- | --- | ---: | ---: | ---: | ---: | ---:  | ---: | ---: | ---: | ---:
FlexIO pin |     10 | 17 | 16 | 11 | 0 | 2 | 1 | 3 | 12 | 29 | 28 | 18 | 19

Ranges 0-3, 10-12, 16-19, 28-29; MUX setting 0x14

### FlexIO 3 ### 
__Note FlexIO 3 does not have DMA support__

Teensy pin |    7 | 8 | 14 | 15 | 16 | 17 | 18 | 19 | 20 | 21 | 22 | 23 | 26 | 27 | 34 | 35 | 36 | 37 | 38 | 39 | 40 | 41
---        | --- | --- | --- | --- | ---: | ---: | ---: | ---: | ---:  | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---:
FlexIO pin |     17 | 16 | 2 | 3 | 7 | 6 | 1 | 0 | 10 | 11 | 8 | 9 | 14 | 15 | 29 | 28 | 18 | 19 | 12 | 13 | 4 | 5 

Ranges: 0-19, 28-29; MUX setting 0x19

The Teensy Sparkfun MicroMod 
-------------

(ARDUINO_TEENSY_MICROMOD) is sort of a cross between T4 and T4.1, but has additional pins on FlexIO 2  

### FlexIO 1 ### 
Teensy pin |    2 | 3 | 4 | 5 | 33 | 0xff | 0xff | 0xff | 0xff | 0xff | 0xff | 0xff | 0xff | 0xff | 0xff,
---        | --- | --- | --- | --- | ---: | ---: | ---: | ---: | ---:  | ---: | ---: | ---: | ---: | ---: | ---:
FlexIO pin |     4 | 5 | 6 | 8 | 7 | 0xff | 0xff | 0xff | 0xff | 0xff | 0xff | 0xff | 0xff | 0xff | 0xff,

Ranges: 4-8; MUX setting 0x14

### FlexIO 2 ### 

Teensy pin |    6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 32 | 40 | 41 | 42 | 43 | 44 | 45 | 
---        | --- | --- | --- | --- | ---: | ---: | ---: | ---: | ---:  | ---: | ---: | ---: | ---: | ---: | ---:
FlexIO pin |     10 | 17 | 16 | 11 | 0 | 2 | 1 | 3 | 12 | 4 | 5 | 6 | 7 | 8 | 9 | 

Ranges 0-12, 16-17; MUX setting 0x14

### FlexIO 3 ### 
__Note FlexIO 3 does not have DMA support__

Teensy pin |    7 | 8 | 14 | 15 | 16 | 17 | 18 | 19 | 20 | 21 | 22 | 23 | 26 | 27 | 0xff | 
---        | --- | --- | --- | --- | ---: | ---: | ---: | ---: | ---:  | ---: | ---: | ---: | ---: | ---: | ---:
FlexIO pin |     17 | 16 | 2 | 3 | 7 | 6 | 1 | 0 | 10 | 11 | 8 | 9 | 14 | 15 | 0xff | 

Ranges: 0-3,6-11,14-17; MUX setting 0x19


NOTE:
=====
This version of the library removed the need to have different tables for each version of the
Teensy that is built using the IMXRT1060.  Instead the tables for each FlexIO object is built
with the complete list of possible FlexIO pins, and then maps the Teensy pin to the IMXRT
pin by using the Pin Mux address in the pin table associated with that actual teensy.

Library details
===============

FlexIOHandler
-------------

The top level class in this library is the class: FlexIOHandler, which tries to do some limited resourse management.
Like mapping an IO pin to which FlexIO object is is on and the actual item on that flexio object.  It also then
allocates other resources like timers and shifters.

There are also a few methods to help with the CCM (Clock Management), for example:
```
uint32_t computeClockRate();
```
Returns the speed that the specified FlexIO is running at, which is controlled by registers in CCM.  Default is 480M/16
or 30000000

You can update this with the method:

```
// clksel(0-3: PLL4, Pll3 PFD2, PLL5, *PLL3_sw)
// clk_pred(0, *1, 2, 7) - divide (n+1)
// clk_podf(0, *7) divide (n+1)
// So default is 480mhz/16
void setClockSettings(uint8_t clk_sel, uint8_t clk_pred, uint8_t clk_podf);
```

The main reason for the desire to for example allow slower baud/clock rates with the SPI and Uart code.

For example with the FlexSerial object, the Baud divider is one byte so without updating the clock speed 
So the default of 30000000 and max divide by 256 = min Baud of 117,187.5/ 2 = 58,594
Now setting the pred to 7 your minimum baud reduces to: 29296.875 / 2 about 14,648

FlexIO SPI
------
Most methods are similar to the existing SPI library.

## Constructor ##
``` c++
FlexIOSPI(int mosiPin, int misoPin, int sckPin, int csPin = -1)
```
If the CS pin is not given then the user code is responsible for asserting and negating it as needed. If it _is_ given, then it will be asserted at the start of
each byte / word / long transferred, and negated at the end. 

## Asynchronous methods ##
These transfer data to/from buffer memory, and trigger an EventResponder
callback once complete. 
``` c++
transfer(const void* src, void* dst, size_t count, EventResponder& evRef);
transfer16(const void* src, void* dst, size_t count, EventResponder& evRef);
transfer32(const void* src, void* dst, size_t count, EventResponder& evRef);
```

Future Updates
==============


Again WIP
=====
