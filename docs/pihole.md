# Pi-hole Setup on Proxmox VMs — Summary

## Overview
This project documents the setup of two Pi-hole DNS servers running on separate Ubuntu Server VMs inside Proxmox. The goal was to provide reliable network-wide ad blocking with redundancy.

---

## Steps Completed

### 1. Created Ubuntu Server VMs on Proxmox
- Installed Ubuntu Server (minimal, no desktop) on two separate VMs.
- Assigned static IP addresses to each VM via netplan:
  - VM1: `192.168.1.6`
  - VM2: `192.168.1.7`

---

### 2. Installed Pi-hole on Each VM
- Installed Pi-hole using the official curl install script:
  ```bash
  curl -sSL https://install.pi-hole.net | bash
  ```
- Configured initial Pi-hole settings and admin password.
- Verified Pi-hole web UI accessibility.

---

### 3. Network and DNS Configuration
- Set static IP addresses in netplan and applied them.
- Configured Pi-hole to use public DNS servers (e.g., Cloudflare 1.1.1.1) temporarily during setup.
- Switched Pi-hole’s nameserver back to `127.0.0.1` after setup for local DNS resolution.

---

### 4. Integrated Pi-hole with Cisco Router DHCP
- Updated Cisco C1111 router DHCP pool configuration to set Pi-holes as DNS servers:
  ```plaintext
  ip dhcp pool LAN
  dns-server 192.168.1.6 192.168.1.7
  ```
- Ensured clients receive Pi-hole IPs via DHCP for DNS.

---

### 5. Troubleshooting and Testing
- Resolved SSH key exchange issues on the router by using SSH client options to accept older algorithms.
- Verified DNS resolution from client devices pointed to Pi-hole IPs.
- Tested Pi-hole functionality and blocking effectiveness.

---

### 6. Attempted Pi-hole Gravity Sync Setup (Retired)
- Attempted to install Gravity Sync for syncing blocklists between Pi-holes.
- Encountered DNS resolution issues with `gravity-sync.dev`.
- Learned that Gravity Sync is retired and incompatible with Pi-hole v6+.
- Decided to explore manual or custom syncing alternatives.

---

### 7. Next Steps and Recommendations
- Consider manual syncing of blocklists or shared external lists.
- Explore or develop custom scripts to sync configurations safely.
- Keep Pi-hole updated and monitor community tools for new syncing solutions.

---

## Commands and Config Snippets

### Setting Static IP in Netplan (Example for `192.168.1.6`)

```yaml
network:
  version: 2
  ethernets:
    ens18:
      dhcp4: no
      addresses:
        - 192.168.1.6/24
      gateway4: 192.168.1.1
      nameservers:
        addresses:
          - 1.1.1.1
          - 8.8.8.8
```

Apply with:

```bash
sudo netplan apply
```

---

### Updating Cisco DHCP DNS Servers

```plaintext
ip dhcp pool LAN
dns-server 192.168.1.6 192.168.1.7
```

---

### Checking Pi-hole Version

```bash
pihole -v
```

---


