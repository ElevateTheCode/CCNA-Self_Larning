# Backup Device Configuration

## Why backup?
Backing up your router or switch configuration is a critical task. It allows you to quickly restore a device to a known working state in case of a failure, accidental deletion, or misconfiguration.

## Method: Using a TFTP Server
A Trivial File Transfer Protocol (TFTP) server is a simple file server used to transfer files over a network. It's the most common way to back up and restore Cisco configurations.

**Prerequisites:**
- A TFTP server software running on a computer on your network.
- The Cisco device must have IP connectivity to the TFTP server.

## Configuration Example
This example shows how to save the running configuration to a TFTP server.

**Step 1: Verify IP connectivity**
Router# ping 192.168.1.100

- `192.168.1.100` is the IP address of the TFTP server. Make sure the ping is successful.

**Step 2: Copy the running configuration to the TFTP server**
Router# copy running-config tftp://192.168.1.100/router-config.txt

- The router will prompt you for the destination filename. `router-config.txt` is an example.
- The command saves the `running-config` to the TFTP server.

**Note:** You can also back up the `startup-config` by using the command `copy startup-config tftp://...`.
