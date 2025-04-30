# 📌 Future Home Network Stack Plans

## 🔧 Hardware
- Integrate Ubiquiti or Cisco enterprise APs  
- Add a managed Cisco switch  
- Possibly replace OPNsense router with Cisco ISR (C1100 or C1111 series)  
- Expand server infrastructure (Proxmox cluster or additional lab servers)

## 📊 Network Monitoring & SIEM
- Implement network monitoring tools (Zabbix, LibreNMS)
- Set up Grafana dashboards for visual metrics
- Deploy Security Onion for centralized SIEM and intrusion detection  

## 🔐 Security & Key Management
- Integrate a free, open-source key management system (HashiCorp Vault or alternatives)
- Plan for centralized key management for VPNs, services, and secrets  

## 📚 Documentation & Knowledge Management
- Maintain full Home Network Lab Documentation on GitHub (network diagrams, configs, decisions)
- Possibly mirror or sync documentation in Obsidian for local offline notes

## 🌐 Virtualization & Lab Environment
- Run GNS3 for virtual network simulation and Cisco image testing  
- Create dedicated VM for GNS3 server instead of running locally on a laptop  

## 🗂️ DNS & Filtering  
- Integrate Pi-hole for DNS filtering  
- Decide whether to replace or integrate alongside Unbound and OpenDNS  

## 🔒 VPN & Remote Access  
- Finalize WireGuard setup for secure VPN access  
- Explore automating key generation and distribution for VPN clients  

## 📑 Future Configuration Tasks
- Create VLAN 99 as the default untagged management VLAN  
- Build out additional VLANs for IoT, Guests, Servers, and Security Onion  
- Review DHCP server scopes and resilience plans  
- Set up scheduled configuration backups for OPNsense  
- Investigate firmware auto-update options for OPNsense or Cisco gear  

# 📖 Home Network Lab Documentation Outline

## 1. Project Overview
- Purpose: Learning, security hardening, career development  
- Key technologies and tools  

## 2. Network Topology
- Network diagram  
- VLAN list, IDs, purposes, subnets  
- Rationale for segmentation  

## 3. Hardware Inventory
- Firewalls, switches, APs, servers, IoT, media servers  

## 4. Services & Software Stack
- Firewall config, VLAN setup, rules summary  
- DNS (Unbound, OpenDNS, Pi-hole)  
- VPN (WireGuard)  
- SIEM (Security Onion)  
- Metrics & monitoring (Grafana, Zabbix, LibreNMS)  
- Media services (Jellyfin)

## 5. Configuration Details
- Interface assignments  
- DHCP scopes  
- NTP setup  
- DNS forwarding  
- VPN configs  
- Firewall rules (summary only)

## 6. Key Decisions & Rationale
- Choices, pros/cons, alternatives  

## 7. Lessons Learned
- Challenges, fixes, future improvements  

## 8. Future Plans
- Hardware, services, features to add  

## 9. Resources
- Links to official docs, tutorials, references  
