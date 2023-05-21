---
description: 11/5/2022
---

# Lab 10.1: Packet Tracer RIP Lab

RIP is a dynamic distance-vector protocol in which connected routers send most or all of their routing tables to define how packets should move across the network. It uses hop count as its metric and has the ability to avoid routing loops by limiting the number of hops per path to 15. The differences between the outdated RIPv1 and RIPv2 are that RIPv2 has VLSM support, sends the subnet mask in its table, manual route summarization, and can work for classless and classful networks.

This lab focused on being an introduction to RIP dynamic routing. Using a pre-configured packet tracer file, we set up RIPv2 in each connected router, and specified the routing tables to be exchanged between the routers. We then examined the RIP packets sent between routers to further understand the steps and processes RIP uses to share routing information.

### Configuring RIPv2 in Packet Tracer

* Start by opening the router, and enter config mode
* Enter `router rip`
* **Make sure you are using RIPv2!!! This can be done by typing `version 2` in the RIP config.**
* Follow this with the router's network address you'd like to configure with the format `network X.X.X.X`. Repeat this with serial connections/inter-router connections as well.
