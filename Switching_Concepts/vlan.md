# VLANs (Virtual Local Area Networks)

## What is a VLAN?
A VLAN is a logical grouping of devices that are on the same broadcast domain, regardless of their physical location. This means devices in the same VLAN can communicate with each other as if they were on the same physical switch, even if they are connected to different switches.

**Why use VLANs?**
- **Security:** Devices in different VLANs cannot communicate by default.
- **Performance:** Reduces the size of broadcast domains, which decreases network traffic.
- **Management:** Simplifies network administration by logically grouping devices.

## Configuration Example
This example shows how to create a VLAN and assign ports to it on a Cisco switch.

**Step 1: Create the VLAN**
Switch(config)# vlan 10
Switch(config-vlan)# name Sales


**Step 2: Assign ports to the VLAN**
- You can assign a single port or a range of ports.
- **Assign single port:**
Switch(config)# interface FastEthernet0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 10

- **Assign a range of ports:**
Switch(config)# interface range FastEthernet0/2 - 5
Switch(config-if-range)# switchport mode access
Switch(config-if-range)# switchport access vlan 10


**Verification Command:**
Switch# show vlan brief

This command displays a summary of all VLANs and the ports assigned to them.
