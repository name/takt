# Hardware Overview

## Status

Planning phase - hardware selection and procurement underway

## Infrastructure Hardware

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

## Network Hardware

### Current Equipment (Transitioning)

| Component | Specification | Purpose |
|-----------|---------------|---------|
| Juniper EX2200-C | 12x 1GbE + 2x SFP+ 10GbE | Current cluster switch |
| Juniper SRX 300 (x2) | Enterprise firewall/router | Current HA gateway |
| NETGEAR GS724T | 24-port managed switch | Management network |
| NETGEAR GS308E | 8-port managed switch | Lab/testing |

### New Network Infrastructure (Ordered)

| Component | Specification | Purpose |
|-----------|---------------|---------|
| Switch Pro Max 24 | 8x 2.5GbE + 16x 1GbE + 2x 10G SFP+ | Main cluster switch |
| U7 Pro XG (x2) | WiFi 7, 10GbE uplink | WiFi bridge infrastructure |
| UniFi 10G PoE++ Adapter (x2) | 60W power delivery | Power for U7 Pro XG units |

## Compute Hardware

### Management Tier

| Component | Target Spec | Purpose |
|-----------|-------------|---------|
| Login/Head Node | TBD | SSH gateway, job management |

### Compute Tier

| Component | Target Spec | Purpose |
|-----------|-------------|---------|
| GPU Nodes | TBD | ML training and inference |

### Storage Tier

| Component | Target Spec | Purpose |
|-----------|-------------|---------|
| Storage Server | High-capacity drives, 10GbE NIC | Shared datasets and user storage |

## Procurement Pipeline

### Currently Ordered

| Component | Specification | Estimated Cost | Status |
|-----------|---------------|----------------|--------|
| Switch Pro Max 24 | 8x 2.5GbE + 16x 1GbE + 2x 10G SFP+ | £345.00 | Ordered |
| U7 Pro XG (x2) | WiFi 7 access points | £318.00 | Ordered |
| UniFi 10G PoE++ Adapter (x2) | 60W power delivery | £62.00 | Ordered |
| VAT | 20% | £145.60 | - |
| **Total** | - | **£870.60** | - |

## Hardware Standards

### Form Factors

- **Compute nodes**: 1U+ rackmount or compatible chassis
- **Storage**: 2U for drive density and cooling
- **Networking**: Standard 1U enterprise equipment

### Connectivity

- **Primary network**: 2.5GbE for GPU nodes, 1GbE for other equipment
- **Storage uplink**: 10GbE via SFP+ for high throughput
- **Management**: Dedicated network for IPMI/BMC access
- **Internet connectivity**: 2.5GbE via WiFi bridge

### Power Requirements

- **Current draw**: ~?kW estimated for full configuration
- **Redundancy**: Single PDU sufficient for current scale
- **Monitoring**: Individual outlet switching capability
