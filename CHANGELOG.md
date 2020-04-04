# Changelog

As of 2020-03-25 All notable changes to my Homeassistant configuration will be documented in this file.

## [0.9.5] - 2020-04-03
### Bug fixes
- mediaplayer: Reverted change name webostv to living_room_tv.
- binary_sensor: picture not presented in LovelaceUI for doors/windows. Updated sensor configuration. 


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



