# Future Home Network Stack Plans

##  Hardware
- Integrate Ubiquiti APs  
- Add a managed Cisco switch  
- Expand server infrastructure (Proxmox cluster or additional lab servers)

##  Network Monitoring & SIEM
- Implement network monitoring tools - snmp, etc (LibreNMS)
- Set up Grafana dashboards for visual metrics
- Deploy Security Onion for centralized SIEM and intrusion detection
- Add Ansible - automation and configuration management tool - Routine IT tasks like updates, installs, config changes

##  Security & Key Management
- Integrate a free, open-source key management system (HashiCorp Vault or alternatives)
- Plan for centralized key management for VPNs, services, and secrets  

##  Virtualization & Lab Environment
- Run GNS3 for virtual network simulation and Cisco image testing  
- Create dedicated VM for GNS3 server instead of running locally on a laptop  

## VPN & Remote Access  
- Finalize WireGuard setup for secure VPN access  
- Explore automating key generation and distribution for VPN clients  

##  Future Configuration Tasks
- Create VLAN 99 as the default untagged management VLAN  
- Build out additional VLANs for IoT, Guests, Servers, and Security Onion  
- Review DHCP server scopes and resilience plans  
- Set up scheduled configuration backups for Cisco 1111 Router
- Investigate firmware auto-update / update options for Cisco gear  

#  Home Network Lab Documentation Outline

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
- Media services (Jellyfin) - This is set up.  Need to complete documentation.
- VMware set up on server
- Truenas build out and NAS setup to support network
- Jellyfin set up with passive loadbalancing/redundancy
- True Backup System for Network Backup
- Firewall config, VLAN setup, rules summary    
- VPN (WireGuard)  
- SIEM (Security Onion)  
- Metrics & monitoring (Grafana, Zabbix, LibreNMS) 
- Install Next Cloud in my environment and evaulate moving away from Office 365 for family needs: https://nextcloud.com/
- Home Assistant: https://www.home-assistant.io/
- Create App/Game for my Kids
  

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



Netflow collector
wire shark - automation and alerting?

