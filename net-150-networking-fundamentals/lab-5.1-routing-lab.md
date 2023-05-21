---
description: 10/1/2022
---

# Lab 5.1: Routing Lab

This lab was intended to start working with routers in packet tracer as well as sniffers. The router had to be configured to a switch (which was connected to 3 PCs) and 2 PCs, which meant manually entering IP information and subnetting information in the router interface and in the PC's configurations.

When cabling, make sure you are using the proper cables for the proper networking devices. Not all these devices are on the same layer, so you will sometimes have to alternate between straight-through and cross-over copper wires.

### How to Configure a Router

* Place a router down, and turn the router off.
  * Drag in as many fast Ethernet modules as you need, and turn the router back on afterwards.
* Enter the CLI and type 'enable' to enter the root
* Enter the config mode with 'config t'
* Then select the interface you want to edit with 'interface \_\_\_\_'
* Edit the IP address and subnet mask parameters with 'ip address xxx.xxx.xxx.xxx yyy.yyy.yyy.yyy' (y = subnet mask)
  * Each interface is its own LAN
* Once finished type 'no shutdown' to restart the service, then press Ctrl+Z to exit and repeat for any additional interfaces.
