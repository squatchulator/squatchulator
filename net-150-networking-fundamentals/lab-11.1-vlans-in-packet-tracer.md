---
description: 11/8/2022
---

# Lab 11.1: VLANs in Packet Tracer

### Creating VLANs + Access & Trunk Port Configuration

* Start by opening the VLAN database on the switch you'd like to configure. Add a number, and name for the VLAN you would like to create.
  * Ensure the name/number is consistent across switches!
* Once VLANs are added to switch databases, each VLAN can now be mapped to an Ethernet port on the switch. Ensure you are using access mode for connections between switch/host. Access mode handles the traffic for a single VLAN.
* After configuring ports, connect switches via crossover cable in their Gigabit Ethernet ports.
  * For these connections, ensure you are using trunk mode. This will allow us to route traffic to and from multiple VLANs. Select the VLANs you have configured in the trunk dropdown menu - it's ok to leave the defaults enabled too.
* Assuming unique IPs have been implemented correctly, you should only be able to communicate within VLANs and not from VLAN to VLAN.&#x20;

### What is "Router on a stick"?

* Also known as a one-armed router, a router on a stick is a router that has a single physical connection via trunk access to a network. This allows routing and communication between VLANs that would otherwise not be able to communicate with one another on the same physical LAN, while still keeping them separated. Applications of this are seen in enterprise networks in which users should not have equal access to network resources. It can be connected to any switch in the network through fast Ethernet, and can be connected with the standard copper cable in Packet Tracer.
