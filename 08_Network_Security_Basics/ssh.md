# SSH (Secure Shell) Setup

## Why use SSH?
SSH is a cryptographic network protocol that provides a secure way to access a device's command-line interface (CLI). It encrypts all communication, including passwords. This is much safer than using Telnet, which sends all data in plaintext.

## Configuration Example
This example shows the basic steps to configure SSH on a Cisco router or switch.

**Step 1: Configure a hostname and domain name**
Router(config)# hostname MyRouter
MyRouter(config)# ip domain-name mynetwork.local


**Step 2: Generate cryptographic keys**
MyRouter(config)# crypto key generate rsa

- The router will ask you for a key modulus size. A size of 1024 or 2048 is recommended.

**Step 3: Create a local user account**
MyRouter(config)# username admin privilege 15 secret cisco123

- `privilege 15` gives the user full administrative access.

**Step 4: Configure the VTY lines for SSH access**
The VTY lines are the virtual terminal lines used for remote access.
MyRouter(config)# line vty 0 4
MyRouter(config-line)# transport input ssh
MyRouter(config-line)# login local

- `transport input ssh`: This command tells the router to only accept SSH connections on these lines.
- `login local`: This command forces the router to use the local database for authentication.

**Verification Command:**
MyRouter# show ssh

This command displays the status of the SSH server. You can then use an SSH client 
