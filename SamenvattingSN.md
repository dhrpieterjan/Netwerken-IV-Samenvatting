# Samenvatting Scaling Networks
## H1: LAN design

> Lezen in de cursus

## H2: Scaling VLANs: VTP, Extended VLANs and DTP

### VTP:

**Vlan trunking protocol** eliminates the need to configure a new VLAN on every switch.
VTP sores VLAN configuration in vlan.dat
VTP V1-2 only learns about normal range vlans (1-5000), V3 support extended VLANs
VTP advertisemenst only in domain (router or l3 switch define the boundary of each domain)

#### VTP modes:

- **Server**
    + Advertises the VTP domain VLAN information to other VTP-enabled switches in the same domain
    + Stores vlan.dat in NVRAM
    + CRUD on VLANs in domain
    + **Default mode**

- **Client**
    + No CRUD on VLANs
    + Stores vlan.dat in RAM
    + Must be confiured as VTP client

- **Transparant**
    + Does not participate in VTP expect forward VTP to other switches (client en server)

#### VTP advertisments:

- **Summary**
    + Informs other switches of domain, sends **configuration revision number**
    + Every 5 min (default)

- **Advertisement request**
    + Respons to a Summary advertisment if the **configuration revision number** is higher than the current one.

#### VTP configuration:

- check version `show vtp status`
- rest check cursus

### DTP

**Dynamic Truncking Protocol** provides the ability for ports to automatically negotiate trunking between switches. 
Turn off DTP on interfaces on a Cisco switch that is connected to devices that do not support DTP to avoid misconfigurations

#### DTP Configuration:

- check cursus

## H3 STP

### STP

**Spannings ree Protocol** provides redundancy as OSI Layer 1 end 2
When multiple paths exist between two devices on a network, and there is no spanning tree implementation on the switches, a Layer 2 loop occurs. 

STP ensures that there is only one logical path between all destinations on the network by intentionally blocking redundant paths that could cause a loop. 

#### STP Port types:

| Port | Defenition |
| ------------- | ------------- |
| **Root** ports | Port closest to the root bridge |
| **Designated** ports | non-root ports permitted to forward trafic |
| **Alternate** and backup port | Blocking state to prevent loops |
| **Disabled** ports | A disabled port is a switch port that is shut down |

#### STP Root Path Cost:

| Link Speed | Cost |
|:-----------|:-----|
| 10 Gb/s    | 2    |
| 1 Gb/s     | 4    |
| 100 Mb/s   | 19   |
| 10 Mb/s    | 100  |

#### STP Confirutation:

-check cursus

## H4: EtherChannel and HSRP


























