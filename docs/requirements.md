# Requirements

## Functional

- **F1:** Read selected Homematic CCU3 datapoints and show their values and states on the NSPanel.
- **F2:** Deliver NSPanel physical-button and touchscreen events to the CCU3 as Homematic-compatible sensor inputs, usable in CCU programs.
- **F3:** Expose both NSPanel relays as CCU3-controllable actors, including actual state feedback.
- **F4:** Allow mappings of CCU datapoints and NSPanel controls to be configured without modifying core integration code where feasible.
- **F5:** Restore or reconcile state after device, network, or CCU3 restart; avoid duplicate or unsafe commands.

## Nonfunctional

- **N1 (must):** Local functionality without vendor cloud services.
- **N2 (must):** OTA delivery of application-function changes after initial installation, with a documented recovery path.
- **N3 (must):** No hard-coded credentials; authenticated access and minimal exposure of control interfaces.
- **N4 (must):** Reproducible sources and development/deployment documentation.
- **N5 (should):** Avoid requiring an additional always-on server; prefer a CCU3 add-on where feasible.
- **N6 (should):** Permit application configuration and UI updates without full ESP32 reflashing when practical.
- **N7 (should):** Provide diagnostics/logs for connection, events, and state changes.

## Technology preferences, not requirements

- Tasmota + Berry is preferred for the NSPanel; evaluate ESPHome and alternatives.
- Prefer a native-feeling CCU3 virtual device integration rather than one-off program triggers.
- Protocol and software language are open design decisions.

## Acceptance scenarios

1. Change a selected CCU3 datapoint and observe the updated value on the NSPanel.
2. Press a physical NSPanel button and observe a corresponding event in CCU3 programs.
3. Trigger a touchscreen control and observe the mapped CCU3 event.
4. Switch each relay from the CCU3 and verify the actual relay state is reflected back.
5. Disconnect and reconnect Wi-Fi and the CCU3, verifying that the integration recovers predictably.
6. Deploy a functional change OTA without physical access to the panel.

## Safety

The NSPanel contains mains-voltage circuitry. Disconnect from mains before opening or attaching a serial adapter; use a proper 3.3 V serial interface. Initial experiments should use a safe test setup and not control critical loads.
