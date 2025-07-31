# IPv4 Addressing Basics

## What is IPv4?
IPv4 (Internet Protocol version 4) is a 32-bit logical address. It's a unique identifier for a device on a network. An IPv4 address is written in dotted-decimal notation, like `192.168.1.1`.

## Address Structure
An IPv4 address is divided into two parts:
1.  **Network Portion:** Identifies the network the device belongs to.
2.  **Host Portion:** Identifies the specific device within that network.

The **Subnet Mask** is used to determine which part is the network and which is the host. A '1' in the subnet mask indicates a network bit, and a '0' indicates a host bit.

**Example:**
- IP Address: `192.168.1.10`
- Subnet Mask: `255.255.255.0`
- This means the first three octets (`192.168.1`) are the Network Portion, and the last octet (`10`) is the Host Portion.

## IP Address Classes
Historically, IP addresses were categorized into classes based on the first octet.
- **Class A:** First octet `1-126`. Default subnet mask `255.0.0.0`. (Large networks)
- **Class B:** First octet `128-191`. Default subnet mask `255.255.0.0`. (Medium networks)
- **Class C:** First octet `192-223`. Default subnet mask `255.255.255.0`. (Small networks)
- **Class D:** `224-239`. Reserved for multicasting.
- **Class E:** `240-255`. Reserved for experimental use.

## Private vs. Public IP Addresses
- **Private IP addresses** are used within a private network (e.g., your home or office LAN). They are not routable on the public internet.
    - `10.0.0.0` to `10.255.255.255` (Class A)
    - `172.16.0.0` to `172.31.255.255` (Class B)
    - `192.168.0.0` to `192.168.255.255` (Class C)
- **Public IP addresses** are globally unique and are routable on the internet.
