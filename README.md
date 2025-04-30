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

![Network Diagram](./diagrams/network-diagram-v1.png)

*Add a clean diagram of your VLANs, physical and logical connections*

---

## Services & Tools  

- **OPNsense** — Firewall, Routing, VLAN Management  
- **WireGuard VPN** — Remote secure access  
- **Pi-hole** — DNS Filtering and Ad Blocking  
- **OpenDNS** — Cloud-based DNS Security  
- **Unbound (DNS Resolver)** — Internal DNS resolution  
- **Ubuntu Server** — Media services and Pi-hole  

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

## Future Plans  

- Integrate Ubiquiti or Cisco enterprise APs  
- Add a managed Cisco switch  
- Implement network monitoring tools (Zabbix/LibreNMS)
- Home Network Lab Documentation
1. Project Overview
Brief description of your home network lab
-key management

Purpose of the project (learning, security hardening, career development, etc.)

Key technologies and tools being used

2. Network Topology
Network Diagram (Visual)

Full map of devices, VLANs, and connections

VLAN Design

List of VLANs with IDs, purposes, and subnets

Rationale for segmentation

3. Hardware Inventory
List of all physical devices

Firewall (OPNsense box)

Switches (TP-Link, future Cisco)

Wi-Fi Access Points (Synology / Ubiquiti plan)

Servers (Ubuntu server, etc.)

IoT devices, Cameras, Media servers

4. Services & Software Stack
Firewall (OPNsense)

Basic config

VLAN setup details

Rules and policies summary

DNS

Unbound setup

OpenDNS integration

Pi-hole integration (if added)

VPN

WireGuard setup notes

SIEM & Security

Security Onion notes (planned or active)

Metrics & Monitoring

Grafana setup and dashboards

Media Services

Jellyfin setup

5. Configuration Details
Interface assignments

DHCP scopes for VLANs

NTP configuration

DNS forwarding setup

Firewall rule sets (summarized, not actual rules for security reasons)

VPN configs

6. Key Decisions & Rationale
Why you chose each piece of software and hardware

Advantages and limitations

Alternatives you considered

7. Lessons Learned
Challenges encountered

Solutions you implemented

Improvements you plan to make

8. Future Plans
Next tools or hardware to add

Features you want to experiment with

9. Resources
Links to official docs, tutorials you followed, etc.



---

## License  

This repository is open-sourced under the [MIT License](./LICENSE).

---

## Contact  

If you're interested in this project or have suggestions, feel free to connect with me on LinkedIn or reach out via GitHub Issues.

