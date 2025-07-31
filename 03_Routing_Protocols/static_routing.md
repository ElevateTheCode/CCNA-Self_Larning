# Static Routing

## What is Static Routing?
Static routing is a process where a network administrator manually configures a router's routing table. The routes are fixed and do not change unless an administrator changes them.

**When to use it:**
- For small, simple networks.
- For a specific path to a destination (e.g., a "default route" to the internet).
- When a dynamic routing protocol is not desired due to security or resource constraints.

## Configuration Example
This example shows how to configure a static route on a Cisco router.

**Scenario:**
- Router A needs to reach the network `192.168.2.0/24`.
- The next-hop router's IP address is `192.168.1.2`.
