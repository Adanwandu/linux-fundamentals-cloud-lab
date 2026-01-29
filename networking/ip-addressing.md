Network: 192.168.64.0/24

172.20.10.10   → Host(MAC)
192.168.64.8   → Load Balancer
192.168.64.7   → linux-fundamentals
192.168.64.9   → Web Server 2
192.168.64.10   → NAT VM

## CIDR & Network Planning

All virtual machines in this project are deployed within the
`192.168.64.0/24` private network.

The `/24` CIDR notation means:
- 24 bits are reserved for the network
- 8 bits are available for host addresses
- 254 usable IP addresses exist in this subnet

This setup mirrors real cloud environments where large networks
are subdivided into smaller subnets for security and organization.
