---
title: "Sensor Boilerplate"
date: 2019-05-17T12:44:38-07:00
draft: false
tags: ["electronics", "sensors", "adafruit"]
topics: []
description: "The Beginning, A Very Good Place to Start"
---

## Microcontrollers

The Adafruit Feather family of microcontrollers is compact and with loads of useful expansion options. The latest and greatest as of now is the "Feather M4 Express" powered by the 120MHz ATSAMD51J19. This board ships with CircuitPython, Adafruit's simplified distribution of Micropython, and 2MB of flash for library, script, and data storage. Priced under $25, its a no brainer for anyone and everyone wanting to break into hobby electronics of just about any flavor. Circuitpython makes development faster and less beginner-error-prone than C code.

Adafruit has excellent documentation, [click here][m4_docs] for relevant M4 Express details.

## Sensors

In addition to microcontrollers, the Feather family also has expansion boards with all sorts of functions.

#### ADXL343 Accelerometer

The ADXL343 is a digital, 3-axis accelerometer with a ton of features. The most immediate sensing projects here will likely involve the "slow" end 2g scale measurements of seismic movement. This module has its own, on-board 10-bit ADC and sends data to the μC over i2C.

Documentation, including Circuitpython examples, is [found here][adxl343_docs].

#### VEML7700 Ambient Light Sensors

The VEML7700 has its own on-board ADC with 16bits of dynamic range, sending data over i2C.

Documentation, including Circuitpython examples, is [found here][veml7700_docs].

[m4_docs]: https://learn.adafruit.com/adafruit-feather-m4-express-atsamd51
[adxl343_docs]: https://learn.adafruit.com/adxl343-breakout-learning-guide
[veml7700_docs]: https://learn.adafruit.com/adafruit-veml7700
