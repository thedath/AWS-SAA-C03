
# Network Address Translation (NAT)

NAT got introduced because there are limited IPv4 addresses availble in the world. With NAT, local area networks (LAN) are being able to support any number of devices without exhausting the available IPv4 addresses. (Uses private IP format of 10.0.0.X)

### There are three types of NATs
1. **Static NAT:** Devices in the LAN are given a unique private IP and mapped each of them to unique public IPs. (Ex: AWS Gateway)
2. **Dynamic NAT:** Public IPs are limited. Those public IPs are distributed among the devices as per the demand. If all the public IPs are being allocated, other devices won't be able to connect to the internet.
3. **Port Address Translation (PAT):** Only one public IP is associated to the LAN and, outgoing and incoming IP packets are handled through by mapping random ports to the each device. Handled via a NAT table. (Ex: Home, office or public wirless networks connected to internet)
