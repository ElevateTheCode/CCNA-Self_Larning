# 802.1Q Trunking

## What is Trunking?
A switch trunk is a physical link that carries traffic for multiple VLANs between switches or between a switch and a router.

**Why use a Trunk?**
Without a trunk, you would need a separate physical cable for each VLAN between switches, which is inefficient. A trunk allows all VLAN traffic to share a single link.

## 802.1Q Standard
The IEEE 802.1Q standard is the most common method for trunking. It works by "tagging" each frame with a VLAN ID as it travels across the trunk link. This allows the receiving switch to know which VLAN the frame belongs to.

## Configuration Example
This example shows how to configure a port as a trunk on a Cisco switch.

**On Switch 1:**
Switch1(config)# interface FastEthernet0/24
Switch1(config-if)# switchport mode trunk
Switch1(config-if)# switchport trunk encapsulation dot1q


**On Switch 2:**
Switch2(config)# interface FastEthernet0/24
Switch2(config-if)# switchport mode trunk
Switch2(config-if)# switchport trunk encapsulation dot1q

- `switchport mode trunk`: Sets the interface to trunking mode.
- `switchport trunk encapsulation dot1q`: Specifies the 802.1Q tagging protocol. (This command is not required on newer switches as it's the default).

**Optional: Allowing specific VLANs on a trunk**
By default, a trunk allows all VLANs. You can specify a list of allowed VLANs for security and traffic control.
Switch1(config-if)# switchport trunk allowed vlan 10,20,30

This command only allows traffic for VLANs 10, 20, and 30 to pass over the trunk.

**Verification Command:**
Switch# show interfaces trunk

This command displays which ports are configured as trunks and which VLANs are allowed.
