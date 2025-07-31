# How to Practice with Real Hardware

## Why use Real Hardware?
While simulators and emulators are great for learning, nothing beats practicing with real hardware.
- You gain experience with physical connections and cable management.
- You learn how to perform a device's initial setup.
- You understand how to handle the physical aspect of network devices.
- You get to hear the fans whir!

## Building a Basic Lab
- **Routers:** Look for older models like Cisco `1841`, `2811`, or `2901`. They are inexpensive and support all the basic CCNA features.
- **Switches:** Cisco `2960` or `3560` series switches are great for CCNA-level labs.
- **Cables:** You will need Ethernet cables (straight-through and crossover), a console cable, and power cables.
- **Terminal:** You'll need a laptop with a terminal emulator like PuTTY or SecureCRT to connect to the console port.

## Where to find hardware
- **eBay or other second-hand marketplaces:** You can often find used Cisco equipment for very low prices.
- **Local computer recycling centers:** Sometimes they have older network gear.
- **Friends/colleagues:** Ask around to see if anyone has old equipment they want to get rid of.

## Getting Started
1.  Connect your laptop to the console port using a console cable.
2.  Use your terminal emulator to connect to the device.
3.  Erase the old configuration using `erase startup-config` and `reload`.
4.  Start from scratch and follow the labs from this repository.
