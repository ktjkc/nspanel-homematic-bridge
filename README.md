# NSPanel–Homematic Bridge

A personal, early-stage project to integrate a **Sonoff NSPanel-US (2022, currently stock firmware)** with a **Homematic CCU3** as a bidirectional, local home-automation device.

**Status:** Requirements and architecture exploration. No functional integration has been implemented yet.

## Goals

1. Show selected CCU3 device states and values on the NSPanel.
2. Expose physical buttons and touchscreen interactions as Homematic-compatible sensor events, ideally usable in CCU3 programs like native device inputs.
3. Expose the NSPanel's two relays as controllable Homematic actors with state feedback.

## Constraints and preferences

- **Required:** local operation without cloud dependence; OTA updates after initial provisioning; reconnection and state synchronization; reproducible development.
- **Preferred, not mandated:** Tasmota + Berry for the panel; a CCU3 add-on rather than an always-on external host.
- **To investigate:** firmware options, the NSPanel display controller and UI update mechanism, CCU3 virtual device integration, transport, security, and OTA recovery.

See [requirements](docs/requirements.md), [roadmap](docs/roadmap.md), and [architecture questions](docs/architecture.md).

## First task for an AI coding assistant

Review the requirements and propose at least two viable architectures. Evaluate Tasmota/Berry versus ESPHome, identify a practical CCU3 device-integration mechanism, and propose an incremental proof of concept. Document alternatives, assumptions, hardware risks, and trade-offs. **Do not implement or flash hardware until the proposal is reviewed.**

## Hardware

- Sonoff NSPanel-US, purchased in 2022, original firmware (exact version to record)
- Homematic CCU3 (firmware version to record)

## Development status

This repository currently contains documentation only. The build system, languages, deployment method, and test framework will be selected after the architecture review.

## Contributing and code rights

This is a personal project. Contributions are welcome after the initial architecture is agreed. Original code added to this repository is intended to be MIT-licensed; third-party code and firmware remain under their respective licenses. Never commit CCU credentials, Wi-Fi secrets, private keys, or local configuration containing secrets.
