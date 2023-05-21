---
description: 11/8/2022
---

# Lab 12.2: Building a WLAN in Packet Tracer

### Steps for Setting up a WLAN in Packet Tracer: Wireless Router Configuration:

* Start by opening the Wireless Router settings and navigating to the GUI tab.
* Set the connection type to static, and assign the internet/uplink IP.
* Scroll down to Network Setup and enter the LAN internet address for the router. Enable DHCP and click save changes.
* In the Wireless tab at the top, set network mode to Wireless-N Only. Change network name if desired, disable SSID broadcast, and save changes.
* Click on Wireless Security at the top. Set security mode to WPA2 Personal and set a passphrase. Save settings. Client Configuration:
* Click on laptop, and navigate to Desktop > PC Wireless. Create a new profile, and name it.
* Click Advanced Setup, and make sure Infrastructure Mode is checked. Enter the SSID of the router in Wireless Network Name.
* Leave Obtain Network Settings Automatically (DHCP) checked.
* Choose WPA2-Personal in the Wireless Security dropdown.
* Enter your password, click Next, Save, and Connect to Network.
* Should be able to see that Laptop is connected to router with a visible signal indicator. If not, try re-entering the passkey in the laptop's config window.
  * If wireless connections are still not working, ensure IPs are entered correctly first and foremost.
  * The network password may be entered wrong somewhere. Ensure this doesn't happen by writing it down somewhere you will remember, and double-checking that the router and the laptop have the same passkey entered.

### Troubleshooting

* Was not able to connect Laptop1 to Wireless Router. Re-traced steps and attempted setup process again, and found that I had entered passkey in wrong. Entered passkey again, and Laptop1 connected successfully.
* Started lab file up again to ensure things were working, and laptops were configured with strange DHCP IP addresses and couldn't access the WebServer. Started by reconfiguring network with IPs to ensure that they were entered correctly, and this still didn't fix it. Tried different default gateways (entered manually) in the laptops, and this did not work either. Also tried static/rip routing. After none of this worked, I went into the router and re-entered all the IP/DHCP information. When I hit save, the IP addresses appeared to be in the correct range on the laptops, and they could all visit the WebServer properly.
