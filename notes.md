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

IP Address for IT VLAN => 192.168.0.0/27 255.255.255.224
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

IP Address for Admin VLAN => 192.168.0.32/27 255.255.255.224
Next IP Address => 192.168.0.64/27

#### HR VLAN 15 Hosts

This network requires 15 hosts

2^h-2=>25
2^5-2=>32-2=30

we will be using 5 bits and we will have 30 usable host addresses

the new subnet mask is going to be 32-5=27 thus:

192.168.0.64/27
11111111.11111111.11111111.11100000
255.255.255.224

Blocksize => 256-224=32

IP Address for HR VLAN => 192.168.0.64/27 255.255.255.224
Next IP Address => 192.168.0.96/27

#### Guest Vlan 10 Hosts

This network requires 10 hosts

2^h-2=>10
2^4-2=>16-2=14

We will be using 4 bits and we will have 14 usable host addresses

The new subnet mask is going to be 32-4=28 thus:

192.168.0.96/28
11111111.11111111.11111111.11110000
255.255.255.240

Blocksize => 256-240=16

Ip Address for Guest Vlan => 192.168.0.96/28 255.255.255.240
Next IP Address => 192.168.0.112/28

#### Servers VLAN 5 hosts

This network requires 5 usable host addresses

2^h-2=>5
2^3-2=>8-2=6

We will be using 3 bits and we will have 6 usable host addresses
The new subnet mask is going to be 32-3=29

192.168.0.112/29
11111111.11111111.11111111.11111000
255.255.255.248

Blocksize => 256-248=8

IP Address for Servers VLAN => 192.168.0.112/29 255.255.255.248
Next IP Address => 192.168.0.120/29

#### WAN 2 hosts

This network requires 2 usable host addresses so by default its going to be /30

We will be using 2 bits and we will have 2 usable host addresses
The new subnet mask is going to be 32-2=30

Blocksize => 256-252=3

192.168.0.120/30 255.255.255.252

### Routing Table

IT VLAN 25 hosts
PC1
PC2
PC3
PC4
Admin VLAN 25 hosts
PC8
PC9
PC10
PC11
HR VLAN 15 hosts
PC5
PC6
PC7
Guest VLAN 10 hosts
PC12
PC13
Servers VLAN 5 hosts
DHCP Server
DNS Server
WAN 2 hosts
R1
R2

|Name   	|IP Address   	|Subnet Mask   	|Connetion|
|---	|---	|---	|---	|
|   	|   	|   	|   	|
|   	|   	|   	|   	|
|   	|   	|   	|   	|
|   	|   	|   	|   	|
|   	|   	|   	|   	|
|   	|   	|   	|   	|
|   	|   	|   	|   	|
|   	|   	|   	|   	|
|   	|   	|   	|   	|
|   	|   	|   	|   	|
|   	|   	|   	|   	|
|   	|   	|   	|   	|
|   	|   	|   	|   	|
|   	|   	|   	|   	|
|   	|   	|   	|   	|
|   	|   	|   	|   	|
|   	|   	|   	|   	|
|   	|   	|   	|   	|
|   	|   	|   	|   	|
|   	|   	|   	|   	|
|   	|   	|   	|   	|
|   	|   	|   	|   	|


## Issues & Solutions

[Document any issues encountered and their solutions]

## Ideas & TODOs

- [ ] [Add todo items here]
- [ ] [Another todo item]

## Important Information

[Add any important information or reminders]


## References

- [Add useful links and references]

