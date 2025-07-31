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


- RouterA(config)# ip route 192.168.2.0 255.255.255.0 192.168.1.2
**Syntax:**
`ip route [destination_network] [subnet_mask] [next_hop_ip_address]`

### Default Static Route
A default route is a special type of static route that is used when a router does not have a specific path to a destination. It's often used to direct all unknown traffic to an upstream router or the internet.

- RouterA(config)# ip route 0.0.0.0 0.0.0.0 192.168.1.2
**Syntax:**
`ip route 0.0.0.0 0.0.0.0 [next_hop_ip_address]`
The `0.0.0.0 0.0.0.0` part means "match all networks with all subnet masks."

**Verification Command:**

- RouterA# show ip route static
This command shows all the static routes configured on the router.


