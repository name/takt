# Takt Cluster

## Status

Planning phase - hardware selection and procurement underway

## Hardware Overview

### Rack & Power

| Component | Specification | Purpose |
|-----------|---------------|---------|
| Tecmojo 16U Open Frame Rack | 16U, 512mm depth | Physical infrastructure |
| 6-Way Switched PDU | 230V, side-mounted | Power distribution |
| Rackstuds | Red 2.2mm/0.086" | Rack mounting hardware |

### Cabling & Connectivity

| Component | Specification | Purpose |
|-----------|---------------|---------|
| 24 Port 1U Patch Panel | 10GbE, Cat6a | Cable management |
| 10Gbps Cat6a Cables | 0.3m, 0.9m, 1.5m | High-speed interconnect |

### Network Hardware

| Component | Specification | Purpose |
|-----------|---------------|---------|
| Juniper EX2200-C | 12x 1GbE + 2x SFP+ 10GbE | Main cluster switch for compute nodes |
| Juniper SRX 300 (x2) | Enterprise firewall/router | Clustered for HA internet gateway and VPN |
| NETGEAR GS724T | 24-port managed switch | Expansion or management network |
| NETGEAR GS308E | 8-port managed switch | Lab bench or isolated testing |

### Compute Hardware

| Component | Target Spec | Purpose |
|-----------|-------------|---------|
| Login/Head Node | Mini-PC/NUC, 8GB+ RAM | SSH gateway, job management |

### Compute Tier

| Component | Target Spec | Purpose |
|-----------|-------------|---------|
| GPU Node | TBD | ML training and inference |

### Storage Tier

| Component | Target Spec | Purpose |
|-----------|-------------|---------|
| Storage Server | High-capacity drives, 10GbE NIC | Shared datasets and user storage |

## Procurement Pipeline

### Waiting on Delivery

| Component | Expected | Status |
|-----------|----------|--------|
| [Items being shipped] | [Date] | [Tracking/notes] |

### Planned Hardware

| Component | Specification | Priority | Estimated Cost |
|-----------|---------------|----------|----------------|
| [Additional planned items] | [Specs] | [Priority] | [Cost] |

## Hardware Standards

### Form Factors

- **Compute nodes**: 1/2U rackmount or compatible chassis
- **Storage**: 2U for drive density and cooling
- **Networking**: Standard 1U enterprise equipment

### Connectivity

- **Primary network**: 1GbE for all compute nodes
- **Storage uplink**: 10GbE via SFP+ for high throughput
- **Management**: Dedicated network for IPMI/BMC access

### Power Requirements

- **Current draw**: ~?kW estimated for full configuration
- **Redundancy**: Single PDU sufficient for current scale
- **Monitoring**: Individual outlet switching capability
