** Connecting your virtual machines to world outside (Internet): **

Install Proxmox, make network-configure.sh script executable with chmod +x network-configure.sh and start it to automatically deploy new bridge and iptables NAT forwarding rules. Script will read your network card's IP address, subnet mask and default gateway and create a new bridge with same settings, effectively giving Internet access to all guests VM's using this bridge.

** Connecting world outside (Internet) to your virtual machines: **

forward.sh is a simple script that's forwarding ports from hypervisor's WAN address to LAN address of guest VM's behind the NAT. First make the script executable with chmod +x forward.sh and then edit it to change your VM LAN address, and WAN and LAN ports. Save it and run it with bash forward.sh
Works perfect with Proxmox on bare metal (such as Scaleway's Elastic Metal line or Hetzner's server auctions). 
