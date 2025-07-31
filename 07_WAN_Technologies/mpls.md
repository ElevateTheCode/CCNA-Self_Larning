# MPLS (Multiprotocol Label Switching)

## What is MPLS?
MPLS is a high-performance, flexible WAN technology that directs data from one network node to the next based on short path labels rather than long network addresses.

**How does it work?**
- In a traditional IP network, each router independently makes a forwarding decision based on the destination IP address in the packet header.
- In an MPLS network, the ingress router (first router) assigns a small, fixed-length label to each packet.
- Subsequent routers (Label Switching Routers or LSRs) simply use this label to forward the packet to the next hop, which is much faster than a full IP lookup.

**Key Benefits:**
- **Faster forwarding:** Label switching is more efficient than IP routing.
- **Traffic engineering:** MPLS allows for fine-grained control over network paths.
- **VPNs:** It's the foundation for many service provider VPN offerings (MPLS L3VPN).

## MPLS Terminology
- **Label:** A short, fixed-length identifier.
- **Label Edge Router (LER):** The router at the edge of the MPLS network that adds and removes labels.
- **Label Switching Router (LSR):** A router inside the MPLS cloud that forwards packets based on their labels.

**Note:** The CCNA exam does not require detailed configuration of MPLS. It's important to understand the concept and its role as a WAN technology.
