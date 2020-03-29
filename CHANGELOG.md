# Changelog

As of 2020-03-25 All notable changes to my Homeassistant configuration will be documented in this file.

## [0.9.1] - 2020-03-29
### Added

### Changed
- Entities: Changed entity names to match with functional use, example: sensor.room_humidity_livingroom > sensor.environment_livingroom_humidity. see [Issue #007](https://github.com/rbisschops/homeassistant/issues/7)
- Automations: Change automation aliases to english and rationalize. Example 'Kerstboom aan-uit' to 'Switch christmas tree toggle' in package_livingroom.yaml. See [Issue #008](https://github.com/rbisschops/homeassistant/issues/8)
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

### Changed


### Removed
- All files: Removed changelogs from individual configuration files.



