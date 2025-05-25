# Rack Configuration

## Current Setup

![Current Rack Configuration](../../docs/images/rack-current.jpg)

*Tecmojo 16U rack with networking equipment installed*

## Current Layout (14U Available)

| U Position | Equipment | Status |
|------------|-----------|--------|
| **U1** | Patch Panel (24-port) | Installed - Cable management at top |
| **U2** | Juniper EX2200-C | Installed - Current cluster switch |
| **U3** | Juniper SRX300 #1 | Installed - Primary firewall |
| **U4** | Juniper SRX300 #2 | Installed - Secondary firewall |
| **U5** | NETGEAR GS724T | Installed - Management network |
| **U6** | Empty | Available for expansion |
| **U7** | Empty | Available for expansion |
| **U8** | Empty | Available for expansion |
| **U9** | 1U Shelf | Installed - Small equipment/tools |
| **U10** | 1U Cover | Clean appearance |
| **U11** | 1U Cover | Clean appearance |
| **U12** | 1U Cover | Clean appearance |
| **U13** | 1U Cover | Clean appearance |
| **U14** | 1U Cover | Clean appearance |

**Back Mount U8:** 6-Way Switched PDU

## Target Configuration

### After Network Upgrade (When UniFi Equipment Arrives)

| U Position | Equipment | Purpose |
|------------|-----------|---------|
| **U1** | Patch Panel (24-port) | Cable management at top |
| **U2** | Switch Pro Max 24 | Main cluster switch (2.5GbE/10GbE) |
| **U3** | 1U Shelf | Login/head node |
| **U4** | Empty | Available for compute |
| **U5** | Empty | Available for compute |
| **U6** | Empty | Available for compute |
| **U7** | Empty | Available for compute |
| **U8** | Empty | Available for compute |
| **U9** | Empty | Available for compute |
| **U10** | 1U Cover | Available for compute |
| **U11** | 1U Cover | Available for compute |
| **U12** | 1U Cover | Available for compute |
| **U13** | 1U Cover | Reserved for storage |
| **U14** | 1U Cover | Reserved for storage |

**Back Mount U8:** 6-Way Switched PDU  
**Off-rack:** U7 Pro XG units (WiFi bridge infrastructure)

### Logical Zones (Post-Upgrade)

| Zone | U Positions | Purpose | Equipment |
|------|-------------|---------|-----------|
| **Network & Management** | U1-U3 | Core services | Patch panel, Switch Pro Max 24, login node |
| **Compute** | U4-U12 | GPU nodes | TBD compute nodes (9U available) |
| **Storage** | U13-U14 | Storage server | TBD storage server (2U reserved) |

## Planned Changes

### Network Infrastructure Upgrade

**Replace Juniper EX2200-C (U2) with Switch Pro Max 24** to provide 2.5GbE connectivity for compute nodes and 10GbE storage uplink. The new switch will support the WiFi bridge architecture with higher bandwidth capabilities.

**Transition away from Juniper SRX firewalls (U3-U4)** as they cannot handle 2.5 Gbps throughput. Network security will be handled by the GT-AX6000 router and VLAN segmentation on the Switch Pro Max 24.

### Equipment Positioning

**Move shelf from U9 to U6** to create a dedicated management zone directly below networking equipment. This positions the login node for easy access while maintaining logical network adjacency.

**Reserve bottom positions (U13-U14) for storage** to place heaviest equipment at the lowest point for rack stability and optimal cooling for storage drives.

## Design Principles

- **Weight distribution**: Heavy equipment at bottom for stability
- **Thermal management**: Heat-generating components positioned for optimal airflow
- **Logical grouping**: Related equipment clustered for easier management
- **Future expansion**: Scalable design with room for growth
- **Cable management**: Organized routing through patch panel at top
- **Network performance**: 2.5GbE/10GbE infrastructure for high-bandwidth workloads

## Expansion Capabilities

The Tecmojo 16U rack is stackable, allowing for vertical expansion when additional compute or storage capacity is needed.
