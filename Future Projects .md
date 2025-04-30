# 📑 Future Projects / Things to Implement

A running list of improvements, upgrades, and experiments planned for my home network lab environment.

## ✅ Planned Network Projects

- **Deploy a SIEM solution**  
  _Plan: Implement Security Onion for network security event monitoring._

- **Stand up a key management solution**  
  _Plan: Deploy HashiCorp Vault (or alternative open-source option) for secure key and secret storage._

- **Deploy GNS3 network emulator**  
  _Plan: Set up a dedicated VM for GNS3 to simulate enterprise-grade network topologies and Cisco environments._

- **Automate WireGuard VPN peer management**  
  _Plan: Create scripts or tools to streamline key generation and peer configuration for VPN connections._

- **Finalize network documentation repository**  
  _Plan: Continue developing and publishing network diagrams, config notes, and setup documentation to GitHub and/or Obsidian vault._

- **Automate OPNsense config backups**  
  _Plan: Configure scheduled automated backups of OPNsense configuration files._

- **Evaluate firmware auto-update strategy for OPNsense**  
  _Plan: Research and implement a safe, controlled method for firmware updates if practical._

- **Implement segmented VLANs**  
  _Plan: Design and deploy multiple VLANs for device segmentation and improved security once the network baseline is stable._

- **Deploy centralized syslog server**  
  _Plan: Configure a central log aggregation service for OPNsense and other network hardware._

- **Deploy Pi-hole (or AdGuard Home)**  
  _Plan: Integrate DNS filtering into the network and decide on the final DNS stack configuration._

- **Publish full network topology diagram and documentation**  
  _Plan: Create and maintain clear, visually engaging diagrams for lab network architecture and include rationale for design choices._

- **Evaluate potential migration to Cisco ISR (C1100/1111 or newer)**  
  _Plan: Transition routing responsibilities from OPNsense to a Cisco enterprise-grade router, pending hardware availability._

- **Set up a backup VPN instance**  
  _Plan: Deploy an OpenVPN or secondary WireGuard server for redundancy._

- **Deploy SNMP monitoring (or Zabbix)**  
  _Plan: Implement a centralized solution for device health, status monitoring, and alerting._

- **Explore Zero Trust network architecture**  
  _Plan: Design and test a Zero Trust framework within the home lab environment._

- **Deploy a management VLAN (VLAN 99)**  
  _Plan: Use VLAN 99 for network management services and possibly as a dead-end for unauthorized traffic._

- **Network Hardening
  -Configuration that exposes a large attack surface,
  -open service ports, 
  -weak or no authentication, 
  -use of default credentials, 
  -lack of secure communication / encryption**

- **RADIUS/NAC server (like FreeRADIUS) to test AAA setups**   

- **SYSLOG server to collect logs from Cisco devices**  







-NetFlow collector (like ntopng or nfdump) to parse Cisco NetFlow exports
