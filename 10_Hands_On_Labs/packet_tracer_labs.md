# Sample Packet Tracer Exercises

## What is Cisco Packet Tracer?
Cisco Packet Tracer is a network simulation tool that allows you to create network topologies and practice with Cisco devices. It's a great tool for beginners because it's free, easy to use, and includes many CCNA-level features.

## Lab 1: Basic LAN Configuration
**Goal:** Configure a simple LAN with a switch, two PCs, and a router.
**Steps:**
1.  Open Packet Tracer and drag a `2960` switch, two `PC`s, and a `1941` router onto the canvas.
2.  Connect the devices using `Copper Straight-Through` cables.
3.  Configure the router's interface connected to the switch with the IP address `192.168.1.1/24`. Remember to use `no shutdown`.
4.  Configure the PCs with static IP addresses in the `192.168.1.0/24` subnet and set the default gateway to `192.168.1.1`.
5.  Use the `ping` command from one PC to the other and from each PC to the router to verify connectivity.

## Lab 2: VLANs and Inter-VLAN Routing
**Goal:** Configure two VLANs on a switch and enable routing between them on a router.
**Steps:**
1.  Use the topology from Lab 1, but add two more PCs.
2.  Configure VLAN 10 (`Sales`) and VLAN 20 (`IT`) on the switch.
3.  Assign one PC to VLAN 10 and another to VLAN 20.
4.  Configure the router for "Router-on-a-Stick" inter-VLAN routing by creating subinterfaces on the router's physical interface.
    - `interface GigabitEthernet0/0.10`: Configure this subinterface for VLAN 10.
    - `interface GigabitEthernet0/0.20`: Configure this subinterface for VLAN 20.
5.  Set the encapsulation and IP addresses for each subinterface.
6.  Set the switch port connected to the router as a trunk port.
7.  Verify connectivity by pinging between the PCs in different VLANs.

**Hint:** You can find more labs and tutorials on the Cisco Networking Academy website.
