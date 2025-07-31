# Subnetting, CIDR, and VLSM

## What is Subnetting?
Subnetting is the process of dividing a single large network into smaller, more efficient subnetworks. This helps to reduce network traffic, improve security, and manage IP addresses more effectively.

### How to Subnet
Subnetting involves borrowing bits from the host portion of an IP address to create new network subnets.

**Formulae:**
- **Number of Subnets:** $2^n$ (where $n$ is the number of borrowed bits)
- **Number of Hosts per Subnet:** $2^h - 2$ (where $h$ is the number of remaining host bits)

The "-2" is because the first address (network address) and the last address (broadcast address) in a subnet are unusable for hosts.

## CIDR (Classless Inter-Domain Routing)
CIDR is a method of IP addressing that uses a prefix length (e.g., `/24`) instead of traditional classes. This allows for more flexible and efficient allocation of IP addresses.

- The `/` followed by a number indicates the number of bits in the network portion.
- **Example:** `192.168.1.0/24`
    - This means the first 24 bits are for the network, and the last 8 bits are for the hosts.
    - The subnet mask is `255.255.255.0`.

## VLSM (Variable-Length Subnet Masking)
VLSM is the ability to use different subnet masks on different subnets of a single classful network. This is the most efficient way to use IP addresses, as it prevents wasting large blocks of IP addresses on small networks (e.g., point-to-point links).

**Example:**
- You have a network `192.168.1.0/24`.
- You need a subnet for 50 hosts and another for 2 hosts.
- Using VLSM, you can create a `192.168.1.0/26` subnet for the 50 hosts and a `192.168.1.64/30` subnet for the 2 hosts. This is much more efficient than using a fixed-size `/26` for both.
