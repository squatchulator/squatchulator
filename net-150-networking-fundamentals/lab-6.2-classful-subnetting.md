---
description: 10/8/2022
---

# Lab 6.2: Classful Subnetting

This lab was split into two separate parts, one part covering the creation of a subnet table for Foster, Joyce, and Skiff networks with the netmask /27 (255.255.255.224) and the other part consisted of building the network in packet tracer using the subnet table. Configuration of the subnets once the addresses were clear was easy, but finding out subnetted addresses is something I will definetley need to dedicate some more time to mastering. One thing that I will need to ensure I memorize is that the network address and the broadcast address need to be accounted for when subnetting as those are treated as hosts.

### Serial Connections

* Used to create a WAN connection (multiple networks are connected in this lab, therefore it is a WAN)
* "Provides serial WAN connectivity to remote sites using Cisco High-Level Data Link Control (HDLC), Point-to-Point Protocol (PPP), or Frame Relay encapsulation through the pluggable, serial WAN interface module." ([https://www.cisco.com/c/en/us/td/docs/routers/access/800M/software/800MSCG/serconf.html#98028](https://www.cisco.com/c/en/us/td/docs/routers/access/800M/software/800MSCG/serconf.html#98028)) RIP
* Stands for Router Information Protocol
* Is a distance vector protocol, which means that some or all of the routing tables from the routers are shared via routing update messages
* Uses hop count between networking devices to find the best routing path
