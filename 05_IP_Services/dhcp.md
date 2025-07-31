# DHCP (Dynamic Host Configuration Protocol)

## What is DHCP?
DHCP is a network protocol that automatically assigns IP addresses and other network configuration parameters to devices on a network. This eliminates the need for manual configuration and makes network management easier.

**DHCP provides:**
- IP Address
- Subnet Mask
- Default Gateway
- DNS Server IP

## Configuration Example
This example shows how to configure a Cisco router to act as a DHCP server.

**Step 1: Exclude addresses from the pool**
It's good practice to exclude addresses that are statically assigned (e.g., to servers or routers).
Router(config)# ip dhcp excluded-address 192.168.1.1 192.168.1.10


**Step 2: Create the DHCP pool**
Router(config)# ip dhcp pool LAN-POOL-1
Router(dhcp-config)# network 192.168.1.0 255.255.255.0
Router(dhcp-config)# default-router 192.168.1.1
Router(dhcp-config)# dns-server 8.8.8.8

- `ip dhcp pool LAN-POOL-1`: Creates a DHCP pool with the name "LAN-POOL-1".
- `network 192.168.1.0 255.255.255.0`: Defines the network for which this pool will assign addresses.
- `default-router 192.168.1.1`: Specifies the default gateway for clients.
- `dns-server 8.8.8.8`: Specifies the DNS server for clients.

**Verification Command:**
Router# show ip dhcp pool
Router# show ip dhcp binding

- `show ip dhcp pool` shows a summary of the DHCP pools.
- `show ip dhcp binding` shows which IP addresses have been leased to clients.
