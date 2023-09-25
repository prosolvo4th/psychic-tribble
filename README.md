# stlink_v2_RST_SWO_mod 
=
Description of adding RST and SWO pins in Chinese clone of stlink v2 for STM32

This info is based on [Habr post](https://habr.com/ru/articles/402927/).

# TL;DR

Cut unused pins on the connector.
Solder pins N18 (reset) and N31(SWO) to connectors pins through 22Ohm resistors.

# How to check Reset

Just use STM32 ST-LINK Utility and set "Connect under reset" in the "Mode" options.

# How to check SWO (in STM32Cube)

- activate SWD
- set the corresponding pin (for STM32F103C it is `PB3`) to `TRACESWO`
- check that set `SWO` in your environment, and not `semihosting`
- add `#include «stdio.h»`
- add `printf(«Hello STM32 world!\r\n»)`
