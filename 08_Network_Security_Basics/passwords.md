# Device Passwords

## Why are passwords important?
Passwords are the first line of defense to prevent unauthorized access to your network devices. Cisco IOS has several types of passwords to protect different levels of access.

## Types of Passwords
1.  **Console Password:** Protects the physical console port.
2.  **VTY Password:** Protects the virtual terminal lines used for remote access (Telnet/SSH).
3.  **Enable Secret Password:** Protects privileged EXEC mode (the `enable` command). This is the most secure password and is encrypted by default.
4.  **Enable Password:** An older, unencrypted version of the enable password. It's not recommended to use this.

## Configuration Example
This example shows how to configure the most important passwords.

**Step 1: Configure the Enable Secret password**
Router(config)# enable secret cisco123

- This password is encrypted and should always be used instead of `enable password`.

**Step 2: Configure the Console password**
Router(config)# line console 0
Router(config-line)# password cisco
Router(config-line)# login

- `password cisco`: Sets the password.
- `login`: Enables the password prompt.

**Step 3: Configure the VTY password (for Telnet)**
Router(config)# line vty 0 4
Router(config-line)# password cisco
Router(config-line)# login

- `line vty 0 4`: Configures the first 5 VTY lines (for 5 simultaneous remote connections).
- **Note:** For SSH, you should use `login local` and a local username/password instead of a VTY password.

**Step 4: Encrypt all passwords**
To protect plaintext passwords (like the console/VTY passwords), you can use the `service password-encryption` command.
Router(config)# service password-encryption


**Verification Command:**
Router# show running-config

This command shows all configured passwords, with the `enable secret` and other passwords properly encrypted if you've enabled encryption.
