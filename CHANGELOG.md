# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog],
and this project adheres to [Semantic Versioning].

## [0.1.0] - 2023-04-22

- Initial release


## [0.1.1] - 2023-04-26

### Added

- Added new product_id for Fingerbot Plus (#1)

### Fixed

- Fixed problem in options flow.

### Changed

- Updated strings.json


## [0.1.2] - 2023-04-26

### Changed

- Changed a way to obtain device credentials from Tuya IOT cloud, possible fix to (#2)

## [0.1.4] - 2023-04-30

### Added

- Added support of CUBETOUCH 1s, thanks @damiano75
- Added new product_ids for Fingerbot.
- Added new product_ids for Fingerbot Plus.
- First attempt to support Smart Lock device.

### Fixed

- Fixed possible disconnect of BLE device.

## [0.1.5] - 2023-06-01

### Added

- Added new product_ids for Fingerbot.
- Added event "fingerbot_button_pressed" which is fired on Fingerbot Plus touch button press.
- First attempt to add support of climate entity.

## [0.1.6] - 2023-06-01

### Added

- Added new product_ids for Fingerbot and Fingerbot Plus.

### Changed

- Updated sources to conform Python 3.11

## [0.1.7] - 2023-06-01

### Added

- Added new product_ids.
- Added full support of BLE TRV provided by @forabi
- Added support of programming mode for Fingerbot Plus, thanks @redphx for information.

### Changed

- Improved connection stability.

## [0.1.9] - 2026-07-08

### Added

- Expanded Smart Lock (category `ms`, product `kgsovyg1`) support: battery
  state, lock alarm and door-contact sensors, plus auto-lock enable switch and
  auto-lock time control.

### Fixed

- Restored compatibility with current Home Assistant releases (2025.x / 2026.x):
  - Decoupled from the rewritten core Tuya integration. The Tuya IoT login
    constants and country list (`TUYA_COUNTRIES`) are now bundled locally
    instead of being imported from `homeassistant.components.tuya.const`,
    which no longer exposes them after the QR-code login rewrite.
  - Replaced removed constants `TEMP_CELSIUS`, `TIME_MINUTES`, `TIME_SECONDS`
    and `VOLUME_MILLILITERS` with the `UnitOf*` enums.
  - Replaced the removed `homeassistant.backports.enum` import.
  - Migrated the options flow from the deprecated `OptionsFlowWithConfigEntry`
    to `OptionsFlow` (explicitly setting `config_entry` is removed in HA 2025.12).
  - Passed `config_entry` to the `DataUpdateCoordinator`.
  - Replaced the deprecated `hass.add_job(coroutine)` with
    `ConfigEntry.async_create_background_task`.

### Changed

- `tuya` moved from `dependencies` to `after_dependencies` in the manifest, so
  the core Tuya integration is no longer required to be set up.


## [0.1.8] - 2023-07-09

### Added

- Added support of 'Irrigation computer', thanks to @SanMiggel.
- Added new product_ids for Smart locks, thanks to @drewpo28.

### Changed

- Connection to the device is postponed now. Previously some out of range device might prevents HA from fully booting.
- Improved connection stability.
