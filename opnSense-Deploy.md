The goal of this project was to setup and deploy OpnSense on a standalone device, implement it into my home network and have it take over routing, vlan, NAT, Firewall, IDS (Suricata), and DNS resolution.

I installed OpnSense on a spare Qotom Computer with five NIC's.  Intial setup is One NIC for the LAN and one for the WAN.  The other NIC's will be explored in the future.  The computer itself was running OpenHAB on a windows 10 platform.  This device was no longer suitable for that function and was not capable of running windows 11, thus it was repurposed into use for OPNsense.

The intital setup with defaults intact was straighforward.
After getting through the wizard, I added several vlans.  I also had to turn my current Wifi Router into AP mode and made sure NAT, DHCP, Firewall were turned off. 
Subsequently I set up the same wifi networks as the vlans, including vlan tagging.
Ensuring that each seperate wifi ssid was obtaining the correct ip for that vlan, which indicated that DHCP for each vlan was working correctly

Next was setting up DNS.  My choice for this was to enable Unbound (in opnsense), for local dns resolution, and the forward all external traffic to OpenDNS.  This required a home account setup at opendns so that I can track metrics and set filtering.



