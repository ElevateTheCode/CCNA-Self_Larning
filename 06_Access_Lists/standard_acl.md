# Standard Access Control Lists (ACLs)

## What are ACLs?
An Access Control List (ACL) is a set of rules used on a router or switch to filter network traffic. ACLs can permit or deny traffic based on specific criteria.

## Standard ACLs
- **Criterion:** Standard ACLs filter traffic based *only* on the **source IP address**.
- **Placement:** They should be placed as close to the **destination** as possible to avoid accidentally filtering traffic from other parts of the network.
- **Syntax:** `access-list [acl_number] [permit|deny] [source_ip] [wildcard_mask]`
- **Numbered:** `1-99` and `1300-1999`
- **Named:** `ip access-list standard [name]`

**Implicit Deny:** Every ACL has an invisible `deny any` statement at the end. This means if traffic does not match any of the ACL's rules, it will be dropped.

## Configuration Example
This example shows how to create a standard ACL to deny traffic from a specific host and then permit all other traffic.

**Scenario:**
- Deny host `192.168.1.10` from reaching any destination.
- Allow all other hosts on the `192.168.1.0/24` network.
- Apply the ACL on the `GigabitEthernet0/1` interface.

**Step 1: Create the ACL**
Router(config)# access-list 10 deny host 192.168.1.10
Router(config)# access-list 10 permit 192.168.1.0 0.0.0.255

- `deny host 192.168.1.10`: A shorthand for `192.168.1.10 0.0.0.0`, which matches a single host.
- `permit 192.168.1.0 0.0.0.255`: Permits all hosts in the `192.168.1.0/24` network.

**Step 2: Apply the ACL to an interface**
Router(config)# interface GigabitEthernet0/1
Router(config-if)# ip access-group 10 out

- `ip access-group 10 out`: Applies ACL 10 to outbound traffic on this interface.

**Verification Command:**
Router# show access-lists

This command displays all configured ACLs.
