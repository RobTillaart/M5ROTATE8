
[![Arduino CI](https://github.com/RobTillaart/M5ROTATE8/workflows/Arduino%20CI/badge.svg)](https://github.com/marketplace/actions/arduino_ci)
[![Arduino-lint](https://github.com/RobTillaart/M5ROTATE8/actions/workflows/arduino-lint.yml/badge.svg)](https://github.com/RobTillaart/M5ROTATE8/actions/workflows/arduino-lint.yml)
[![JSON check](https://github.com/RobTillaart/M5ROTATE8/actions/workflows/jsoncheck.yml/badge.svg)](https://github.com/RobTillaart/M5ROTATE8/actions/workflows/jsoncheck.yml)
[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](https://github.com/RobTillaart/M5ROTATE8/blob/master/LICENSE)
[![GitHub release](https://img.shields.io/github/release/RobTillaart/M5ROTATE8.svg?maxAge=3600)](https://github.com/RobTillaart/M5ROTATE8/releases)


# M5ROTATE8

Arduino library for m5 8angle 8x12 bit potentiometers.


## Description

**Experimental**

M5ROTATE8 is an Arduino class 


No tests with hardware have been done yet, so use with care.
Feedback welcome!


#### I2C

TODO to what clock does it work?
Address range?

#### Related

- https://github.com/RobTillaart/map2colour


## Interface

```cpp
#include "M5ROTATE8.h"
```

- **M5ROTATE8(uint8_t address = 0x43, TwoWire \*wire = &Wire)** constructor.
Default address = 0x43, default Wire.
- **bool begin(int sda, int scl)** ESP32 et al.
- **bool begin()** initialize I2C, check if connected.
- **bool isConnected()** checks if address is on the I2C bus.
- **bool setAddress(uint8_t address)** set a new address for the device.
- **uint8_t getAddress()** convenience function. 
- **uint8_t getVersion()** get firmware version from device.

#### IO part

- **uint16_t analogRead(uint8_t channel, uint8_t resolution = 12)**
Read a potentiometer, if resolution = 8 (0..255) otherwise (0..4095).
- **uint8_t inputSwitch()** read status of the switch.
- **bool writeRGB(uint8_t channel, uint8_t R, uint8_t G, uint8_t B, uint8_t brightness)** Set the RGB value and brightness of a LED.
- **bool allOff()** switches all LEDs off.


## Future

#### Must

- improve documentation
- test with hardware

TODO before release
- magic numbers


#### Should

- error handling

#### Could

- add examples
- add unit tests
- check performance
- caching?
- **writeBrightness(channel)**


#### Wont (unless)



