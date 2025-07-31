# GNS3 Lab Files and Explanation

## What is GNS3?
GNS3 (Graphical Network Simulator-3) is a more powerful and realistic network emulator than Packet Tracer. It allows you to run actual Cisco IOS images and connect them to real-world devices, virtual machines, and other software.

**Advantages of GNS3:**
- Uses real Cisco IOS, allowing you to practice with more advanced features.
- Can integrate with virtual machines (e.g., a Windows Server VM) to create more realistic network environments.
- Supports a wider range of network devices.

## How to use GNS3
1.  **Installation:** Download and install GNS3 from the official website. You'll also need a hypervisor like VirtualBox or VMware Workstation.
2.  **Obtaining IOS Images:** GNS3 does not come with Cisco IOS images. You must obtain them legally from Cisco or through other means.
3.  **Create a New Project:** Start a new project and drag and drop routers, switches, and other devices onto the canvas.
4.  **Configuration:** Right-click a device and select `Console` to access its CLI and start configuring.

## GNS3 Lab Ideas
- **OSPF Multi-Area:** Practice configuring a network with a backbone area (Area 0) and several non-backbone areas.
- **EIGRP Configuration:** Use GNS3 to practice configuring EIGRP, which is not available in Packet Tracer.
- **Frame Relay:** Simulate complex WAN technologies.

**Note:** GNS3 requires more resources (RAM, CPU) than Packet Tracer.
