# Pi-hole DNS Filtering Setup

## Overview

- **Purpose**: Network-wide ad and tracker blocking using Pi-hole
- **Host System**: Ubuntu VM running on Proxmox
- **Pi-hole Version**: v5.11.1
- **Network Integration**: OPNsense firewall with VLAN segmentation

## Installation Steps

1. **System Update**
   ```bash
   sudo apt update && sudo apt upgrade -y
Pi-hole Installation

bash
Copy
Edit
curl -sSL https://install.pi-hole.net | bash
Static IP Assignment

Configured a static IP for Pi-hole via OPNsense DHCP static mapping

Configuration Details
Upstream DNS Providers: OpenDNS (208.67.222.222, 208.67.220.220)

DNSSEC: Enabled

Query Logging: Enabled (Show Everything)

Blocklists:

StevenBlack Unified Hosts

Firebog Ticked Green Lists

Firewall Rules in OPNsense
Allow Rule
Action: Pass

Interface: LAN or applicable VLAN

Protocol: TCP/UDP

Source: LAN net

Destination: Pi-hole IP

Destination Port: 53

Description: Allow DNS to Pi-hole

Block Rule
Action: Block

Interface: LAN or applicable VLAN

Protocol: TCP/UDP

Source: LAN net

Destination: Any

Destination Port: 53

Description: Block all other DNS

DHCP Configuration
DNS server set to Pi-hole IP in OPNsense DHCP settings for all VLANs

Devices obtain new leases with Pi-hole as their DNS server

Monitoring and Maintenance
Dashboard: http://pi.hole/admin

Update Pi-hole

bash
Copy
Edit
pihole -up
Update OS

bash
Copy
Edit
sudo apt update && sudo apt upgrade -y
Query Log: Regularly review to monitor traffic patterns

Notes
Redundancy: Consider setting up a secondary Pi-hole instance for failover

Unbound Integration: Future enhancement to add a recursive DNS resolver for increased privacy

Grafana Integration: Potential to visualize Pi-hole metrics using Grafana dashboards

vbnet
Copy
Edit


# Pi-hole Secondary DNS Server Setup on Proxmox

## Overview

This guide documents the setup of a second Pi-hole DNS filtering instance hosted on a separate physical machine running Proxmox VE. The second Pi-hole ensures high availability and resilience for DNS filtering and network-wide ad blocking.

---

## Host Setup

- **Hypervisor**: Proxmox VE
- **VM OS**: Ubuntu Server 24.04 LTS
- **VM Resources**:  
  - CPU: 1–2 cores  
  - RAM: 512MB–1GB  
  - Disk: 4GB+  
  - Network: Bridged (VirtIO or Intel E1000)

---

## Step 1: Create the VM in Proxmox

1. Upload the Ubuntu Server ISO to Proxmox.
2. Create a new VM and attach the ISO.
3. Configure:
   - Network: Use a bridged adapter (VLAN-aware if needed).
   - Disk: Use `scsi` or `virtio`.
   - Boot order: Set CD-ROM first, then disk.
4. Start the VM and install Ubuntu Server.

---

## Step 2: Assign a Static IP

You can either:
- Set a static IP in the VM via Netplan:

  ```bash
  sudo nano /etc/netplan/01-netcfg.yaml

