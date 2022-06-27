Last update: April 24th, 2020

![](https://img.shields.io/badge/Home%20Assistant-0.103.5-blue.svg)
![](https://img.shields.io/github/last-commit/rbisschops/homeassistant.svg)
[![](https://img.shields.io/github/issues-raw/rbisschops/homeassistant)](https://github.com/rbisschops/homeassistant/issues)

<div align="center"><a name="menu"></a>
  <h4>
    <a href="#my-home-server">My Home server</a>
    <span> | </span>
    <a href="#home-assistant">Home Assistant</a>
    <span> | </span>
    <a href="#devices-and-services">Devices and services</a>
    <span> | </span>
    <a href="#things-planned">Things planned</a>
    <span> | </span>
    <a href="#development">Development</a>
    <span> | </span>
    <a href="#license">License</a>
  </h4>
</div>

# [My Home server](#my-home-server)

Here's my [Home Assistant](https://home-assistant.io/) configuration. I have installed Home Assistant on an custom build PC. The PC is running as a "Home server". I am currently running Ubuntu 18.04 LTS on the PC. Home Assistant as well as all supporting appllications (and some additional non Home Assistant related applications) are running in Docker containers. Home assistant is running on HASS.io as are some of the add-ons.

## Things that I run on my Home server
* [Home Assistant](https://home-assistant.io/), home automation solution running as HASS.io version.

Home assistant add-ons:
* [ESPHome](https://esphome.io/), used for connecting all kinds of sensors to Home Assistant. Intend to add a lot of ESP32 based sensors with this (for example for Bluetooth devices)
* [Node-RED](https://nodered.org), flow based programming, an intuitive addition to both Home Assistant and Domoticz (or any other home automation system).

Stand alone containers:
* [Mosquitto](https://mosquitto.org/), my favourite MQTT Broker. Used for exchanging data between a lot of applications and from the outside world (through the reverse proxy).
* [Zigbee2MQTT](https://koenkk.github.io/zigbee2mqtt/), great development for getting rid of most of the proprietary bridges. I use it for all my ZigBee devices except for Hue.
* [InfluxDB](https://www.influxdata.com/), a time series database. Installed, tested but not used yet.
* [Grafana](https://grafana.com/), analytics and monitoring. Installed, tested but not used yet.
* [Traefik](https://traefik.io/), reverse proxy for secure access from the outside world.
* [Unifi Controller](https://www.ui.com/), for managing my Ubiquiti Access points.
* [Portainer](https://www.portainer.io/), makes managing my Docker containers easy.
* [Domoticz](https://www.domoticz.com/), running as a legacy solution for collecting the data of the MySensors watermeter.

Standalone solutions
A number of solutions have their own hardware, mostly raspberry Pi's:
* [Domoticz](https://www.domoticz.com/), running on a Raspberry Pi. This Domoticz instance will retire when everything is migrated to Home Assistant (mainly the RFXtrx and the CoCo hardware).
* [HA Bridge](https://www.bwssystems.com/#), running an emulated Hue bridge. I use it for connecting my Amazon Alexa Echo-dot to Home Assistant.
* [MySensors gateway](https://www.mysensors.org/), The gateway for the MySensors devices around the house. Running on a Raspberry Pi.
* [DSMR Reader](https://dsmr-reader.readthedocs.io/nl/v3/), Application for monitoring the energy usage in the use. Connects to Homeassistant for displaying the daily usage.

# [Home Assistant](#home-assistant)

Home Assistant and Domoticz are running in parallel at the moment. I spent quite some time to get the two working together. Home Assistant is the main home automation application.

**I regularly update my configuration files as my Home server is still under development.**

## Home Assistant setup

### Home Assistant configuration
After looking at a ton of configurations and playing around with them I decided to go for packages. All my configurations are now in packages grouped as logical collections of components, entities automations etc. ,mostly room based.

For example package_notification contains the applied notification components (Prowl, Telegram and Pushsafer currently), the associated entities, automations and scripts. Most scripts can be  used by other packages that require  notifications to be sent.

### Lovelace UI
Like all by now run Lovelace as the UI.
I use a number of custom cards and helpers in my Lovelace. I will do some write up on these later but here are the ones I use now.
* [compact-custom-header](https://github.com/maykar/custom-header), card by Ryan Meek (maykar) for customizing the header of your UI.
* [decluttering-card](https://github.com/custom-cards/decluttering-card), card by Jérôme W (RomRider). This card significantly reduces the number of lines in your Lovelace configuration. Helps structure your code.
* [mini-graph-card](https://github.com/kalkih/mini-graph-card), nice graphs of your data can be created with this card. Good work delivered by Karl Kihlström (kalkih).
* [button-card](https://github.com/custom-cards/button-card), customize your buttons with this card. Started by Alexandre Garcia this card now has many active contributors.
* [card-mod](https://github.com/thomasloven/lovelace-card-mod), Adds CSS styles to (almost) any lovelace card. Powerful custom card by Thomas Lovén (thomasloven)

When things are progressing I will upload some screenshots of my UI.

# [Devices and services](#devices-and-services)

* Zwave:
  * [Aeotec Z-Stick Gen5](https://aeotec.com/z-wave-usb-stick) Z-Wave controller.
  * [Heatit Thermostat](https://www.heatit.com/heating-control/floor-heating-thermostats/heatit-z-wave-thermostat/) Z-Wave thermostat for controlling the electrical heating in one room.
  * [Neo Coolcam sensors](https://www.szneo.com/) Motion sensors and door/window sensors. Available at AliExpress for competitive prices.
  * [Fibaro smoke sensors](https://www.fibaro.com/en/) The best looking smoke detectors on the market (IMHO).

* Zigbee:
  * [Xiaomi Aqara sensors](https://www.aliexpress.com) I use motion sensors, door/window sensors, temp/hum/pressure sensors, vibration sensors, light sensors, a magic cube (nice gadget!) and some buttons. All sensors are connected to Home Assistant (through Zigbee2mqtt)
  * [Philips Hue](https://www2.meethue.com) Philips Hue bulbs used in the house. Operated through the Hue Bridge. The ambiance (colour) is controlled form Home Assistant where I decided to go for profiles instead of scenes.
  * [IKEA Trådfri](https://www.ikea.com) Cheap ZigBee compatible smart home devices. Currently I use Wireless control outlets for the more critical switches (replacement of Click-On-Click-Off units) and a repeater. I'm not convinced with the quality and the performance.  All entities are connected to Home Assistant (through Zigbee2mqtt)
  * The Aqara bridge is retired. 

* MySensors platform:
  * [MySensors](https://www.mysensors.org/) The MySensors platform offers a solution for developing highly customized sensors and actors. I run a Raspberry Pi as gateway and use NRF24 radio modules. I have developed a [custom water meter sensor](https://www.openhardware.io/view/15/Itron-Aquadis-watermeter-sensor-V10) to read my dumb water meter values. Connected to Domoticz since all my history is logged there as well. Planning to replace this with a ESP based solution.

* MQTT:
  * [OwnTracks](https://home-assistant.io/components/device_tracker.owntracks/) Presence detection is an important part of the home automation. OwnTracks is used for Geolocation over MQTT.

* Wi-Fi and network:
  * [Netgear Nighthawk](https://www.netgear.nl/home/products/networking/wifi-routers/R7000.aspx), the centre of all the networking activities in the house. Connects to all devices that require wired networking and to the Wi-Fi AP's. Several unmanaged switches are used to connect wired devices in the house. The Nighthawk submits the status information of all connected devices to Home Assistant. This way I can track if everything is still online. Connected mobile phones are tracked for additional presence detection. 
  * [Unifi AP AC Lite](https://www.ui.com/unifi/unifi-ap-ac-lite/), the access points I use in the house to support full Wi-Fi coverage for the mobile and Wi-Fi connected devices.

* Voice control:
  * [Amazon Echo Dot 2nd gen.](https://amazon.com), Echo dot 2nd generation used for voice control. Currently this runs through the HA Bridge. Will be exchanged with Home Assistant native Amazon Alexa support in the future.
  * [Google Home Mini](https://store.google.com/product/google_home_mini), currently not in use. But successfully tested with Home Assistant.

* Media devices:
  * [LG Television](https://www.lg.com), my LG television running LG WebOS is controlled by Home Assistant mainly for choosing the correct mode for things like Netflix and Spotify.
  * [Popcorn Hour](https://www.cloudmedia.com/), a classic in my house, the Popcorn A300. Mainly controlled with the Harmony Hub, but some initial settings are done by Home Assistant at start up.
  * [Denon AVR-X3600H](https://www.denon.com), AV receiver with network connect. powerful for internet radio and streaming music, direct control over Home Assistant is partly implemented though not complete yet. As the device is HEOS compatible, this should open integration possibilities.
  * [Humax iHRD-5050c](https://myhumax.info/), this is an older cable receiver, but still working. Used for cable television and radio. I can control the Humax over the Harmony Hub.
  * [Apple TV](https://www.apple.com), not much used anymore these days as the LG can do most of it.
  * [Harmony Hub](https://www.logitech.com), the Harmony Hub, despite Logitech's poor way of supporting interoperability, a powerful device for controlling the media devices. Integrated with Home Assistant. I spent a lot of time in getting it running in Home Assistant. Still some lose ends but I'm getting there.

# [Things planned](#things-planned)

Some projects I have planned:
* Water meter sensor version 3.0 based on ESP32
* Presence sensors for the garbage binds based on ESP32 with Bluetooth beacons
* Water temperature sensors for monitoring and tuning the heating system (aka zone based heating system)
* Add camera's for home security
* Add motion sensors and automations to switch on lights for orientation at night time

Many ideas, too little time! I will add some more projects later.
When I find the time I will write a blog or something alike about my Home automation projects.

# [Development](#development)

I develop most of my applications in [Microsoft Visual Studio Code](https://code.visualstudio.com/). VS code has some nice extensions for checking the YAML syntax.

If you have questions on my configuration, ping me on twitter [@rbisschops](https://twitter.com/rbisschops)

If my works helps you reduce time to develop, you can always consider buying me a cup of coffee.

<a href="https://www.buymeacoffee.com/rbisschops" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: auto !important;width: auto !important;" ></a>

# [License](#license)

MIT License

Copyright (c) 2020 Ralph Bisschops

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
