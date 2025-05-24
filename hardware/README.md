# Takt Cluster

## Status

Planning phase - hardware selection and procurement underway

## Hardware Overview

### General Hardware

| Component | Specification | Purpose |
|-----------|---------------|---------|
| Tecmojo 16U Open Frame Rack | 16U, 512mm depth | Rack for compute nodes, storage, and networking equipment |
| 10Gbps Cat6a Cables | 0.3, 0.9, 1.5m | High-speed interconnect between nodes and storage |
| Rackstuds | Red 2.2mm/0.086" | Rack mounting hardware for securing equipment |
| 24 Port 1U Patch Panel | 10GbE, Cat6a | Organized cabling for easy management |
| 6 Way Switched PDU | 230V | Power distribution for rack equipment |

### Network Hardware

| Component | Specification | Purpose |
|-----------|---------------|---------|
| Juniper EX2200-C | 12x 1GbE + 2x SFP+ 10GbE | Main cluster switch for compute nodes |
| Juniper SRX 300 (x2) | Enterprise firewall/router | Clustered for HA internet gateway and VPN |
| NETGEAR GS724T | 24-port managed switch | Expansion or management network |
| NETGEAR GS308E | 8-port managed switch | Lab bench or isolated testing |

### Compute Hardware

| Component | Specification | Purpose |
|-----------|---------------|---------|
| [TBD] | Login/head node | SSH gateway and job management |
| [TBD] | GPU compute nodes | ML training and inference workloads |
| [TBD] | Storage server | Shared datasets and user storage |

### Waiting on Delivery

| Component | Expected | Status |
|-----------|----------|--------|
| [Items being shipped] | [Date] | [Tracking/notes] |

### Planned Hardware

| Component | Specification | Priority | Estimated Cost |
|-----------|---------------|----------|----------------|
| [Additional planned items] | [Specs] | [Priority] | [Cost] |
