---
description: 9/10/2022
---

# Lab 2.2: Observing LAN Activity

In this lab, we explored the program WireShark and how it can be used to monitor and view specifics of network traffic. Also explored how Address Resolution Protocol (ARP) works.

### What is a MAC address and what are its components?

* A MAC address (MAC stands for Media Access Control) is a unique number assigned to a physical port on a piece of hardware/device. It is similar in functionality to a home address, as it is a constant identifier for a specific device (or location if home address). The first 6 numbers in a MAC address are known as the organizationally unique identifier (OUI) and are unique to the manufacturer of the device, and the last 6 numbers are unique to the specific networking device that the port is attached to.&#x20;

### How do you get a MAC address?

* The MAC address is obtainable in many ways, but one of the easiest is to open a PowerShell or Command Prompt window and type the command ipconfig /all and look for the Physical Address.&#x20;

### What is WireShark and how is it used?

* WireShark is a program designed to monitor network traffic as it happens. It allows the user to choose a specific networking interface to monitor (ethernet, wifi, etc.) and record a capture of all network activity/packet activity that passes through the network during the capture.&#x20;

### How do you find a protocol in WireShark?

* Protocols are accessable in WireShark by either clicking the drop-down menu that is labeled "Protocol" in a capture window, or typing in the desired protocol in the search field at the top of the window.
