Adafruit CircuitPython BusDevice For MicroPython
================================

A fork of https://github.com/adafruit/Adafruit_CircuitPython_BusDevice to work in MicroPython on Raspberry Pi Pico. It may or may not work on other MicroPython hardware

I've driven a bus through some probably very well thought out enginerring in order to get this to work. It may or may not need to be added back in at a later stage.

So far, I've only done I2C as I don't have any SPI devices to test with.

Changes:
*removed try_lock as that concept doesn't seem to exist in MicroPython
*readto and writeto are both no longer using their start and stop parameters. This may cause a problem for some sensors.

Currently tested devices
Pimoroni BMP280 breakout.

Example code (you'll also need this file saved on your device: https://github.com/adafruit/Adafruit_CircuitPython_BMP280/blob/master/adafruit_bmp280.py)

```
from machine import Pin, I2C
i2c = I2C(0,scl=Pin(21), sda=Pin(20))

import adafruit_bmp280
sensor = adafruit_bmp280.Adafruit_BMP280_I2C(i2c, address=0x76)
```
