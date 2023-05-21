---
description: 10/6/2022
---

# Lab 7.1: VLSM

The purpose of this lab was to explore VLSM, and connecting networks via RIP routing. This lab consisted of connecting 3 subnetted networks linked to 1 router to another router linked to 2 other subnetted networks, and adding the network to each router's RIP table.

### Issues:

* One of the larger issues I ran into while working on this lab was that I could not get the routers to communicate with eachother properly. Despite setting the RIP network address to 172.16.0.0 on both routers, end devices were not able to ping end devices on the other network. Eventually after a bit of research I found that my routers were using RIP v1 rather than v2.
  * RIP v2 is a much more feature-packed protocol that supports classful subnetting, VLSM, route summarization, and CIDR. My issue stemmed from the fact that I was attempting to use RIP v1 for a VLSM network when it's unsupported by that technology.
* I found that my subnets were often typed in mistakenly as well. Many times my end devices would not ping eachother because I had entered the subnet incorrectly.
  * I have started writing/drawing out my network topologies beforehand so that I can see exactly what goes where without having to reference multiple sources at once.
