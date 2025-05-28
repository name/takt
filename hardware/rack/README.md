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
| **U2** | UniFi Switch Aggregation | Core 10G SFP+ switching |
| **U3** | UniFi Switch Pro Max 24 | Main access switch (1GbE/2.5GbE/10GbE) |
| **U4** | 1U Shelf | Login/head node |
| **U5** | Empty | Available for compute |
| **U6** | Empty | Available for compute |
| **U7** | Empty | Available for compute |
| **U8** | Empty | Available for compute |
| **U9** | Empty | Available for compute |
| **U10** | Empty | Available for compute |
| **U11** | 1U Cover | Available for compute |
| **U12** | 1U Cover | Available for compute |
| **U13** | 1U Cover | Reserved for storage |
| **U14** | 1U Cover | Reserved for storage |

**Back Mount U8:** 6-Way Switched PDU  
**Off-rack Equipment:**

- UniFi Dream Router 7 (desktop placement)
- UniFi 10G PoE++ Injector (desktop/wall mount)
- UniFi U7 Pro XG access points (x2) (ceiling/wall mount)

### Network Architecture Integration

**Core Switching Tier (U2):** UniFi Switch Aggregation provides 8x 10G SFP+ ports for high-speed interconnects and storage uplinks

**Access Switching Tier (U3):** UniFi Switch Pro Max 24 delivers 16x 1GbE + 8x 2.5GbE for compute nodes, with 2x 10G SFP+ uplinks to core

**Off-Rack Integration:** Wireless bridge infrastructure (U7 Pro XG units) connects rack to internet via UniFi Dream Router 7, eliminating need for dedicated WAN equipment in rack

### Logical Zones (Post-Upgrade)

| Zone | U Positions | Purpose | Equipment |
|------|-------------|---------|-----------|
| **Core Network** | U1-U3 | Switching fabric | Patch panel, core switch, access switch |
| **Management** | U4 | Control services | Login node, management server |
| **Compute** | U5-U12 | GPU nodes | TBD compute nodes (8U available) |
| **Storage** | U13-U14 | Storage server | TBD storage server (2U reserved) |

## Planned Changes

### Network Infrastructure Upgrade

**Replace legacy Juniper equipment (U2-U4)** with modern UniFi switching infrastructure:

- **Core tier:** UniFi Switch Aggregation for 10G backbone
- **Access tier:** UniFi Switch Pro Max 24 for compute connectivity
- **Gateway tier:** Off-rack UniFi Dream Router 7 with wireless bridge

**Performance improvements:**

- **Compute connectivity:** Upgrade from 1GbE to 2.5GbE per node
- **Storage uplink:** Dedicated 10G SFP+ connection for high-throughput storage
- **Inter-switch:** 20G LAG between core and access switches
- **Internet:** 1.8 Gbps via wireless bridge (2.5 Gbps distribution capacity)

### Equipment Positioning Strategy

**Two-tier switching design** maximizes port density while maintaining 10G backbone performance for storage and inter-switch communication.

**Off-rack wireless infrastructure** eliminates cable runs while providing sufficient bandwidth for internet connectivity and cross-segment communication.

**Compute zone expansion** from 7U to 8U available space by consolidating network equipment and removing redundant firewalls.

## Design Principles

- **Hierarchical switching:** Core/access design for scalable 10G performance
- **Weight distribution:** Heavy equipment at bottom for stability
- **Thermal optimization:** Heat-generating components positioned for airflow
- **Logical adjacency:** Related equipment grouped for management efficiency
- **Future expansion:** Scalable design with room for growth
- **Cable management:** Organized routing through patch panel
- **Wireless integration:** Bridge architecture eliminates cable constraints

## Expansion Capabilities

**Current rack capacity:** 8U compute + 2U storage + 3U infrastructure + 1U management

**Vertical expansion:** Tecmojo racks are stackable for additional capacity when needed

**Network scalability:** UniFi Switch Aggregation provides 5 additional 10G SFP+ ports for future high-speed devices or inter-rack connectivity
