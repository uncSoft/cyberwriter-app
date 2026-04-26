---
tags: [engineering, architecture, systems]
owner: Marcus Kim
---

# System Architecture

> [!note] Owner
> Maintained by [[Marcus Kim]]. All changes require review.
## Station Systems Overview

```mermaid
---
title: Station Power Diagram
---
flowchart TB
    subgraph Power["Power Systems"]
        Solar[Solar Arrays 28kW] --> PDU[Power Distribution]
        PDU --> Battery[Battery Bank\n48V Li-Ion]
        PDU --> Bus[Main Power Bus]
    end

    subgraph Life["Life Support"]
        O2[O2 Generation Electrolysis] --> Atmo[Atmosphere Control]
        CO2A[CO2 Scrubber Primary] --> Atmo
        CO2B[CO2 Scrubber Backup ⚠️] --> Atmo
        Water[Water Recycling] --> O2
    end

    subgraph Comms["Communications"]
        Sband[SBand Telemetry] --> Ground[Ground Station]
       Kaband[Ka-Band High Data] --> Ground
        UHF[UHF EVA Comms] --> Crew[Crew Radios]
    end

    Bus --> Life
    Bus --> Comms

    style Solar fill:#ffe599,stroke:#e6b800,color:#000
    style PDU fill:#a9c7ff,stroke:#7aa3e5,color:#000
    style Battery fill:#a9c7ff,stroke:#7aa3e5,color:#000
    style Bus fill:#ff9f40,stroke:#cc7a00,color:#000

    style O2 fill:#b6e8b6,stroke:#4caf50,color:#000
    style Atmo fill:#b6e8b6,stroke:#4caf50,color:#000
    style CO2A fill:#ffd6a5,stroke:#e8914a,color:#000
    style CO2B fill:#ffb3b3,stroke:#e05555,color:#000
    style Water fill:#b6e8b6,stroke:#4caf50,color:#000

    style Sband fill:#d9b3ff,stroke:#a855f7,color:#000
    style Kaband fill:#d9b3ff,stroke:#a855f7,color:#000
    style UHF fill:#d9b3ff,stroke:#a855f7,color:#000
    style Ground fill:#f0c4f0,stroke:#c084fc,color:#000
    style Crew fill:#f0c4f0,stroke:#c084fc,color:#000
``` 

## Data Flow: Telemetry Pipeline

```mermaid
---
config:
    theme: 'dark'
---
sequenceDiagram
    participant S as Sensors
    participant OBC as Onboard Computer
    participant TX as S-Band Transmitter
    participant GS as Ground Station
    participant MC as Mission Control

    S->>OBC: Raw sensor data (100Hz)
    OBC->>OBC: Filter & compress
    OBC->>TX: Telemetry packets (1Hz)
    TX->>GS: Downlink (2 Mbps)
    GS->>MC: TCP/IP relay
    MC->>MC: Display & alert
    MC-->>GS: Command uplink
    GS-->>TX: S-Band uplink
    TX-->>OBC: Execute command
    OBC-->>S: Actuator control
```

## Module Layout

```mermaid
---
config: 
    theme: 'neutral'
---
flowchart LR
    Dock[Docking Port] --- Node[Node Module]
    Node --- Hab[Habitat Module]
    Node --- Lab[Science Lab]
    Node --- Power[Power Truss]
    Hab --- LSS[Life Support System]
    Lab --- Airlock[EVA\ Airlock]
    style Node fill:#a9c7ff,stroke:#7aa3e5,color:#000
    style Hab fill:#a9c7ff,stroke:#7aa3e5,color:#000
    style Lab fill:#ffaaf7,stroke:#d88fd0,color:#000
    style Power fill:#ffd93d,stroke:#f0c000,color:#000
    style Dock fill:#6bcb77,stroke:#4caf50,color:#000
    style Airlock fill:#ff67ff,stroke:#7aa3e5,color:#000
    style LSS fill:#00e9d6,stroke:#f0c000,color:#000

```

## Power Budget

| System | Power Draw | Priority |
|--------|-----------|----------|
| Life Support | 8.2 kW | 🔴 Critical |
| Thermal Control | 4.1 kW | 🔴 Critical |
| Communications | 2.3 kW | 🟡 High |
| Science Payloads | 5.8 kW | 🟢 Normal |
| Crew Systems | 3.4 kW | 🟢 Normal |
| GN&C | 1.8 kW | 🔴 Critical |
| **Total** | **25.6 kW** | - |
| **Available (Solar)** | **28.0 kW** | - |
| **Margin** | **2.4 kW (8.6%)** | ⚠️ |

> [!warning] Power Margin
> 8.6% margin is below our 15% target. Options under review:
> 1. Add two more solar panels (+4 kW, +180 kg) - impacts [[Orbital Mechanics]]
> 2. Reduce science payload priority to load-shed during eclipse
> 3. Upgrade to higher-efficiency GaAs cells (+$2.1M) - impacts [[Mission Briefing|budget]]

## Related

- [[Mission Briefing]] - timeline and budget
- [[Marcus Kim]] - system owner
- [[Habitat Design]] - interior integration points
- [[Orbital Mechanics]] - mass budget constraints

#engineering #architecture #power #systems

