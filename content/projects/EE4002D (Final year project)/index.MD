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

Ensured freshness of food in a fridge using an embedded electronic nose with machine learning to detect foods that are spoiling.

Using ESP32-S3-DevKitC-1U-N8R8, SEN0567, SEN0568, SEN0569 and SPEC Ethylene Sensor 110-650 with a LCD screen attachment.

Developing the code using vscode and ESP-idf

## ESP-IDF vs Arduino vs Micropython:
### ESP-IDF:
I am using the ESP-IDF as there is a supported plugin on vscode for it, its more modular as I can separate each function in its own C file, its lightweight and fast. I can also work on the machine learning code without the microcontroller as I can run and compile C on my computer.

### Arduino:
Arduino is much more simpler to use, with many libraries available that I can use but its not as modular. As this project is a pair project, only one person has access to the ESP micro controller, so its difficult to do collaboration if we use arduino. I am also less familiar with arduino. It also slightly more bloated than pure C.

### Micropython:
Micropython is the easiest language to use and I am the most familiar with it, but it suffers from performance. However, it would be the best backup as it is the best suited for machine learning.

## Topics learnt
Header vs C files
static & volatile variables

## Reading the analog sensors:
To read the analog sensors, I connected the sensors to the GPIO pins on ADC1, ADC2 is not recommended to be used as its reserved for WIFI.
I use the esp adc oneshot libary to get the values instead of the continous library as I only get the values every 3 seconds, it would be easier than constantly reading the the sensors and get a sample instead.
![Sensor](sensor_read.png "Serial print of the analog values")

## Wifi connection:
For the wifi, I used the wifi_connect library and modified the code slightly to what I need. This works well very well except that the antannae is not strong enough and need an external antannae to connect better. I also used a WIFI_CONNECTED flag that i set to true or false if the wifi is connected. This allows me to only send data when wifi is connected. I read that using Xeventgroup is good to wait til the wifi is connected before proceeding however, I do not know if this is suitable for my need. I will continue using the wifi_connected flag first.

## MQTT broker:
For MQTT connection, I was initially using the sample mqtt5 program given, but it was very convuluted and bloated. So I decided to keep only the mqtt initialization and do a single publish using esp_mqtt_client_publish. I also had to import the certificate to connect to the broker over mqtts.

## Issues Faced:
### Wifi was intermittent and could not connect frequently:
Attached a simple antennae to the ESP to increase the strength. 

### LCD had no inbuilt library and was difficult to configure the output:
Tried integrating the Arduino-LiquidCrystal-I2C library but I'm using ESP-IDF 5.4.1 which does not support arduino. Integrated this library instead https://github.com/abdellah2288/esp32-i2c-lcd-driver

### Main code stopped running after initializing wifi
Found out that loose cables made the initializing fail when trying to read the sensors, always ensure your connections are secure!

### LCD stopped working and sensors values inaccurate:
One of the sensor got shorted, causing voltage issues when reading the analog output. It also heated up really quickly and burnt my finger when i check on it, I only knew it was burning when i smelt something burning. So please check your connections carefully!