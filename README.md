# Home Network Lab Documentation

Welcome to my personal network lab project! This repository documents the design, configuration, and ongoing development of my home network and lab environment. The goal is to improve my skills in network engineering, firewall management, VLAN segmentation, VPN configuration, and infrastructure documentation — while building a secure, segmented, and scalable network at home.

---

## Table of Contents  

- [Overview](#overview)  
- [Lab Hardware](#lab-hardware)  
- [Network Topology](#network-topology)  
- [Services & Tools](#services--tools)  
- [VLAN Design](#vlan-design)  
- [VPN Configuration](#vpn-configuration)  
- [DNS & Security](#dns--security)  
- [Backup & Monitoring](#backup--monitoring)
- [WebTrees - Family Geneology - Self Hosted](#Webtrees-Self-Hosted-Genealogy-Platform)
- [Future Plans](#future-plans)

---

## Overview  

This lab uses **OPNsense** as the core firewall/router with VLAN segmentation, **Pi-hole** for ad-blocking and DNS filtering, **OpenDNS** for DNS security, and various hardware components like managed switches and wireless access points.  

The lab is designed to simulate small-to-mid-sized network environments while providing a secure and scalable infrastructure for real-world use and future experimentation.

---

## Lab Hardware  

| Device                  | Purpose                       |
|:------------------------|:------------------------------|
| Custom OPNsense Firewall | Router/Firewall/VLAN Manager   |
| TP-Link Smart Switch     | VLAN segmentation, Trunk ports |
| Synology RT6600ax        | Wireless Access Point          |
| Ubuntu Server VM         | Jellyfin, Pi-hole, WireGuard    |
| Various Client Devices   | Test devices (phones, laptops) |

---

## Network Topology  

[Network Diagram](./diagrams/LabSetupDiagram.png)


---
# UniFi Controller Setup & VLAN-Tagged SSIDs

## Date
2025-07-23

## Objective
Set up a UniFi controller in Proxmox to manage a UniFi AP, adopt it into the network, and prepare to segment wireless traffic using VLANs per SSID.

---

## Steps Completed

### 🛠️ 1. Deploy UniFi Controller in Proxmox
- Created a new LXC container in Proxmox.
- Set `features: nesting=1` and enabled `usePAM: yes` for full functionality.
- Installed UniFi Network Application using [LinuxServer.io Docker container](https://docs.linuxserver.io/images/docker-unifi-controller).
- Mapped required ports (e.g., 8443 for GUI).
- Ensured container had static IP and proper DNS resolution.

### 🔐 2. Access Controller GUI
- Accessed the UniFi controller via: `https://<container-IP>:8443`
- Logged in and completed initial setup wizard.

### 📡 3. Adopt UniFi Access Point (AP)
- AP discovered via Layer 2.
- Adopted AP through controller dashboard.
- Waited for it to fully provision and update firmware (if needed).
- Confirmed successful connection to controller.

### 🚚 4. Move AP to Final Location
- Physically unplugged the AP and moved it to desired location.
- Plugged into a trunk port allowing all necessary VLANs.

### 🌐 5. Configure VLANs for SSIDs
- Navigated to **Settings > Networks**
- Selected **"Add New Virtual Network"**
- Created VLAN-only networks for each desired segment:
  - Example: `IoT VLAN` (VLAN ID: 20)
  - Example: `Guest VLAN` (VLAN ID: 30)
- Saved each virtual network without DHCP or routing (handled by external router).

---

## Next Steps
- Assign VLANs to specific SSIDs via **Settings > WiFi > SSID > Advanced > Use VLAN**
- Confirm switch ports and upstream router (e.g., OPNsense) are correctly tagging and handling VLANs
- Apply firewall rules as needed in router to isolate VLANs

---

## Notes
- Ensure controller container’s time, DNS, and internet connectivity are solid
- Future plan: integrate controller with Home Assistant and Zabbix for visibility



---

## Services & Tools  

- **OPNsense** — Firewall, Routing, VLAN Management  
- **WireGuard VPN** — Remote secure access  
- **Pi-hole** — DNS Filtering and Ad Blocking [Link to more info](./docs/pihole.md) 
- **OpenDNS** — Cloud-based DNS Security  
- **Unbound (DNS Resolver)** — Internal DNS resolution  
- **Ubuntu Server** — Media services and Pi-hole
- **Security Onion** - IDS (Intrusion Detction), NSM (Network Security Monitoring), Log Management and Threat Hunting [Link to more info](./docs/SecurityOnion.md) 

---

## VLAN Design  

| VLAN ID | Name        | Subnet         | Purpose                |
|:--------|:------------|:----------------|:------------------------|
| 10      | LAN          | 192.168.10.0/24 | Default Untagged         |
| 20      | Trusted      | 192.168.20.0/24 | Trusted Devices          |
| 30      | IoT          | 192.168.30.0/24 | IoT/Smart Devices        |
| 40      | Guest        | 192.168.40.0/27 | Guest WiFi               |
| 50      | Cameras      | 192.168.50.0/24 | IP Cameras               |
| 70      | Media        | 192.168.70.0/24 | Streaming devices/Jellyfin|
| 99      | Management   | 192.168.99.0/24 | Network device management|

---

## VPN Configuration  

- **WireGuard** VPN set up on OPNsense for secure remote access  


---

## DNS & Security  

- **Pi-hole** for DNS ad-blocking  
- **OpenDNS** for cloud-based DNS filtering  
- **Unbound DNS Resolver** configured for internal resolution with forwarding enabled

---

## Backup & Monitoring  

- Future integration: Reg Config Backups via OPNsense, Firmware update plan and scnapshot schedule, syslog, NTP monitoring, and SNMP stats collection

---

## Webtrees Self-Hosted Genealogy Platform

# Webtrees Self-Hosted Genealogy Platform

## Project Summary
This project documents my deployment and configuration of [Webtrees](https://webtrees.net/), an open-source, self-hosted genealogy application for managing and exploring family trees. The goal is to maintain full control over personal family history data while building hands-on experience with Linux server administration, LAMP stack management, and secure web hosting practices.

---

## Key Features
- Self-hosted on **Ubuntu Server** within my home lab environment
- Full **LAMP stack** deployment (Linux, Apache, MySQL/MariaDB, PHP)
- Secured with **Let's Encrypt SSL** for encrypted HTTPS access
- Automated **database and media backups**
- Fully private setup — no reliance on third-party genealogy platforms

---

## Why This Project?
- Provides a **private, customizable platform** for family history research
- Strengthens my skills in:
  - Web server administration (**Apache2**)
  - Database management (**MySQL/MariaDB**)
  - Linux security, backups, and system automation
- Supports long-term **digital preservation** of family records

---

## Future Plans
- Evaluate **Docker-based deployment** for easier portability
- Integrate with existing **home network services** (DNS, backup systems)
- Potential public-facing deployment with a domain and secure remote access

---

## Related Technologies
- Ubuntu Server 22.04 LTS
- Apache2
- MySQL or MariaDB
- PHP 8.x
- Let's Encrypt (Certbot)
- Webtrees 2.x

---

*This project reflects my ongoing efforts to build a secure, private, and reliable platform for family tree management while developing practical system administration skills in my home lab.*

---

## Future Plans  


[Future Projects](./docs/Future-Projects.md)



---

## Contact  

If you're interested in this project or have suggestions, feel free to connect with me on LinkedIn or reach out via GitHub Issues.

