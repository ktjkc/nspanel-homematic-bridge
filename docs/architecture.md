# Architecture exploration (open)

No architecture has been selected. The initial AI-assisted task is to research and document alternatives rather than commit prematurely.

## Candidate topology

```text
Sonoff NSPanel-US                 Integration layer                Homematic CCU3
ESP32 + display controller <--> protocol/device mapping <--> CCU datapoints/programs
buttons / touch / relays          location TBD                    virtual inputs / actors
```

## Questions to answer

1. Tasmota + Berry vs ESPHome: NSPanel-US hardware support, UI flexibility, firmware OTA, application logic updates, debugging and maintainability?
2. How is the NSPanel's display controller programmed, and how can its UI be updated remotely?
3. Which CCU3 interfaces can expose virtual devices and channels (rather than only invoking programs)? What add-on mechanism is feasible?
4. Should transport be MQTT, HTTP, XML-RPC, another local protocol, or a combination?
5. Can the bridge run reliably as a CCU3 add-on? What are the operational and packaging constraints?
6. How will device discovery, configuration, state reconciliation, event deduplication, authentication and update rollback work?
7. What is the smallest hardware-backed end-to-end proof of concept?

## Decision record template

For each major decision, record: context, options, evidence, trade-offs, decision, consequences, and unresolved questions. Avoid assuming that firmware or a CCU interface supports a feature until validated.
