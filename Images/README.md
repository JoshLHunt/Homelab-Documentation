### Architecture Overview

The lab environment is designed to simulate a segmented enterprise infrastructure while maintaining safe isolation for security testing.

Traffic flow begins at the ISP edge and passes through a Fortigate firewall before reaching a Cisco Layer 3 switch responsible for VLAN segmentation and inter-VLAN routing.

The Proxmox cluster is connected via VLAN 10 and hosts multiple virtual machines, including:

- Active Directory Domain Controller
- Windows client systems
- Kali Linux attacker workstation
- Additional service VMs

The Active Directory lab environment is further isolated using an internal Proxmox bridge (vmbr1) with no external routing. This allows controlled attack simulation without exposing the lab network to the internet.

Kali Linux is dual-homed to simulate realistic attacker positioning:
- Connected to the internal AD lab bridge for lateral movement testing
- Connected to VLAN 10 for tool updates and internet access

Storage infrastructure is segmented on VLAN 20, separating data access from compute workloads.

Media services are placed on VLAN 30 to prevent unnecessary lateral exposure between entertainment workloads and core lab infrastructure.

This layered segmentation approach enforces:

- Network isolation between functional tiers
- Reduced attack surface
- Controlled routing boundaries
- Realistic enterprise-style architecture for security testing

All IP addressing and sensitive identifiers are sanitized for documentation purposes.
