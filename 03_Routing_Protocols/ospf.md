# OSPF (Open Shortest Path First)

## What is OSPF?
OSPF is a dynamic routing protocol that uses the **Dijkstra algorithm** to find the shortest path to all destinations. It is a **link-state** protocol, which means each router has a complete "map" of the network topology.

**Key Features:**
- **Fast convergence:** Quickly reacts to changes in the network.
- **Scalable:** Works well in large and complex network environments.
- **Classless:** Supports VLSM and CIDR.
- **Metric:** Uses "cost," which is based on link bandwidth. Lower cost is better.

## OSPF Areas
OSPF uses a hierarchical structure with areas.
- **Area 0 (Backbone Area):** The central area that connects all other areas.
- **Non-Backbone Areas:** All other areas must connect to Area 0.

## Simple Single-Area Configuration
This example shows how to configure OSPF on two routers in a single area (Area 0).

**Router 1 Configuration:**
Router1(config)# router ospf 1
Router1(config-router)# network 10.0.0.0 0.255.255.255 area 0
Router1(config-router)# network 192.168.1.0 0.0.0.255 area 0


**Router 2 Configuration:**
Router2(config)# router ospf 1
Router2(config-router)# network 192.168.1.0 0.0.0.255 area 0
Router2(config-router)# network 192.168.2.0 0.0.0.255 area 0

- `router ospf 1`: Starts the OSPF process with a process ID (1 in this case, can be any number).
- `network [network_address] [wildcard_mask] area [area_id]`: This command enables OSPF on the interfaces that match the specified network address. The wildcard mask is the inverse of the subnet mask.

**Verification Commands:**
Router1# show ip ospf neighbor
Router1# show ip route ospf

`show ip ospf neighbor` checks if the router has established a neighbor relationship. `show ip route ospf` shows the routes learned via OSPF.
