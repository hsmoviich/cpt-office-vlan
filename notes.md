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




WAN 2 hosts
R1
R2

|Name   	|IP Address   	|Subnet Mask   	|Connetion|
|---	|---	|---	|---	|
|**IT Vlan|192.168.0.0/27|255.255.255.224**|
| PC1  	|192.168.0.1/27|255.255.255.224|   	|
| PC2	|192.168.0.2/27|255.255.255.224|   	|
| PC3  	|192.168.0.3/27|255.255.255.224|   	|
| PC4  	|192.168.0.4/27|255.255.255.224|   	|
|**Admin VLAN|192.168.0.32/27|255.255.255.224**|   	|
| PC8  	|192.168.0.33/27|255.255.255.224|   	|
| PC9  	|192.168.0.34/27|255.255.255.224|   	|
| PC10  |192.168.0.35/27|255.255.255.224|   	|
| PC11 	|192.168.0.36/27|255.255.255.224|   	|
|**HR VLAN|192.168.0.64/27|225.255.255.224**|   	|
|  PC5 	|192.168.0.65/27|225.255.255.224|   	|
|  PC6 	|192.168.0.66/27|225.255.255.224|   	|
|  PC7 	|192.168.0.67/27|225.255.255.224|   	|
|**Guest VLAN|192.168.0.96/28|255.255.255.240**|   	|
|  PC12	|192.168.0.97/28|255.255.255.240|   	|
|  PC13	|192.168.0.98/28|255.255.255.240|   	|
|**Servers VLAN|192.168.0.112/29|255.255.255.248**|   	|
|DHCP Server|192.168.0.113/29|255.255.255.248|   	|
|DNS Server|192.168.0.114/29|255.255.255.248|   	|
|**WAN|192.168.0.120/30|255.255.255.252**|   	|
|  R1 	|192.168.0.120/30|255.255.255.252|   	|
|  R2 	|192.168.0.120/30|255.255.255.252|   	|


## Issues & Solutions

[Document any issues encountered and their solutions]

## Ideas & TODOs

- [ ] [Add todo items here]
- [ ] [Another todo item]

## Important Information

[Add any important information or reminders]


## References

- [Add useful links and references]

