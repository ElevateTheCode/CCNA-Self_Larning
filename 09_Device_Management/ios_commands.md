# Basic Cisco IOS Commands

This is a list of essential commands for configuring, verifying, and troubleshooting Cisco devices.

## Global Commands
- `enable`: Enters privileged EXEC mode.
- `configure terminal`: Enters global configuration mode.
- `end`: Returns to privileged EXEC mode from any configuration mode.
- `exit`: Logs out or returns to the previous mode.
- `hostname [name]`: Sets the device hostname.
- `no [command]`: Negates a command.
- `?`: Provides context-sensitive help.

## Interface Commands
- `interface [interface_type] [number]`: Enters interface configuration mode. (e.g., `interface gigabitethernet 0/1`)
- `ip address [ip_address] [subnet_mask]`: Configures an IP address on an interface.
- `no shutdown`: Enables an interface.
- `shutdown`: Disables an interface.

## Show Commands (for Verification)
- `show version`: Displays the Cisco IOS version, hardware, and uptime.
- `show ip interface brief`: A quick summary of all interfaces and their IP addresses and status.
- `show running-config`: Displays the currently active configuration.
- `show startup-config`: Displays the configuration saved in NVRAM.
- `show ip route`: Displays the routing table.
- `show cdp neighbors`: Displays a list of directly connected Cisco devices.
- `show vlan brief`: Displays a summary of all configured VLANs.

## Other Useful Commands
- `copy running-config startup-config`: Saves the active configuration to NVRAM.
- `reload`: Reboots the device.
- `erase startup-config`: Deletes the saved configuration.
- `ping [ip_address]`: Tests connectivity to another device.
- `telnet [ip_address]`: Connects to a remote device using Telnet.
- `terminal history size [number]`: Sets the size of the command history buffer.
