# Plant watering ESP8266
_________

[![](https://github.com/MadsBornebusch/PlantWateringESP8266/workflows/Plant%20Watering%20ESP8266%20CI/badge.svg)](https://github.com/MadsBornebusch/PlantWateringESP8266/actions?query=branch%3Amaster)

This is a plant watering ESP8266.

The code is licensed under the GNU GENERAL PUBLIC LICENSE Version 3 in the LICENSE file.

The PCB is licensed under the Creative Commons Attribution-ShareAlike 4.0 license due to using an [ESP8266 kicad library](https://github.com/jdunmire/kicad-ESP8266) and a particular [soil moisture probe design](https://github.com/acolomitchi/cap-soil-moisture-v2).

# PCB

## Pinout when seen from component side:

Left side from top:

- FTDI_RX
- FTDI_TX
- SDA
- SCL
- GND
- Battery VCC

## Right side from top:

- Battery VCC IN
- GND
- VCC (3.3 V)
- Watering OUT

# Settings

The WiFi, ThingSpeak and MQTT settings can be configured via a web interface:

![](img/plant_settings.png)

At first boot the module will turn on a hotspot with the SSID: `PlantWateringESP8266` and password: `plantsarecool`.

After logging on to the WiFI simply navigate to `192.168.4.1` to configure the module.

```

# TODO lists

## TODO

- [x] Add Kicad PCB project
- [x] Add some form of license

## TODO code

- [ ] [OTA update via http](https://arduino-esp8266.readthedocs.io/en/latest/ota_updates/readme.html#http-server)
- [ ] Make a struct for variables to save in RTC memory
- [ ] Only check for OTA update once per day (24 hr)
- [ ] [Use SPIFFS file system to store configuration file (soil moisture etc)](https://arduino-esp8266.readthedocs.io/en/latest/filesystem.html)
- [x] Use MQTT for data
- [x] Show MQTT data in Home Assistant

## TODO code (low priority)

- [ ] Try long sleeps and only wake rf on the last wakeup
- [ ] Define for printing stuff to serial
- [ ] Other ways to read soil moisture?
- [ ] Check power consumption in sleep and awake
- [ ] Header file with definitions?
- [ ] Better structure: move functions out of main files
- [ ] Read I2C sensors (such as BME environment sensors)
