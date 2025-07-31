# NAT (Network Address Translation)

## What is NAT?
NAT is a process that translates private IP addresses into public IP addresses. It's used to allow devices on a private network to access the internet using a single public IP address.

**Key NAT Terms:**
- **Inside Local:** The private IP address of a device on the internal network.
- **Inside Global:** The public IP address that the inside local address is translated to.
- **Outside Local:** The public IP address of a destination device on the external network.
- **Outside Global:** The public IP address of the destination device on the external network.

## Types of NAT
1.  **Static NAT:** A one-to-one mapping of a single inside local address to a single inside global address. Useful for servers that need a constant public address.
2.  **Dynamic NAT:** A one-to-many mapping. A pool of inside global addresses is used to translate inside local addresses.
3.  **NAT Overload (PAT):** Also known as Port Address Translation. This is the most common type. It uses a single public IP address and different port numbers to allow multiple inside devices to access the internet.

## NAT Overload (PAT) Configuration
This is a common configuration example for home and small business routers.

**Step 1: Configure the inside and outside interfaces**
Router(config)# interface GigabitEthernet0/1
Router(config-if)# ip nat inside

Router(config)# interface GigabitEthernet0/2
Router(config-if)# ip nat outside

- `ip nat inside`: This command marks the interface connected to the internal network.
- `ip nat outside`: This command marks the interface connected to the internet.

**Step 2: Create a standard ACL to identify traffic to be translated**
Router(config)# access-list 1 permit 192.168.1.0 0.0.0.255

This ACL permits all hosts on the `192.168.1.0/24` network.

**Step 3: Create the NAT Overload rule**
Router(config)# ip nat inside source list 1 interface GigabitEthernet0/2 overload

- `ip nat inside source list 1`: Specifies that the source traffic is defined by ACL 1.
- `interface GigabitEthernet0/2`: Specifies the public IP address to use for the translation (the IP of the outside interface).
- `overload`: Enables Port Address Translation.

**Verification Command:**
Router# show ip nat translations

This command shows the active NAT translations.
