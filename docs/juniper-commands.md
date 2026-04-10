# Juniper Commands by Plane

## Routing Engine (RE) - Control Plane

| Command | Purpose |
|---------|---------|
| `show route` | View routing table |
| `show route protocol ospf` | OSPF-specific routes |
| `show system processes` | See all Junos daemons |
| `show system processes extensive` | CPU/memory per process |
| `show log messages` | RE system logs |
| `show log messages | match "BGP"` | Filter logs |
| `show configuration` | Current config (management plane) |
| `request system reboot` | Reboot RE |

## Packet Forwarding Engine (PFE) - Data Plane

| Command | Purpose |
|---------|---------|
| `show pfe statistics traffic` | Forwarding stats |
| `show interfaces diagnostics optics ge-0/0/0` | Optical transceiver info |
| `monitor interface traffic` | Real-time data plane view |
| `show interfaces queue ge-0/0/0` | Queue statistics |
| `show chassis fpc` | PFE status and communication |
| `test interface ge-0/0/0` | Loopback test data path |

## Services Plane

| Command | Purpose |
|---------|---------|
| `show services accounting` | Services module stats |
| `show security flow statistics` | Firewall (on SRX) |
| `show security ipsec statistics` | VPN tunnel stats |
| `show services load-balancing statistics` | LB stats |

## RE-PFE Communication Debug

| Command | Purpose |
|---------|---------|
| `show chassis fpc pic-status` | Check PFE communication |
| `show log kmd` | Kernel module debug |
| `request support information` | Collect all plane info |
