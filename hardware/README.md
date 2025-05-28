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
| UniFi Dream Router 7 (UDR7-UK) | 1x 2.5GbE WAN, 3x 2.5GbE LAN, 1x 10G SFP+, WiFi 7 | Gateway/router |
| UniFi 10G PoE++ Injector (UACC-PoE++-10G-EU) | 60W, 10GbE | Power and data for access points |
| UniFi Switch Aggregation (USW-Aggregation-UK) | 8x 10G SFP+ | Core aggregation switch |
| UniFi Switch Pro Max 24 (USW-Pro-Max-24-EU) | 16x 1GbE, 8x 2.5GbE, 2x 10G SFP+ | Main access switch |
| UniFi Access Point U7 Pro XG (x2) | WiFi 7, 10GbE uplink | Wireless bridge infrastructure |
| UniFi SFP+ to RJ45 Module (UACC-CM-RJ45-MG) | 10G copper transceiver | Media conversion |
| UniFi SFP+ DAC Cable (UACC-DAC-SFP10-0.5M) | 0.5m direct attach | Switch interconnect |

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

## Network Topology

### Architecture Overview

```plaintext
                            Internet (1.8 Gbps)
                                   ↓
                            UniFi Dream Router 7
                                   ↓
                          UniFi 10G PoE++ Switch
                                   ↓
                            UniFi Access Point U7 Pro XG (x2)
                                   ↓
                            UniFi Switch Aggregation
                                   ↓ (20G LAG)
                            UniFi Switch Pro Max 24
                                   ↓
                            Compute Nodes / Storage Server
```

### Performance Characteristics

- **Internet throughput**: 1.8 Gbps WAN, 2.5 Gbps LAN distribution
- **Intra-segment LAN**: Full 10G within switch domains
- **Cross-segment LAN**: ~2-3 Gbps via wireless bridge
- **Core backbone**: 20G aggregate between core switches

## Procurement Pipeline

### Currently Ordered

| Component | Estimated Cost | Status |
|-----------|---------------|----------------|--------|
| UniFi Dream Router 7 (UDR7-UK) | £220 | Ordered |
| UniFi 10G PoE++ Adapter (60W) (UACC-PoE++-10G-EU) | £62 | Ordered |
| UniFi Switch Aggregation (USW-Aggregation-UK) | £215 | Ordered |
| UniFi Switch Pro Max 24 (USW-Pro-Max-24-EU) | £345.00 | Ordered |
| UniFi Access Point U7 Pro XG (x2) | £318.00 | Ordered |
| UniFi SFP+ to RJ45 Module (UACC-CM-RJ45-MG) | £50 | Ordered |
| UniFi SFP+ DAC Cable (UACC-DAC-SFP10-0.5M) (x2) | £20 | Ordered |
| VAT | 20% | £248.00 | - |
| Shipping | £10.00 | - |
| **Total** | **£1,488.00+** | - |

## Hardware Standards

### Form Factors

- **Compute nodes**: 1U+ rackmount or compatible chassis
- **Storage**: 2U for drive density and cooling
- **Networking**: Standard 1U enterprise equipment

### Connectivity

- **Primary network**: 10GbE backbone with 10GbE/2.5GbE access
- **Storage uplink**: 10GbE via SFP+ for high throughput
- **Management**: Dedicated network for IPMI/BMC access
- **Internet connectivity**: 2.5GbE distribution via wireless bridge

### Power Requirements

- **Current draw**: ~?kW estimated for full configuration
- **Redundancy**: Single PDU sufficient for current scale
- **Monitoring**: Individual outlet switching capability
