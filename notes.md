# Notes

This document contains notes and observations for the cpt-office-vlan project.

## Project Notes

Started with designing the topology creating colored fields to make it easier to disect which is which topology.
Now starting to do subnetting for the topology

### Subnetting

Network IP Address is 192.168.0.0/24

The topology requirements are the following
IT VLAN 25 hosts
Admin VLAN 25 hosts
HR VLAN 15 hosts
Guest VLAN 10 hosts
Servers VLAN 5 hosts
WAN 2 hosts

#### IT VLAN 25 hosts

First IP Address 192.168.0.0/24
Subnet mask 255.255.255.0 or 11111111.11111111.00000000.00000000

This network requires 25 hosts 

2^h-2=>25
2^5-2=>32-2=30

we will be using 5 bits and we will have 30 usable host addresses

the new subnet mask is going to be 32-5=27 thus:

192.168.0.0/27
11111111.11111111.11111111.11100000
255.255.255.224

Blocksize => 256-224=32

IP Address for IP VLAN => 192.168.0.0/27 255.255.255.252
Next IP Address => 192.168.0.32/27

#### Admin VLAN 25 hosts

This network requires 25 hosts 

2^h-2=>25
2^5-2=>32-2=30

we will be using 5 bits and we will have 30 usable host addresses

the new subnet mask is going to be 32-5=27 thus:

192.168.0.32/27
11111111.11111111.11111111.11100000
255.255.255.224

Blocksize => 256-224=32

IP Address for IP VLAN => 192.168.0.32/27 255.255.255.252
Next IP Address => 192.168.0.64/27

#### HR VLAN 15 Hosts

This network requires 15 hosts








to accomodate this network requirements we will be taking 3 network bits and converting them to host bits 

## Issues & Solutions

[Document any issues encountered and their solutions]

## Ideas & TODOs

- [ ] [Add todo items here]
- [ ] [Another todo item]

## Important Information

[Add any important information or reminders]


## References

- [Add useful links and references]

