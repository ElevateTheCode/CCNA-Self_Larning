# SNMP (Simple Network Management Protocol)

## What is SNMP?
SNMP is an application-layer protocol used to manage and monitor network devices. It allows a central network management system (NMS) to poll devices for information and receive alerts about events.

**Key Components:**
- **SNMP Manager (NMS):** The central station that runs the network monitoring software.
- **SNMP Agent:** Software that runs on the managed device (router, switch, server) and collects information.
- **Management Information Base (MIB):** A database of information about the device's status and statistics. The SNMP agent makes this information available to the NMS.

## Basic Configuration
This example shows how to configure a Cisco device with an SNMP agent.

**Step 1: Configure a community string**
A community string acts like a password to authenticate the NMS. There are two types: `read-only` and `read-write`.

Router(config)# snmp-server community CCNA-READ-ONLY ro
Router(config)# snmp-server community CCNA-READ-WRITE rw

- `snmp-server community [string] [permission]`: This command configures the community string.
- `ro`: read-only permission. The NMS can only view device information.
- `rw`: read-write permission. The NMS can view and modify device configuration.

**Step 2: (Optional) Configure a host to receive traps**
A trap is an alert message sent from the SNMP agent to the NMS when a specific event occurs.

Router(config)# snmp-server host 10.1.1.1 traps version 2c CCNA-READ-ONLY

- `snmp-server host [NMS_ip] traps`: Specifies the IP address of the NMS to send traps to.
- `version 2c`: Specifies the SNMP version.

**Verification Command:**
There is no direct `show` command for SNMP. You need to use a network monitoring tool (like PRTG or SolarWinds) to verify the configuration.
