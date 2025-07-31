# Setting Up EVE-NG

## What is EVE-NG?
EVE-NG (Emulated Virtual Environment for Network, Security, and DevOps Professionals) is a network emulation platform similar to GNS3 but running in a web browser. It's known for its clean interface and ability to run multiple vendor images at once.

**Advantages of EVE-NG:**
- Web-based user interface, no desktop application required.
- Supports a huge variety of vendors (Cisco, Juniper, Fortinet, etc.).
- Easily shareable lab files.

## How to use EVE-NG
1.  **Download and Install:** EVE-NG is typically deployed as a virtual appliance on a hypervisor like VMware or ESXi.
2.  **Initial Setup:** Follow the first-boot wizard to configure network settings.
3.  **Uploading Images:** You need to upload device images (IOS, vIOS, etc.) to the EVE-NG VM. This is usually done via an SCP tool like WinSCP.
4.  **Create a Lab:** Create a new lab in the web interface, add nodes (devices), and start configuring.

**Lab Idea:**
- **Full Security Topology:** Build a lab with a router, a multi-layer switch, and a firewall (e.g., Cisco ASA) to practice a more complete network security configuration.

**Note:** EVE-NG is a powerful tool used by professionals. It can be more complex to set up initially than Packet Tracer.
