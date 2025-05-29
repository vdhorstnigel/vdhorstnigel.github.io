---
title: "EE4002D (Final year project)"
description: "My final year project from NUS EE4002D Project 184"
date: 2025-05-27
---

{{< keywordList >}}
{{< keyword icon="github" >}} [Github Repo](https://github.com/vdhorstnigel/EE4002D_FRESH) {{< /keyword >}}
{{< keyword icon = "code" >}} C {{< /keyword >}}
{{< /keywordList >}}

Embedded Electronic Nose: FRESH System for Fridge Food Monitoring 

Ensured freshness of food in a fridge using an embedded electronic nose with machine learning to detect foods that are spoiling

Using ESP32-S3-DevKitC-1U-N8R8, SEN0567, SEN0568, SEN0569 and SPEC Ethylene Sensor 110-650 with a LCD screen attachment.

Developing the code using vscode and ESP-idf


Issues Faced:

Wifi was intermittent and could not connect frequently:
Attached a simple antennae to the ESP to increase the strength. 

LCD had no inbuilt library and was difficult to configure the output.
Tried integrating the Arduino-LiquidCrystal-I2C library but I'm using ESP-IDF 5.4.1 which does not support arduino. Integrated this library instead https://github.com/abdellah2288/esp32-i2c-lcd-driver