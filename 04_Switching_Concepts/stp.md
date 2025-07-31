# STP (Spanning Tree Protocol)

## What is STP?
Spanning Tree Protocol (STP) is a Layer 2 protocol that prevents switching loops in a network. A switching loop occurs when there are multiple paths between switches, causing broadcasts to circulate endlessly.

**How does STP work?**
STP works by electing a **Root Bridge** for the entire network. Then, it determines the best path to the Root Bridge for each switch and logically "blocks" redundant links to prevent loops.

- **Root Bridge:** The switch with the lowest Bridge ID (BID). The BID is a combination of a priority value (default 32768) and the switch's MAC address.
- **Port States:** STP puts ports into different states to prevent loops:
    - **Blocking:** The port is not forwarding frames to prevent a loop.
    - **Listening:** The port is processing BPDUs (Bridge Protocol Data Units) to find the Root Bridge.
    - **Learning:** The port learns MAC addresses but does not forward frames.
    - **Forwarding:** The port is actively forwarding frames.

## Configuration
STP is enabled by default on Cisco switches. The primary configuration task is often to manipulate which switch becomes the Root Bridge.

**Making a switch the Root Bridge:**
Switch(config)# spanning-tree vlan 10 priority 4096

- A lower priority value makes a switch more likely to be the Root Bridge. The default is 32768. We're setting it to 4096 here for VLAN 10.

**Alternative command (more user-friendly):**
Switch(config)# spanning-tree vlan 10 root primary

This command automatically sets the priority to 24576 (or 4096 if another switch has a lower priority) to make this switch the primary root.

**Verification Command:**
Switch# show spanning-tree

This command displays the STP status, including the Root Bridge and port roles.
