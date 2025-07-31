# Restore Device Configuration

## Why restore?
You would restore a configuration file to a device to either roll back to a previous state or to quickly set up a new device with a pre-configured template.

## Method: Using a TFTP Server
This process uses the same TFTP server from the backup procedure.

**Prerequisites:**
- A backup configuration file (e.g., `router-config.txt`) on a TFTP server.
- The Cisco device must have IP connectivity to the TFTP server.

## Configuration Example
This example shows how to restore a configuration file from a TFTP server to the running configuration.

**Step 1: Verify IP connectivity**
Router# ping 192.168.1.100


**Step 2: Copy the configuration from the TFTP server**
Router# copy tftp://192.168.1.100/router-config.txt running-config

- The router will prompt you for the source filename.
- The command will load the file into the `running-config`, and all the commands will be executed. This can cause brief network disruptions.

**Step 3: Save the new running configuration**
After the restore is complete, you should save the running configuration to NVRAM.
Router# copy running-config startup-config

This ensures that the device boots up with the restored configuration.
