# Changelog

As of 2020-03-25 All notable changes to my Homeassistant configuration will be documented in this file.

## [1.6.0]
### 2021-01-13
- Added template sensors for monitoring, filtering and alerting on battery levels of wireless devices.
- Added new Xiaomi Aqara LLKZMK11LM Dual Switch for the garden, decomissioned CoCo switch.
- Added Xiaomi Mijia WXKG01LM wireless switch for light control for the second floor room.
### 2021-01-03
- Added new Lonsonho QS-Zigbee-D02-TRIAC-LN dimmer for second floor room, decommisioned CoCo dimmer.
### 2020-12-29
- Updated: Minor changes to picture-elements cards.
- Updated: Complete overhaul of picture-elements cards incl. the creation of new buttons and icons.
- Updated: Revision of a number of flows in Node-RED related to: precense, scenes, light behaviour.
- Removed: Commented automations ans scripts from HA (these are all in Node-RED now).
- Added: custom card for labels in picture-elements cards ([text-element card](https://github.com/custom-cards/text-element)).
- Added: Lidl/Silvercrest ZigBee powerplugs for high cabinets and christmas tree.
- Updated: A number of small changes in Node-RED flows.
- Updated: started clean-up of Lovelace custom cards configurations
### 2020-11-16
- Updated: HA  0.114.1 sequential to version 0.117.6
## 2020-11-04
- Added: Node-RED flows for lightcontrol based on Xiaomi light sensors icncluding supporting input_booleans in HA. 
### 2020-08-21
- Updated: HA to version 0.114.1

## [1.5.0]
### 2020-09-25
- Added windows on the 2nd floor to the UI. [Issue #013](https://github.com/rbisschops/homeassistant/issues/13)
- Added experimental wake-up light function in Node-RED. [Issue #042](https://github.com/rbisschops/homeassistant/issues/42)
### 2020-09-24
- Added new garbage bin (paper) for testing earlier notification (day before). [Issue #041](https://github.com/rbisschops/homeassistant/issues/41)
- Added BLE temp/humidity sensors based on BLE Xiaomi Mijia devices
- Added BLE tracker based on ESPHome/ESP32. [Issue #043](https://github.com/rbisschops/homeassistant/issues/43)
### 2020-09-20
- Disabled all YAML automations and scripts that moved to Node-RED over the last weeks. Rebooted HA with "clean" config.
- Disabled all YAML based entities that are no longer in use.
- Migrated last automations and scripts to Node-RED over the past weeks.

## [1.4.0] 
### 2020-08-20
- Migrated humidity notifications to Node-RED.
- Migrated netwrok alerts to Node-RED.
- Migrated battery status alerts to Node-RED.
- All notification are now in Node-RED incl. mechanism to hold notifications when we are away or sleeping.
### 2020-08-17
- Updated: Changed buienradar interval to 5 minutes.
- Updated: Changed names for garbage calendar, conflicts with names for garbage bins in Node-RED.
- Added: State of cartridges for the HP printer in Lovelace-UI. 
- Removed: Server states for the Domoticz (master) server from the Lovelace-UI.
- Updated: Started updates on Hue lamps logic in Node_RED.
### 2020-08-16
- Created backups of all Node_RED flows ans node JavaScript (Part 2).
- Added: New iPhone for family member including notifications and person settings.
### 2020-08-15
- Created backups of all Node_RED flows ans node JavaScript (Part 1).
### 2020-08-13
- Updated: Some lovelace updates for the home dashboard.
- Updated: Notifications to allow for priority during silent hours and away from home times 
### 2020-08-12:
- Updated: Notification silence during night time (based on bed time scene) to Node-RED was not working well.
### 2020-08-11:
- Added: Small node-RED flow for slave storage door input_boolean (10 sec. delayed off)
- Added: Test automation with new choose function for test in HA for slave storage door input_boolean.
- Added: Slave input_boolean.door_storage_door_delayed for delayed off (used for mailbox sensor).
- Added: Added silence during night time (based on bed time scene) to Node-RED.
### 2020-08-10:
- Added: Node-RED queue for notifications so notifications are stored when someone is not home.
### 2020-08-09:
- Added: Notification in Node-RED, disabled HA notification automations and scripts.

## [1.3.0] - 2020-07-29
- Changed: Moved RfxTrx integration from Domoticz to HA including update of all actuators and sensors
- Added: Glances integration for monitoring server HW 
- Bugfix: Wrong payload send to livingroom lights state input_select
- Migrated media center control to Node-RED.
- Updated: Node-RED flows for lighting.
- Removed: Hue from config files (yaml). Is now integration.
- Updated: theme files to remove paper as class.
- Updated: HA to version 0.113.2

## [1.2.0] - 2020-07-04
- Updated custome header configuration
- Updated mini-graph-card-bundle to version 0.9.4
- Updated button-card to version 3.3.6
- Updated custom-header to version 1.6.5
- Updated decluttering-card to version 0.6.3
- Updated card-mod to version 14
- Updated HA to version 0.112.2

## [1.1.0] - 2020-06-07
#### Changed
- Migrated rest room heating to Node-RED. [Issue #040](https://github.com/rbisschops/homeassistant/issues/40)
- Migrated scenes to Node-RED. [Issue #039](https://github.com/rbisschops/homeassistant/issues/39)
- Migrated presence detection to Node-RED. [Issue #038](https://github.com/rbisschops/homeassistant/issues/38)
- Migrated porch light to Node-RED. [Issue #037](https://github.com/rbisschops/homeassistant/issues/37)
- Migrated hallway lights to Node-RED. [Issue #036](https://github.com/rbisschops/homeassistant/issues/36)
- Migrated livingroom hue lights to Node-RED. [Issue #035](https://github.com/rbisschops/homeassistant/issues/35)
- Migrated high cabinets lights to Node-RED. [Issue #034](https://github.com/rbisschops/homeassistant/issues/34)
- Migrating bar lights to Node-RED. [Issue #033](https://github.com/rbisschops/homeassistant/issues/33)
- NodeRed: Migrating water ornament to Node-RED. [Issue #032](https://github.com/rbisschops/homeassistant/issues/32)
- NodeRed: Migrated the christmas tree to Node-RED. [Issue #030](https://github.com/rbisschops/homeassistant/issues/30)
- NodeRed: Migrated the garden lights to Node-RED. [Issue #031](https://github.com/rbisschops/homeassistant/issues/31)

## [1.0.0] - 2020-04-24
- Release before introduction of Node-RED

## [0.9.19] - 2020-04-24
#### Changed
- Changed switch entities. Mostly only added freindly names [Issue #007](https://github.com/rbisschops/homeassistant/issues/7)
- Updated HA to version 0.108.8

## [0.9.18] - 2020-04-23
#### Changed
- Changed light entity types. Most come from hue bridge, so not possible to change these.
- Removed water ornament from UI as this item is removed from the garden.

### Bug fixes
-entity light.program_missed was showing as light.dim_bar_lights. Removed device from HA Brdige and re-entered it

## [0.9.17] - 2020-04-22
#### Removed
- Removed MySensors integration as it is currently not used. [Issue #029](https://github.com/rbisschops/homeassistant/issues/29)

## [0.9.16] - 2020-04-20
#### Changed
- Changed Z-Wave sensor names to more logical names. [Issue #007](https://github.com/rbisschops/homeassistant/issues/7)
- Changed Z-Wave device names to more logical names. [Issue #007](https://github.com/rbisschops/homeassistant/issues/7)

### Added
- Added seperate automation for sending alerts when not home. Now every trigger of someone coming home is kicking of the automation. 

## [0.9.15] - 2020-04-18
#### Changed
- Promoted dashboard items for showing the humidity in the house by means of RAG (Red-Amber-Green) indicators to final. [Issue #025](https://github.com/rbisschops/homeassistant/issues/25)

### Bug fixes
- Fixed wrong entity ID for timer Zigbee2MQTT in Lovelace UI tab settings. [Issue #026](https://github.com/rbisschops/homeassistant/issues/26)

### Added
- Mechanism to send alerts at 08:00 (after nightly silence) and at homecoming See [Issue #028](https://github.com/rbisschops/homeassistant/issues/28)
- Added functions for monitoring sensors that are no longer updating See [Issue #027](https://github.com/rbisschops/homeassistant/issues/27)  

## [0.9.14] - 2020-04-15
### Added
- Added experimental dashboard items for showing the humidity in the house by means of RAG (Red-Amber-Green) indicators. [Issue #025](https://github.com/rbisschops/homeassistant/issues/25)

### Removed
- removed template sensors for RAG from package.environment.yaml (sensor.environment_livingroom_humidity_rag & sensor.environment_test_humidity_rag) Not used.

## [0.9.13] - 2020-04-13
### Changed
- Changed behavior of humidity warmings for livingroom. [Issue #024](https://github.com/rbisschops/homeassistant/issues/24)

## [0.9.12] - 2020-04-12
### Bug fixes
- Fixed: Triggers  missing for Pathe thuis and Disney+ in automations: Media - actions triggered from UI, Media - actions triggered from HA-Bridge, Media - actions triggered from Harmony Hub
- Fixed: Trigger for Uitzending gemist from HA Bridge in automation Media - actions triggered from HA-Bridge was wrong, no binanry sensor used.

## [0.9.11] - 2020-04-11
### Bug fixes
- Fixed: Friendly name input_boolean.dummy_side_room_window [Issue #022](https://github.com/rbisschops/homeassistant/issues/22)
- Fixed: Name changed to Zigbee joinen toegestaan voor input_boolean.zigbee2mqtt_permit_join [Issue #023](https://github.com/rbisschops/homeassistant/issues/23)

### Changed
- Changed name of most network sensors from nc_xxx to network_xxx in all files
- Changed decluttering template for stats_critical_small_icon and stats_normal_small_icon to match network_ instead of nc_
- sensors: Changed multiple entities names to more logical names.
- Sensors: Added missing friendly names

### Removed
- Removed unused groups from file package_network.yaml

### Added
- Support for Disney+ source selection on LG television. Requires testing! [Issue #019](https://github.com/rbisschops/homeassistant/issues/19)
- Support for Pathé Thuis source selection on LG television. Requires testing! [Issue #020](https://github.com/rbisschops/homeassistant/issues/20)
- Support for Uitzending gemist source selection on LG television. Requires testing! [Issue #018](https://github.com/rbisschops/homeassistant/issues/18)

## [0.9.10] - 2020-04-07
### Bug fixes
- Fixed: File media_center.yaml. Multiple wrong names for input_booolean.media_program_missed (Uitzending gemist).
- Fixed: File media_center.yaml. Wrong reference for input_boolean.media_mediaplayer (still media_player used in dict).

## [0.9.9] - 2020-04-07
### Added
- Lovelace: Button for Uitzending gemist added to mediaplayer tab (mediaplayer.yaml). [Issue #018](https://github.com/rbisschops/homeassistant/issues/18)
- Lovelace: Button for Disney+ added to mediaplayer tab (mediaplayer.yaml). [Issue #019](https://github.com/rbisschops/homeassistant/issues/19)
- Lovelace: Button for Pathe thuis added to mediaplayer tab (mediaplayer.yaml). [Issue #020](https://github.com/rbisschops/homeassistant/issues/20)

### Changed
- Lovelace: Changed media_button_large to support pictures additional to icons. [Issue #021](https://github.com/rbisschops/homeassistant/issues/21)
- Lovelace: Changed mediaplayer buttons for media modes to support entity_pictures. [Issue #021](https://github.com/rbisschops/homeassistant/issues/21)

## [0.9.8] - 2020-04-06
### Bug fixes
- Fixed: Reversed some names for media modes to match Harmony names. [Issue #010](https://github.com/rbisschops/homeassistant/issues/10)
- FIxed: Changed selection for light modes. [Issue #016](https://github.com/rbisschops/homeassistant/issues/16)

### Added
- Option to select Uitzending gemist added to media_center.yaml. [Issue #018](https://github.com/rbisschops/homeassistant/issues/18)

## [0.9.7] - 2020-04-05
### Bug fixes
- Fixed: Top floor showing door in loverlace instead of right window. [Issue #015](https://github.com/rbisschops/homeassistant/issues/15)
- Fixed: Hallway light not working anymore. [Issue #011](https://github.com/rbisschops/homeassistant/issues/11)
- Fixed: Livingroom lights not working from lovelace button anymore. [Issue #017](https://github.com/rbisschops/homeassistant/issues/17)
- Fixed: First floor hallway door showing as groundfloor door on floorplan. [Issue #014](https://github.com/rbisschops/homeassistant/issues/14)

## [0.9.6] - 2020-04-04
### Bug fixes
- hue scripts: Fixed bug in script names.

### Changed
- input_boolean: Changed multiple entities names to more logical names.
- timer: Changed entity_id 'timer.zigbee_permit_join' to 'timer.zigbee2mqtt_permit_join' in package_zigbee2mqtt.yaml

## [0.9.5] - 2020-04-03
### Bug fixes
- mediaplayer: Reverted change name webostv to living_room_tv.
- binary_sensor: picture not presented in LovelaceUI for doors/windows. Updated sensor configuration. 

### Changed
- timer: Changed multiple entities names to more logical names.
- input_boolean: Changed name 'input_boolean.hallwaylight' to 'input_boolean.light_hallway' in package_hallway.yaml
- script: Changed multiple entities names to more logical names.

## [0.9.4] - 2020-04-02
### Bug fixes
- automations: bug fixes in referenced automations

### Changed
- automation: changed the humidity automations to not notify when humidity is high or low (commented).
- input_text: Changed multiple entities names to more logical names.
- mediaplayer: Changed name of media_player_living_room_tv.

## [0.9.3] - 2020-04-01
### Changed
- climate: Changed entity name to more logical name.
- input_number: Changed multiple entities names to more logical names.
- input_select: Changed multiple entities names to more logical names.

## [0.9.2] - 2020-03-31
### Changed
- automation: Change automation aliases to english and rationalize (continued). See [Issue #008](https://github.com/rbisschops/homeassistant/issues/8)
- binary_sensor: Changed multiple sensors names to more logical names.

## [0.9.1] - 2020-03-29
### Changed
- entitie: Changed entity names to match with functional use, example: sensor.room_humidity_livingroom > sensor.environment_livingroom_humidity. see [Issue #007](https://github.com/rbisschops/homeassistant/issues/7)
- automation: Change automation aliases to english and rationalize. Example 'Kerstboom aan-uit' to 'Switch christmas tree toggle' in package_livingroom.yaml. See [Issue #008](https://github.com/rbisschops/homeassistant/issues/8)
- Automation: Replaced if-else statements with inline Jinja2 formated statements for 'Switch christmas tree toggle'
- Automation: Replaced if-else statements with inline Jinja2 formated statements for 'Light bar toggle'
- Automation: Replaced if-else statements with inline Jinja2 formated statements for 'Light Porch toggle'
- Automation: Replaced if-else statements with inline Jinja2 formated statements for 'Light hallway toggle'
- Automation: Replaced if-else statements with inline Jinja2 formated statements for 'Light high cabinets toggle'
- Automation: Replaced if-else statements with inline Jinja2 formated statements for 'Light garden toggle'
- Automation: Replaced if-else statements with inline Jinja2 formated statements for 'Switch water ornament toggle'
- Automation: Replaced if-else statements with inline Jinja2 formated statements for 'Light livingroom toggle'

### Removed
- All package files: Removed all unused and obsolte groups as these are no longer required since the old state UI was depricated in HA 0.107. See [Issue #002](https://github.com/rbisschops/homeassistant/issues/2)

## [0.9.0] - 2020-03-26
### Added
- CHANGELOG.md, file containing notable changes in my Homeassistant configuration.

### Removed
- All files: Removed changelogs from individual configuration files.



