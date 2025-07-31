# RIP (Routing Information Protocol)

## What is RIP?
RIP is a dynamic routing protocol that uses **hop count** as its metric. It is a **distance-vector** protocol, which means it relies on its neighbors to tell it the best paths.

**Key Features:**
- **Simple to configure.**
- **Hop count:** The number of routers a packet must cross to reach its destination.
- **Max hop count:** The maximum hop count is 15. A hop count of 16 is considered "unreachable."
- **Full updates:** Sends its entire routing table to its neighbors every 30 seconds.

**Note:** RIP is an older protocol and is not as widely used in modern networks as OSPF or EIGRP due to its limitations. RIPv2 is the current version.

## Configuration Example
This example shows how to configure RIPv2 on a Cisco router.

**Router 1 Configuration:**
Router1(config)# router rip
Router1(config-router)# version 2
Router1(config-router)# network 10.0.0.0
Router1(config-router)# network 192.168.1.0
Router1(config-router)# no auto-summary


**Router 2 Configuration:**
Router2(config)# router rip
Router2(config-router)# version 2
Router2(config-router)# network 192.168.1.0
Router2(config-router)# network 192.168.2.0
Router2(config-router)# no auto-summary

- `router rip`: Starts the RIP routing process.
- `version 2`: Specifies RIP version 2, which supports VLSM and CIDR.
- `network [network_address]`: This command enables RIP on interfaces within that major network.
- `no auto-summary`: This command is important for RIPv2 as it prevents the protocol from summarizing subnets, allowing for the use of VLSM.

**Verification Command:**
Router1# show ip route rip

This command displays the routes learned via RIP.
