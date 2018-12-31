+++
menutitle = "VirtualBox Network"
date = 2018-12-29T17:15:52Z
weight = 6
chapter = false
pre = "<b>- </b>"
+++

# VirtualBox network configuration
- Create HostOnly network with IP range `192.168.78.0`
  - Open Virtual Box
  - Got to menu and navigate to File ->Host Network Manager
  - Then click "Create"
  - Modify the network range to `192.168.78.0/24` if its different.
 This will create a Host-Only Network.

 DHCP should be disabled on this network.

 Internet access is needed on all VMs (for downloading needed binaries).

 Make sure you can see the NAT network.(If not , create one).


| VBox Host Networking |      
|---------------|--------------
| HostOnly      | 172.28.10.0
| NAT           | VBOX Defined